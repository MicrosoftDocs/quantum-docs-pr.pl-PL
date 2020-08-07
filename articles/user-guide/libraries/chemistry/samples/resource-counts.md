---
title: Uzyskiwanie liczb zasobów
description: Dowiedz się, jak uzyskać oszacowania zasobów przy użyciu symulatora śledzenia Quantum.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
no-loc:
- Q#
- $$v
ms.openlocfilehash: 35c16e622a390b730ad7385efcc365c212e981fe
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869328"
---
# <a name="obtaining-resource-counts"></a>Uzyskiwanie liczb zasobów

Koszt symulowania $n $ qubits na klasycznych komputerach jest skalowany wykładniczo z $n $. Znacznie ogranicza to rozmiar symulacji chemii Quantum, którą możemy wykonać przy użyciu symulatora pełnego stanu. W przypadku dużych wystąpień chemii firma Microsoft może jednak uzyskać przydatne informacje. Tutaj sprawdzimy, jak koszty zasobów, takie jak liczba bram T lub bram CNOT, do symulowania chemii, można uzyskać w zautomatyzowany sposób przy użyciu [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Informacje te informuje nas, gdy komputery Quantum mogą być wystarczająco duże, aby można było uruchamiać te algorytmy biochemiczne. Aby uzyskać informacje, zobacz podany `GetGateCount` przykład.

Załóżmy, że mamy już `FermionHamiltonian` wystąpienie, na przykład załadowane ze schematu Broombridge, zgodnie z opisem w przykładzie [ładowania z pliku](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) . 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

Składnia służąca do uzyskiwania oszacowań zasobów jest niemal identyczna z uruchamianiem algorytmu w symulatorze pełnego stanu. Po prostu wybieramy inną maszynę docelową. Na potrzeby oszacowań zasobów wystarcza do oceny kosztu pojedynczego kroku Trotter lub określenia Quantum utworzonego przez technikę Qubitization. Do wywoływania tych algorytmów stosuje się następujący sposób.

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

Teraz skonfigurujemy symulator śledzenia do śledzenia interesujących Cię zasobów. W tym przypadku liczą pierwotne operacje Quantum przez ustawienie `usePrimitiveOperationsCounter` flagi na `true` . Szczegółami technicznymi `throwOnUnconstraintMeasurement` jest ustawienie, aby `false` uniknąć wyjątków w przypadkach, w których kod nie popełnił Q# prawdopodobieństwa wyników pomiarów, jeśli są wykonywane.

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

Algorytm Quantum jest teraz uruchamiany z programu sterownika w następujący sposób.

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```
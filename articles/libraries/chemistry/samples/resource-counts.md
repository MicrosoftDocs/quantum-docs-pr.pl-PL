---
title: Uzyskiwanie liczników zasobów | Microsoft Docs
description: Uzyskiwanie dokumentacji dotyczącej liczby zasobów
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: f9311c1987ced4336c4e98bdb984fbee009e9acc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442451"
---
# <a name="obtaining-resource-counts"></a><span data-ttu-id="617f5-103">Uzyskiwanie liczb zasobów</span><span class="sxs-lookup"><span data-stu-id="617f5-103">Obtaining resource counts</span></span>

<span data-ttu-id="617f5-104">Koszt symulowania $n $ qubits na klasycznych komputerach jest skalowany wykładniczo z $n $.</span><span class="sxs-lookup"><span data-stu-id="617f5-104">The cost of simulating $n$ qubits on classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="617f5-105">Znacznie ogranicza to rozmiar symulacji chemii Quantum, którą możemy wykonać przy użyciu symulatora pełnego stanu.</span><span class="sxs-lookup"><span data-stu-id="617f5-105">This greatly limits the size of a quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="617f5-106">W przypadku dużych wystąpień chemii firma Microsoft może jednak uzyskać przydatne informacje.</span><span class="sxs-lookup"><span data-stu-id="617f5-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="617f5-107">Tutaj sprawdzimy, jak koszty zasobów, takie jak liczba bram T lub bram CNOT, do symulowania chemii, można uzyskać w zautomatyzowany sposób przy użyciu [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="617f5-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="617f5-108">Informacje te informuje nas, gdy komputery Quantum mogą być wystarczająco duże, aby można było uruchamiać te algorytmy biochemiczne.</span><span class="sxs-lookup"><span data-stu-id="617f5-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="617f5-109">Aby uzyskać informacje, zobacz podanego przykładu `GetGateCount`.</span><span class="sxs-lookup"><span data-stu-id="617f5-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="617f5-110">Załóżmy, że mamy już wystąpienie `FermionHamiltonian`, na przykład załadowane ze schematu Broombridge, zgodnie z opisem w przykładzie [ładowania z pliku](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="617f5-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="617f5-111">Składnia służąca do uzyskiwania oszacowań zasobów jest niemal identyczna z uruchamianiem algorytmu w symulatorze pełnego stanu.</span><span class="sxs-lookup"><span data-stu-id="617f5-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="617f5-112">Po prostu wybieramy inną maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="617f5-112">We simply choose a different target machine.</span></span> <span data-ttu-id="617f5-113">Na potrzeby oszacowań zasobów wystarcza do oceny kosztu pojedynczego kroku Trotter lub określenia Quantum utworzonego przez technikę Qubitization.</span><span class="sxs-lookup"><span data-stu-id="617f5-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="617f5-114">Do wywoływania tych algorytmów stosuje się następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="617f5-114">The boilerplate for invoking these algorithms is as follows.</span></span>

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

<span data-ttu-id="617f5-115">Teraz skonfigurujemy symulator śledzenia do śledzenia interesujących Cię zasobów.</span><span class="sxs-lookup"><span data-stu-id="617f5-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="617f5-116">W tym przypadku liczą pierwotne operacje Quantum przez ustawienie flagi `usePrimitiveOperationsCounter`, aby `true`.</span><span class="sxs-lookup"><span data-stu-id="617f5-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="617f5-117">`throwOnUnconstraintMeasurement` szczegóły techniczne są ustawiane na `false`, aby uniknąć wyjątków w przypadkach, gdy kod Q nie popełnił prawdopodobieństwa wyników pomiarów, jeśli są wykonywane.</span><span class="sxs-lookup"><span data-stu-id="617f5-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probability of measurement outcomes, if any are performed.</span></span>

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

<span data-ttu-id="617f5-118">Algorytm Quantum jest teraz uruchamiany z programu sterownika w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="617f5-118">We now run the quantum algorithm from the driver program as follows.</span></span>

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
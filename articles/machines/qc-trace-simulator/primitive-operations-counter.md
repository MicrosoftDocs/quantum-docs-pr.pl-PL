---
title: Licznik operacji pierwotnych | Symulator śledzenia komputerów Quantum | Microsoft Docs
description: Omówienie symulatora śledzenia komputerów z interfejsem Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184886"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="72442-103">Licznik operacji pierwotnych</span><span class="sxs-lookup"><span data-stu-id="72442-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="72442-104">`Primitive Operations Counter` jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum.</span><span class="sxs-lookup"><span data-stu-id="72442-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="72442-105">Liczy liczbę wykonań pierwotnych używanych przez każdą operację wywoływaną w programie Quantum.</span><span class="sxs-lookup"><span data-stu-id="72442-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="72442-106">Wszystkie operacje z `Microsoft.Quantum.Primitive` są wyrażane w zakresie pojedynczych rotacji qubit, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów dla wieloqubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="72442-106">All operations from `Microsoft.Quantum.Primitive` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="72442-107">Zebrane dane statystyczne są agregowane na krawędziach grafu wywołań operacji.</span><span class="sxs-lookup"><span data-stu-id="72442-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="72442-108">Poinformuj nas o liczbie bram `T` potrzebnych do zaimplementowania operacji `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="72442-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="72442-109">Korzystanie z licznika operacji pierwotnych w C# ramach programu</span><span class="sxs-lookup"><span data-stu-id="72442-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="72442-110">Aby sprawdzić, czy `CCNOT` rzeczywiście wymagają 7 bram `T` i że `CCNOTDriver` wykonuje 8 bram `T`, możemy użyć następującego C# kodu:</span><span class="sxs-lookup"><span data-stu-id="72442-110">To check that `CCNOT` indeed requires 7 `T` gates and that `CCNOTDriver` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="72442-111">Pierwsza część programu jest wykonywana `CCNOTDriver`.</span><span class="sxs-lookup"><span data-stu-id="72442-111">The first part of the program executes `CCNOTDriver`.</span></span> <span data-ttu-id="72442-112">W drugiej części używamy metody `QCTraceSimulator.GetMetric`, aby uzyskać liczbę bram T wykonywanych przez `CCNOTDriver`:</span><span class="sxs-lookup"><span data-stu-id="72442-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `CCNOTDriver`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="72442-113">Gdy `GetMetric` jest wywoływana z dwoma parametrami typu, zwraca wartość metryki skojarzonej z daną krawędzią grafu wywołania.</span><span class="sxs-lookup"><span data-stu-id="72442-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="72442-114">W naszym przykładzie operacja `Primitive.CCNOT` jest wywoływana w `CCNOTDriver` i dlatego wykres wywołań zawiera `<Primitive.CCNOT,CCNOTDriver>`krawędzi.</span><span class="sxs-lookup"><span data-stu-id="72442-114">In our example operation `Primitive.CCNOT` is called within `CCNOTDriver` and therefore the call graph contains the edge `<Primitive.CCNOT,CCNOTDriver>`.</span></span> 

<span data-ttu-id="72442-115">Aby uzyskać liczbę używanych bram `CNOT`, można dodać następujący wiersz:</span><span class="sxs-lookup"><span data-stu-id="72442-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="72442-116">Na koniec w celu wygenerowania wszystkich statystyk zbieranych przez licznik bram w formacie CSV można użyć następujących instrukcji:</span><span class="sxs-lookup"><span data-stu-id="72442-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="72442-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="72442-117">See also</span></span> ##

- <span data-ttu-id="72442-118">Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.</span><span class="sxs-lookup"><span data-stu-id="72442-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>

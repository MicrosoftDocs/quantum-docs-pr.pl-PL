---
title: Licznik operacji pierwotnych
description: Dowiedz się więcej o liczniku operacji programu Microsoft QDKe pierwotne, który śledzi liczbę wykonań pierwotnych używanych przez operacje w programie Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275557"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="c0d37-103">Licznik operacji pierwotnych</span><span class="sxs-lookup"><span data-stu-id="c0d37-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="c0d37-104">`Primitive Operations Counter`Jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum.</span><span class="sxs-lookup"><span data-stu-id="c0d37-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="c0d37-105">Liczy liczbę wykonań pierwotnych używanych przez każdą operację wywoływaną w programie Quantum.</span><span class="sxs-lookup"><span data-stu-id="c0d37-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="c0d37-106">Wszystkie operacje z `Microsoft.Quantum.Intrinsic` są wyrażane w odniesieniu do pojedynczych qubitych obrotów, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów wieloqubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="c0d37-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="c0d37-107">Zebrane dane statystyczne są agregowane na krawędziach grafu wywołań operacji.</span><span class="sxs-lookup"><span data-stu-id="c0d37-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="c0d37-108">Pozwól nam teraz obliczyć liczbę `T` bram potrzebnych do zaimplementowania `CCNOT` operacji.</span><span class="sxs-lookup"><span data-stu-id="c0d37-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="c0d37-109">Korzystanie z licznika operacji pierwotnych w programie w języku C#</span><span class="sxs-lookup"><span data-stu-id="c0d37-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="c0d37-110">Aby sprawdzić, czy w `CCNOT` rzeczywistości wymagane `T` są 7 bram i które `ApplySampleWithCCNOT` wykonuje 8 `T` bram, możemy użyć następującego kodu w języku C#:</span><span class="sxs-lookup"><span data-stu-id="c0d37-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="c0d37-111">Zostanie wykonana pierwsza część programu `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="c0d37-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="c0d37-112">W drugiej części używamy metody, `QCTraceSimulator.GetMetric` Aby uzyskać liczbę bram T wykonywanych przez `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="c0d37-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="c0d37-113">Gdy `GetMetric` jest wywoływana z dwoma parametrami typu, zwraca wartość metryki skojarzonej z daną krawędzią grafu wywołania.</span><span class="sxs-lookup"><span data-stu-id="c0d37-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="c0d37-114">W naszej przykładowej operacji `Primitive.CCNOT` jest wywoływana wewnątrz `ApplySampleWithCCNOT` i dlatego wykres wywołań zawiera krawędź `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="c0d37-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="c0d37-115">Aby uzyskać liczbę `CNOT` używanych bram, można dodać następujący wiersz:</span><span class="sxs-lookup"><span data-stu-id="c0d37-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="c0d37-116">Na koniec w celu wygenerowania wszystkich statystyk zbieranych przez licznik bram w formacie CSV można użyć następujących instrukcji:</span><span class="sxs-lookup"><span data-stu-id="c0d37-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="c0d37-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c0d37-117">See also</span></span> ##

- <span data-ttu-id="c0d37-118">Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.</span><span class="sxs-lookup"><span data-stu-id="c0d37-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>

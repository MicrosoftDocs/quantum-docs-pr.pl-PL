---
title: Licznik operacji pierwotnych-Quantum Development Kit
description: 'Dowiedz się więcej o liczniku operacji programu Microsoft QDKe pierwotnego, który korzysta z symulatora śledzenia Quantum do śledzenia wykonywania pierwotnego używanych przez operacje w programie Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: ea022d499354f7cefd60da690466496e0ce7c336
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871029"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="206cb-103">Symulator śledzenia Quantum: licznik operacji pierwotnych</span><span class="sxs-lookup"><span data-stu-id="206cb-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="206cb-104">Licznik operacji pierwotnej jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="206cb-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="206cb-105">Liczy liczbę wykonań pierwotnych używanych przez każdą operację wywoływaną w programie Quantum.</span><span class="sxs-lookup"><span data-stu-id="206cb-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="206cb-106">Wszystkie <xref:microsoft.quantum.intrinsic> operacje są wyrażane w odniesieniu do rotacji qubit, operacji T, operacji qubit Clifford, operacji CNOT i pomiarów wieloqubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="206cb-106">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="206cb-107">Licznik operacji pierwotnych agreguje i zbiera dane statystyczne na temat wszystkich krawędzi [grafu wywołania](https://en.wikipedia.org/wiki/Call_graph)operacji.</span><span class="sxs-lookup"><span data-stu-id="206cb-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="206cb-108">Wywoływanie licznika operacji pierwotnej</span><span class="sxs-lookup"><span data-stu-id="206cb-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="206cb-109">Aby uruchomić symulator śledzenia Quantum z licznikiem operacji pierwotnej, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UsePrimitiveOperationsCounter` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru.</span><span class="sxs-lookup"><span data-stu-id="206cb-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="206cb-110">Używanie licznika operacji pierwotnej w programie hosta C#</span><span class="sxs-lookup"><span data-stu-id="206cb-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="206cb-111">Przykład w języku C# opisany w tej sekcji liczy liczbę <xref:microsoft.quantum.intrinsic.t> operacji potrzebnych do zaimplementowania <xref:microsoft.quantum.intrinsic.ccnot> operacji w oparciu o następujący przykładowy kod Q #:</span><span class="sxs-lookup"><span data-stu-id="206cb-111">The C# example that follows in this section counts how many <xref:microsoft.quantum.intrinsic.t> operations are needed to implement the <xref:microsoft.quantum.intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="206cb-112">Aby sprawdzić, czy program `CCNOT` wymaga siedmiu `T` operacji `ApplySampleWithCCNOT` , które uruchamiają osiem `T` operacji, użyj następującego kodu w języku C#:</span><span class="sxs-lookup"><span data-stu-id="206cb-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="206cb-113">Zostanie uruchomiona pierwsza część programu `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="206cb-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="206cb-114">Druga część używa [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metody do pobierania liczby `T` operacji wykonywanych przez `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="206cb-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="206cb-115">W przypadku wywołania `GetMetric` z dwoma parametrami typu zwraca wartość metryki skojarzonej z daną krawędzią grafu wywołania.</span><span class="sxs-lookup"><span data-stu-id="206cb-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="206cb-116">W poprzednim przykładzie program wywołuje `Primitive.CCNOT` operację w ramach `ApplySampleWithCCNOT` i dlatego wykres wywołań zawiera krawędź `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="206cb-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="206cb-117">Aby pobrać liczbę `CNOT` używanych operacji, Dodaj następujący wiersz:</span><span class="sxs-lookup"><span data-stu-id="206cb-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="206cb-118">Na koniec można wyprowadzić wszystkie dane statystyczne zebrane przez licznik operacji pierwotnych w formacie CSV, korzystając z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="206cb-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="206cb-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="206cb-119">See also</span></span>

- <span data-ttu-id="206cb-120">Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="206cb-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="206cb-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="206cb-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="206cb-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="206cb-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="206cb-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="206cb-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>
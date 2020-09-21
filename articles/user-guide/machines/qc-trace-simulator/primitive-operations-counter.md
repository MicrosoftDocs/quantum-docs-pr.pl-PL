---
title: Licznik operacji pierwotnych-Quantum Development Kit
description: Dowiedz się więcej o liczniku operacji programu Microsoft QDKe podstawowe, który korzysta z symulatora śledzenia Quantum do śledzenia procesów pierwotnych używanych przez operacje w Q# programie.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8ee9ce25e680112e2f3c68d82ae9267c1b0fb355
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835982"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="f6efa-103">Symulator śledzenia Quantum: licznik operacji pierwotnych</span><span class="sxs-lookup"><span data-stu-id="f6efa-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="f6efa-104">Licznik operacji pierwotnej jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="f6efa-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="f6efa-105">Liczy liczbę procesów pierwotnych używanych przez każdą operację wywoływaną w programie Quantum.</span><span class="sxs-lookup"><span data-stu-id="f6efa-105">It counts the number of primitive processes used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="f6efa-106">Wszystkie <xref:microsoft.quantum.intrinsic> operacje są wyrażane w odniesieniu do rotacji qubit, operacji T, operacji qubit Clifford, operacji CNOT i pomiarów wieloqubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="f6efa-106">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="f6efa-107">Licznik operacji pierwotnych agreguje i zbiera dane statystyczne na temat wszystkich krawędzi [grafu wywołania](https://en.wikipedia.org/wiki/Call_graph)operacji.</span><span class="sxs-lookup"><span data-stu-id="f6efa-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="f6efa-108">Wywoływanie licznika operacji pierwotnej</span><span class="sxs-lookup"><span data-stu-id="f6efa-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="f6efa-109">Aby uruchomić symulator śledzenia Quantum z licznikiem operacji pierwotnej, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UsePrimitiveOperationsCounter` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru.</span><span class="sxs-lookup"><span data-stu-id="f6efa-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="f6efa-110">Używanie licznika operacji pierwotnej w programie hosta C#</span><span class="sxs-lookup"><span data-stu-id="f6efa-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="f6efa-111">Poniższy przykład kodu w języku C# jest częścią liczby <xref:microsoft.quantum.intrinsic.t> operacji potrzebnych do zaimplementowania <xref:microsoft.quantum.intrinsic.ccnot> operacji w oparciu o następujący Q# przykładowy kod:</span><span class="sxs-lookup"><span data-stu-id="f6efa-111">The C# example that follows in this section counts how many <xref:microsoft.quantum.intrinsic.t> operations are needed to implement the <xref:microsoft.quantum.intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="f6efa-112">Aby sprawdzić, czy program `CCNOT` wymaga siedmiu `T` operacji `ApplySampleWithCCNOT` , które uruchamiają osiem `T` operacji, użyj następującego kodu w języku C#:</span><span class="sxs-lookup"><span data-stu-id="f6efa-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

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

<span data-ttu-id="f6efa-113">Zostanie uruchomiona pierwsza część programu `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="f6efa-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="f6efa-114">Druga część używa [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metody do pobierania liczby `T` operacji wykonywanych przez `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="f6efa-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="f6efa-115">W przypadku wywołania `GetMetric` z dwoma parametrami typu zwraca wartość metryki skojarzonej z daną krawędzią grafu wywołania.</span><span class="sxs-lookup"><span data-stu-id="f6efa-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="f6efa-116">W poprzednim przykładzie program wywołuje `Primitive.CCNOT` operację w ramach `ApplySampleWithCCNOT` i dlatego wykres wywołań zawiera krawędź `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="f6efa-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="f6efa-117">Aby pobrać liczbę `CNOT` używanych operacji, Dodaj następujący wiersz:</span><span class="sxs-lookup"><span data-stu-id="f6efa-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="f6efa-118">Na koniec można wyprowadzić wszystkie dane statystyczne zebrane przez licznik operacji pierwotnych w formacie CSV, korzystając z następujących elementów:</span><span class="sxs-lookup"><span data-stu-id="f6efa-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="f6efa-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f6efa-119">See also</span></span>

- <span data-ttu-id="f6efa-120">Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="f6efa-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="f6efa-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="f6efa-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="f6efa-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="f6efa-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="f6efa-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="f6efa-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>
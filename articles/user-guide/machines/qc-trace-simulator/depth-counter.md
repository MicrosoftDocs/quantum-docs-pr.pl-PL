---
title: Licznik głębokości-Quantum Development Kit
description: Dowiedz się więcej o liczniku głębokości QDK firmy Microsoft, który używa symulatora śledzenia Quantum do zbierania informacji o głębokości każdej operacji wywoływanej w Q# programie.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5c54f6fc479203d30c68c4958329605d4323f9ea
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868325"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="56769-103">Symulator śledzenia Quantum: licznik głębokości</span><span class="sxs-lookup"><span data-stu-id="56769-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="56769-104">Licznik głębokości jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="56769-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="56769-105">Można jej użyć do zebrania liczb, które reprezentują dolną granicę głębokości każdej operacji wywołanej w programie Quantum.</span><span class="sxs-lookup"><span data-stu-id="56769-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="56769-106">Wartości głębokości</span><span class="sxs-lookup"><span data-stu-id="56769-106">Depth values</span></span>

<span data-ttu-id="56769-107">Domyślnie wszystkie operacje mają głębokość **0** z wyjątkiem `T` operacji, która ma głębokość **1**.</span><span class="sxs-lookup"><span data-stu-id="56769-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="56769-108">Oznacza to, że domyślnie `T` obliczana jest tylko głębokość operacji (co jest często pożądane).</span><span class="sxs-lookup"><span data-stu-id="56769-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="56769-109">Licznik głębokości agreguje i zbiera dane statystyczne na temat wszystkich krawędzi [grafu wywołania](https://en.wikipedia.org/wiki/Call_graph)operacji.</span><span class="sxs-lookup"><span data-stu-id="56769-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="56769-110">Wszystkie <xref:microsoft.quantum.intrinsic> operacje są wyrażane w zakresie obrotów qubit, operacji <xref:microsoft.quantum.intrinsic.t> , operacji qubit Clifford, <xref:microsoft.quantum.intrinsic.cnot> operacji i pomiarów wieloqubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="56769-110">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, <xref:microsoft.quantum.intrinsic.t> operations, single-qubit Clifford operations, <xref:microsoft.quantum.intrinsic.cnot> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="56769-111">Użytkownicy mogą ustawić głębokość dla każdej operacji pierwotnej za pomocą `gateTimes` pola <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="56769-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="56769-112">Wywoływanie licznika głębokości</span><span class="sxs-lookup"><span data-stu-id="56769-112">Invoking the depth counter</span></span>

<span data-ttu-id="56769-113">Aby uruchomić symulator śledzenia Quantum z licznikiem głębokości, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić jego `UseDepthCounter` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru.</span><span class="sxs-lookup"><span data-stu-id="56769-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="56769-114">Korzystanie z licznika głębokości w programie hosta C#</span><span class="sxs-lookup"><span data-stu-id="56769-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="56769-115">Przykładowy kod w języku C#, który znajduje się w tej sekcji `T` , oblicza głębokość `CCNOT` operacji na podstawie następującego Q# przykładowego kodu:</span><span class="sxs-lookup"><span data-stu-id="56769-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="56769-116">Aby sprawdzić, czy `CCNOT` ma `T` głębokość **5** i `ApplySampleWithCCNOT` ma `T` głębokość **6**, użyj następującego kodu w języku C#:</span><span class="sxs-lookup"><span data-stu-id="56769-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="56769-117">Zostanie uruchomiona pierwsza część programu `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="56769-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="56769-118">Druga część używa [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metody do pobierania `T` głębokości `CCNOT` i `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="56769-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="56769-119">Na koniec można wyprowadzić wszystkie dane statystyczne zebrane przez licznik głębokości w formacie CSV przy użyciu następujących instrukcji:</span><span class="sxs-lookup"><span data-stu-id="56769-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="56769-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="56769-120">See also</span></span>

- <span data-ttu-id="56769-121">Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="56769-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="56769-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="56769-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="56769-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="56769-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="56769-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="56769-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>

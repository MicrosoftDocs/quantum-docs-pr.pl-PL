---
title: Licznik głębokości-Quantum Development Kit
description: Dowiedz się więcej o liczniku głębokości QDK firmy Microsoft, który używa symulatora śledzenia Quantum do zbierania informacji o głębokości każdej operacji wywoływanej w Q# programie.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9c3a772861582e5c49fe5ad27519c25a59d617b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859044"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="728b6-103">Symulator śledzenia Quantum: licznik głębokości</span><span class="sxs-lookup"><span data-stu-id="728b6-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="728b6-104">Licznik głębokości jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="728b6-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="728b6-105">Można jej użyć do zebrania liczb, które reprezentują dolną granicę głębokości każdej operacji wywołanej w programie Quantum.</span><span class="sxs-lookup"><span data-stu-id="728b6-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="728b6-106">Wartości głębokości</span><span class="sxs-lookup"><span data-stu-id="728b6-106">Depth values</span></span>

<span data-ttu-id="728b6-107">Domyślnie wszystkie operacje mają głębokość **0** z wyjątkiem `T` operacji, która ma głębokość **1**.</span><span class="sxs-lookup"><span data-stu-id="728b6-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="728b6-108">Oznacza to, że domyślnie `T` obliczana jest tylko głębokość operacji (co jest często pożądane).</span><span class="sxs-lookup"><span data-stu-id="728b6-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="728b6-109">Licznik głębokości agreguje i zbiera dane statystyczne na temat wszystkich krawędzi [grafu wywołania](https://en.wikipedia.org/wiki/Call_graph)operacji.</span><span class="sxs-lookup"><span data-stu-id="728b6-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="728b6-110">Wszystkie <xref:Microsoft.Quantum.Intrinsic> operacje są wyrażane w zakresie obrotów qubit, operacji <xref:Microsoft.Quantum.Intrinsic.T> , operacji qubit Clifford, <xref:Microsoft.Quantum.Intrinsic.CNOT> operacji i pomiarów wieloqubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="728b6-110">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, <xref:Microsoft.Quantum.Intrinsic.T> operations, single-qubit Clifford operations, <xref:Microsoft.Quantum.Intrinsic.CNOT> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="728b6-111">Użytkownicy mogą ustawić głębokość dla każdej operacji pierwotnej za pomocą `gateTimes` pola <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="728b6-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="728b6-112">Wywoływanie licznika głębokości</span><span class="sxs-lookup"><span data-stu-id="728b6-112">Invoking the depth counter</span></span>

<span data-ttu-id="728b6-113">Aby uruchomić symulator śledzenia Quantum z licznikiem głębokości, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić jego `UseDepthCounter` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru.</span><span class="sxs-lookup"><span data-stu-id="728b6-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="728b6-114">Korzystanie z licznika głębokości w programie hosta C#</span><span class="sxs-lookup"><span data-stu-id="728b6-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="728b6-115">Przykładowy kod w języku C#, który znajduje się w tej sekcji `T` , oblicza głębokość `CCNOT` operacji na podstawie następującego Q# przykładowego kodu:</span><span class="sxs-lookup"><span data-stu-id="728b6-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="728b6-116">Aby sprawdzić, czy `CCNOT` ma `T` głębokość **5** i `ApplySampleWithCCNOT` ma `T` głębokość **6**, użyj następującego kodu w języku C#:</span><span class="sxs-lookup"><span data-stu-id="728b6-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

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

<span data-ttu-id="728b6-117">Zostanie uruchomiona pierwsza część programu `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="728b6-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="728b6-118">Druga część używa [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metody do pobierania `T` głębokości `CCNOT` i `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="728b6-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="728b6-119">Na koniec można wyprowadzić wszystkie dane statystyczne zebrane przez licznik głębokości w formacie CSV przy użyciu następujących instrukcji:</span><span class="sxs-lookup"><span data-stu-id="728b6-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="728b6-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="728b6-120">See also</span></span>

- <span data-ttu-id="728b6-121">Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="728b6-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="728b6-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="728b6-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="728b6-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="728b6-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="728b6-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="728b6-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>

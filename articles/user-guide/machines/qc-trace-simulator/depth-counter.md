---
title: Licznik głębokości
description: Dowiedz się więcej o liczniku głębokości QDK firmy Microsoft, który gromadzi informacje o głębokości każdej operacji wywołanej w programie Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275626"
---
# <a name="depth-counter"></a><span data-ttu-id="175e6-103">Licznik głębokości</span><span class="sxs-lookup"><span data-stu-id="175e6-103">Depth Counter</span></span>

<span data-ttu-id="175e6-104">`Depth Counter`Jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum.</span><span class="sxs-lookup"><span data-stu-id="175e6-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="175e6-105">Służy do zbierania liczby głębokości każdej operacji wywołanej w programie Quantum.</span><span class="sxs-lookup"><span data-stu-id="175e6-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="175e6-106">Wszystkie operacje z <xref:microsoft.quantum.intrinsic> są wyrażane w odniesieniu do pojedynczych qubitych obrotów, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów wieloqubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="175e6-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="175e6-107">Użytkownicy mogą ustawić głębokość dla każdej operacji pierwotnej za pomocą `gateTimes` pola <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="175e6-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="175e6-108">Domyślnie wszystkie operacje mają głębię 0 z wyjątkiem bramy T, która ma głębokość 1.</span><span class="sxs-lookup"><span data-stu-id="175e6-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="175e6-109">Oznacza to, że domyślnie tylko głębokość T operacji jest obliczana (co jest często pożądane).</span><span class="sxs-lookup"><span data-stu-id="175e6-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="175e6-110">Zebrane dane statystyczne są agregowane na wszystkich krawędziach grafu wywołań operacji.</span><span class="sxs-lookup"><span data-stu-id="175e6-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="175e6-111">Teraz obliczą <xref:microsoft.quantum.intrinsic.t> głębokość <xref:microsoft.quantum.intrinsic.ccnot> operacji.</span><span class="sxs-lookup"><span data-stu-id="175e6-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="175e6-112">Będziemy używać następującego przykładowego kodu Q #:</span><span class="sxs-lookup"><span data-stu-id="175e6-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="175e6-113">Używanie licznika głębokości w programie w języku C#</span><span class="sxs-lookup"><span data-stu-id="175e6-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="175e6-114">Aby sprawdzić, czy `CCNOT` ma `T` głębokość 5 i `ApplySampleWithCCNOT` ma `T` głębokość 6, można użyć następującego kodu w języku C#:</span><span class="sxs-lookup"><span data-stu-id="175e6-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="175e6-115">Zostanie wykonana pierwsza część programu `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="175e6-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="175e6-116">W drugiej części używamy metody `QCTraceSimulator.GetMetric` do uzyskania `T` głębokości `CCNOT` i `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="175e6-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="175e6-117">Na koniec w celu wygenerowania wszystkich statystyk zebranych przez `Depth Counter` program w formacie CSV można użyć następujących instrukcji:</span><span class="sxs-lookup"><span data-stu-id="175e6-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="175e6-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="175e6-118">See also</span></span> ##

- <span data-ttu-id="175e6-119">Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.</span><span class="sxs-lookup"><span data-stu-id="175e6-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>

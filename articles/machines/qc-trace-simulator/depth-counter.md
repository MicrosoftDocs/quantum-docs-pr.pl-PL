---
title: Licznik głębokości | Symulator śledzenia komputerów Quantum | Microsoft Docs
description: Omówienie symulatora śledzenia komputera kwantowego
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 07f927c794e2c62e53e4e053b5bc683d24bbed8d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820474"
---
# <a name="depth-counter"></a><span data-ttu-id="ae6a5-103">Licznik głębokości</span><span class="sxs-lookup"><span data-stu-id="ae6a5-103">Depth Counter</span></span>

<span data-ttu-id="ae6a5-104">`Depth Counter` jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum.</span><span class="sxs-lookup"><span data-stu-id="ae6a5-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="ae6a5-105">Służy do zbierania liczby głębokości każdej operacji wywołanej w programie Quantum.</span><span class="sxs-lookup"><span data-stu-id="ae6a5-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="ae6a5-106">Wszystkie operacje z <xref:microsoft.quantum.intrinsic> są wyrażane w zakresie pojedynczych rotacji qubit, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów dla wieloqubit Pauli observables.</span><span class="sxs-lookup"><span data-stu-id="ae6a5-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="ae6a5-107">Użytkownicy mogą ustawić głębokość dla każdej operacji pierwotnej za pomocą pola `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span><span class="sxs-lookup"><span data-stu-id="ae6a5-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="ae6a5-108">Domyślnie wszystkie operacje mają głębię 0 z wyjątkiem bramy T, która ma głębokość 1.</span><span class="sxs-lookup"><span data-stu-id="ae6a5-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="ae6a5-109">Oznacza to, że domyślnie tylko głębokość T operacji jest obliczana (co jest często pożądane).</span><span class="sxs-lookup"><span data-stu-id="ae6a5-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="ae6a5-110">Zebrane dane statystyczne są agregowane na wszystkich krawędziach grafu wywołań operacji.</span><span class="sxs-lookup"><span data-stu-id="ae6a5-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="ae6a5-111">Teraz Oblicz <xref:microsoft.quantum.intrinsic.t> głębokość <xref:microsoft.quantum.intrinsic.ccnot> operacji.</span><span class="sxs-lookup"><span data-stu-id="ae6a5-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="ae6a5-112">Będziemy używać następującego przykładowego kodu Q #:</span><span class="sxs-lookup"><span data-stu-id="ae6a5-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="ae6a5-113">Korzystanie z licznika głębokości w C# ramach programu</span><span class="sxs-lookup"><span data-stu-id="ae6a5-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="ae6a5-114">Aby sprawdzić, czy `CCNOT` ma `T` głębokości 5 i `ApplySampleWithCCNOT` `T` głębokości 6 możemy użyć następującego C# kodu:</span><span class="sxs-lookup"><span data-stu-id="ae6a5-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

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

<span data-ttu-id="ae6a5-115">Pierwsza część programu jest wykonywana `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="ae6a5-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="ae6a5-116">W drugiej części używamy metody `QCTraceSimulator.GetMetric`, aby uzyskać `T` głębokość `CCNOT` i `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="ae6a5-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="ae6a5-117">Na koniec w celu wygenerowania wszystkich statystyk zbieranych przez `Depth Counter` w formacie CSV można użyć następujących instrukcji:</span><span class="sxs-lookup"><span data-stu-id="ae6a5-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="ae6a5-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ae6a5-118">See also</span></span> ##

- <span data-ttu-id="ae6a5-119">Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.</span><span class="sxs-lookup"><span data-stu-id="ae6a5-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>

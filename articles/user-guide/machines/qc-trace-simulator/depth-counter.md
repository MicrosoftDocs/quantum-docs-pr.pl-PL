---
title: Licznik głębokości
description: Dowiedz się więcej o liczniku głębokości QDK firmy Microsoft, który gromadzi informacje o głębokości każdej operacji wywołanej w programie Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 0029a00e6a3563dc542daeda2afa7cabf42441fb
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415270"
---
# <a name="depth-counter"></a>Licznik głębokości

`Depth Counter`Jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum.
Służy do zbierania liczb reprezentujących dolną granicę głębokości każdej operacji wywołanej w programie Quantum. Wszystkie operacje z <xref:microsoft.quantum.intrinsic> są wyrażane w odniesieniu do pojedynczych qubitych obrotów, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów wieloqubit Pauli observables. Użytkownicy mogą ustawić głębokość dla każdej operacji pierwotnej za pomocą `gateTimes` pola <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

Domyślnie wszystkie operacje mają głębię 0 z wyjątkiem bramy T, która ma głębokość 1. Oznacza to, że domyślnie tylko głębokość T operacji jest obliczana (co jest często pożądane). Zebrane dane statystyczne są agregowane na wszystkich krawędziach grafu wywołań operacji. 

Teraz obliczą <xref:microsoft.quantum.intrinsic.t> głębokość <xref:microsoft.quantum.intrinsic.ccnot> operacji. Będziemy używać następującego przykładowego kodu Q #:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Używanie licznika głębokości w programie w języku C#

Aby sprawdzić, czy `CCNOT` ma `T` głębokość 5 i `ApplySampleWithCCNOT` ma `T` głębokość 6, można użyć następującego kodu w języku C#:

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

Zostanie wykonana pierwsza część programu `ApplySampleWithCCNOT` . W drugiej części używamy metody `QCTraceSimulator.GetMetric` do uzyskania `T` głębokości `CCNOT` i `ApplySampleWithCCNOT` : 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Na koniec w celu wygenerowania wszystkich statystyk zebranych przez `Depth Counter` program w formacie CSV można użyć następujących instrukcji:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Zobacz też ##

- Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.

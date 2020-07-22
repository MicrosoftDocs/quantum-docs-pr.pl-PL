---
title: Licznik głębokości-Quantum Development Kit
description: 'Dowiedz się więcej o liczniku głębokości QDK firmy Microsoft, który używa symulatora śledzenia Quantum do zbierania informacji o głębokości każdej operacji wywołanej w programie Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 811e387fedf547d2681518ae0bb525c13dc84ff4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871131"
---
# <a name="quantum-trace-simulator-depth-counter"></a>Symulator śledzenia Quantum: licznik głębokości

Licznik głębokości jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit.
Można jej użyć do zebrania liczb, które reprezentują dolną granicę głębokości każdej operacji wywołanej w programie Quantum. 

## <a name="depth-values"></a>Wartości głębokości

Domyślnie wszystkie operacje mają głębokość **0** z wyjątkiem `T` operacji, która ma głębokość **1**. Oznacza to, że domyślnie `T` obliczana jest tylko głębokość operacji (co jest często pożądane). Licznik głębokości agreguje i zbiera dane statystyczne na temat wszystkich krawędzi [grafu wywołania](https://en.wikipedia.org/wiki/Call_graph)operacji.

Wszystkie <xref:microsoft.quantum.intrinsic> operacje są wyrażane w zakresie obrotów qubit, operacji <xref:microsoft.quantum.intrinsic.t> , operacji qubit Clifford, <xref:microsoft.quantum.intrinsic.cnot> operacji i pomiarów wieloqubit Pauli observables. Użytkownicy mogą ustawić głębokość dla każdej operacji pierwotnej za pomocą `gateTimes` pola <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

## <a name="invoking-the-depth-counter"></a>Wywoływanie licznika głębokości

Aby uruchomić symulator śledzenia Quantum z licznikiem głębokości, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić jego `UseDepthCounter` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>Korzystanie z licznika głębokości w programie hosta C#

Przykład w języku C# opisany w tej sekcji oblicza `T` głębokość `CCNOT` operacji w oparciu o następujący przykładowy kod Q #:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Aby sprawdzić, czy `CCNOT` ma `T` głębokość **5** i `ApplySampleWithCCNOT` ma `T` głębokość **6**, użyj następującego kodu w języku C#:

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

Zostanie uruchomiona pierwsza część programu `ApplySampleWithCCNOT` . Druga część używa [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metody do pobierania `T` głębokości `CCNOT` i `ApplySampleWithCCNOT` . 

Na koniec można wyprowadzić wszystkie dane statystyczne zebrane przez licznik głębokości w formacie CSV przy użyciu następujących instrukcji:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Zobacz także

- Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>Dokumentacja interfejsu API.

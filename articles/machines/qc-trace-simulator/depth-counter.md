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
# <a name="depth-counter"></a>Licznik głębokości

`Depth Counter` jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum.
Służy do zbierania liczby głębokości każdej operacji wywołanej w programie Quantum. Wszystkie operacje z <xref:microsoft.quantum.intrinsic> są wyrażane w zakresie pojedynczych rotacji qubit, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów dla wieloqubit Pauli observables. Użytkownicy mogą ustawić głębokość dla każdej operacji pierwotnej za pomocą pola `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.

Domyślnie wszystkie operacje mają głębię 0 z wyjątkiem bramy T, która ma głębokość 1. Oznacza to, że domyślnie tylko głębokość T operacji jest obliczana (co jest często pożądane). Zebrane dane statystyczne są agregowane na wszystkich krawędziach grafu wywołań operacji. 

Teraz Oblicz <xref:microsoft.quantum.intrinsic.t> głębokość <xref:microsoft.quantum.intrinsic.ccnot> operacji. Będziemy używać następującego przykładowego kodu Q #:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Korzystanie z licznika głębokości w C# ramach programu

Aby sprawdzić, czy `CCNOT` ma `T` głębokości 5 i `ApplySampleWithCCNOT` `T` głębokości 6 możemy użyć następującego C# kodu:

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

Pierwsza część programu jest wykonywana `ApplySampleWithCCNOT`. W drugiej części używamy metody `QCTraceSimulator.GetMetric`, aby uzyskać `T` głębokość `CCNOT` i `ApplySampleWithCCNOT`: 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Na koniec w celu wygenerowania wszystkich statystyk zbieranych przez `Depth Counter` w formacie CSV można użyć następujących instrukcji:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Zobacz także ##

- Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.

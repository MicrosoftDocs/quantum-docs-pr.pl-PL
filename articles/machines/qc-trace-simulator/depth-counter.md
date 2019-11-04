---
title: Licznik głębokości | Symulator śledzenia komputerów Quantum | Microsoft Docs
description: Omówienie symulatora śledzenia komputerów z interfejsem Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: f5fcaa64e91290d377eeba597df2e307e187277c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184903"
---
# <a name="depth-counter"></a>Licznik głębokości

`Depth Counter` jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum.
Służy do zbierania liczby głębokości każdej operacji wywołanej w programie Quantum. Wszystkie operacje z <xref:microsoft.quantum.intrinsic> są wyrażane w zakresie pojedynczych rotacji qubit, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów dla wieloqubit Pauli observables. Użytkownicy mogą ustawić głębokość dla każdej operacji pierwotnej za pomocą pola `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.

Domyślnie wszystkie operacje mają głębię 0 z wyjątkiem bramy T, która ma głębokość 1. Oznacza to, że domyślnie tylko głębokość T operacji jest obliczana (co jest często pożądane). Zebrane dane statystyczne są agregowane na wszystkich krawędziach grafu wywołań operacji. 

Teraz Oblicz <xref:microsoft.quantum.intrinsic.t> głębokość <xref:microsoft.quantum.intrinsic.ccnot> operacji. Będziemy używać następującego kodu sterownika Q #: 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Korzystanie z licznika głębokości w C# ramach programu

Aby sprawdzić, czy `CCNOT` ma `T` głębokości 5 i `CCNOTDriver` `T` głębokości 6 możemy użyć następującego C# kodu:

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

Pierwsza część programu jest wykonywana `CCNOTDriver`. W drugiej części używamy metody `QCTraceSimulator.GetMetric`, aby uzyskać `T` głębokość `CCNOT` i `CCNOTDriver`: 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

Na koniec w celu wygenerowania wszystkich statystyk zbieranych przez `Depth Counter` w formacie CSV można użyć następujących instrukcji:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Zobacz także ##

- Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.

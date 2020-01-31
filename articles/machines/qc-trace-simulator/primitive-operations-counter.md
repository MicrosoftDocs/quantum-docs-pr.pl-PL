---
title: Licznik operacji pierwotnych | Symulator śledzenia komputerów Quantum | Microsoft Docs
description: Omówienie symulatora śledzenia komputera kwantowego
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 1f554c0a1b92c8f6b59be3a9d9965e0e25bd074f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820423"
---
# <a name="primitive-operations-counter"></a>Licznik operacji pierwotnych  

`Primitive Operations Counter` jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum. Liczy liczbę wykonań pierwotnych używanych przez każdą operację wywoływaną w programie Quantum. Wszystkie operacje z `Microsoft.Quantum.Intrinsic` są wyrażane w zakresie pojedynczych rotacji qubit, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów dla wieloqubit Pauli observables. Zebrane dane statystyczne są agregowane na krawędziach grafu wywołań operacji. Poinformuj nas o liczbie bram `T` potrzebnych do zaimplementowania operacji `CCNOT`. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Korzystanie z licznika operacji pierwotnych w C# ramach programu

Aby sprawdzić, czy `CCNOT` rzeczywiście wymagają 7 bram `T` i że `ApplySampleWithCCNOT` wykonuje 8 bram `T`, możemy użyć następującego C# kodu:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Pierwsza część programu jest wykonywana `ApplySampleWithCCNOT`. W drugiej części używamy metody `QCTraceSimulator.GetMetric`, aby uzyskać liczbę bram T wykonywanych przez `ApplySampleWithCCNOT`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Gdy `GetMetric` jest wywoływana z dwoma parametrami typu, zwraca wartość metryki skojarzonej z daną krawędzią grafu wywołania. W naszym przykładzie operacja `Primitive.CCNOT` jest wywoływana w `ApplySampleWithCCNOT` i dlatego wykres wywołań zawiera `<Primitive.CCNOT, ApplySampleWithCCNOT>`krawędzi. 

Aby uzyskać liczbę używanych bram `CNOT`, można dodać następujący wiersz:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Na koniec w celu wygenerowania wszystkich statystyk zbieranych przez licznik bram w formacie CSV można użyć następujących instrukcji:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Zobacz także ##

- Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.

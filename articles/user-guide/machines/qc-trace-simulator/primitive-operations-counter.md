---
title: Licznik operacji pierwotnych
description: Dowiedz się więcej o liczniku operacji programu Microsoft QDKe pierwotne, który śledzi liczbę wykonań pierwotnych używanych przez operacje w programie Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275557"
---
# <a name="primitive-operations-counter"></a>Licznik operacji pierwotnych  

`Primitive Operations Counter`Jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)komputerów z systemem Quantum. Liczy liczbę wykonań pierwotnych używanych przez każdą operację wywoływaną w programie Quantum. Wszystkie operacje z `Microsoft.Quantum.Intrinsic` są wyrażane w odniesieniu do pojedynczych qubitych obrotów, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów wieloqubit Pauli observables. Zebrane dane statystyczne są agregowane na krawędziach grafu wywołań operacji. Pozwól nam teraz obliczyć liczbę `T` bram potrzebnych do zaimplementowania `CCNOT` operacji. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Korzystanie z licznika operacji pierwotnych w programie w języku C#

Aby sprawdzić, czy w `CCNOT` rzeczywistości wymagane `T` są 7 bram i które `ApplySampleWithCCNOT` wykonuje 8 `T` bram, możemy użyć następującego kodu w języku C#:

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

Zostanie wykonana pierwsza część programu `ApplySampleWithCCNOT` . W drugiej części używamy metody, `QCTraceSimulator.GetMetric` Aby uzyskać liczbę bram T wykonywanych przez `ApplySampleWithCCNOT` : 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Gdy `GetMetric` jest wywoływana z dwoma parametrami typu, zwraca wartość metryki skojarzonej z daną krawędzią grafu wywołania. W naszej przykładowej operacji `Primitive.CCNOT` jest wywoływana wewnątrz `ApplySampleWithCCNOT` i dlatego wykres wywołań zawiera krawędź `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Aby uzyskać liczbę `CNOT` używanych bram, można dodać następujący wiersz:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Na koniec w celu wygenerowania wszystkich statystyk zbieranych przez licznik bram w formacie CSV można użyć następujących instrukcji:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Zobacz też ##

- Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.

---
title: Licznik operacji pierwotnych-Quantum Development Kit
description: Dowiedz się więcej o liczniku operacji programu Microsoft QDKe podstawowe, który korzysta z symulatora śledzenia Quantum do śledzenia procesów pierwotnych używanych przez operacje w Q# programie.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 19ea3c1f5a91c00de4d3e435318bf4cf8cdd83be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858602"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>Symulator śledzenia Quantum: licznik operacji pierwotnych

Licznik operacji pierwotnej jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit. Liczy liczbę procesów pierwotnych używanych przez każdą operację wywoływaną w programie Quantum. 

Wszystkie <xref:Microsoft.Quantum.Intrinsic> operacje są wyrażane w odniesieniu do rotacji qubit, operacji T, operacji qubit Clifford, operacji CNOT i pomiarów wieloqubit Pauli observables. Licznik operacji pierwotnych agreguje i zbiera dane statystyczne na temat wszystkich krawędzi [grafu wywołania](https://en.wikipedia.org/wiki/Call_graph)operacji.

## <a name="invoking-the-primitive-operation-counter"></a>Wywoływanie licznika operacji pierwotnej

Aby uruchomić symulator śledzenia Quantum z licznikiem operacji pierwotnej, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UsePrimitiveOperationsCounter` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie za pomocą `QCTraceSimulatorConfiguration` jako parametru.

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>Używanie licznika operacji pierwotnej w programie hosta C#

Poniższy przykład kodu w języku C# jest częścią liczby <xref:Microsoft.Quantum.Intrinsic.T> operacji potrzebnych do zaimplementowania <xref:Microsoft.Quantum.Intrinsic.CCNOT> operacji w oparciu o następujący Q# przykładowy kod:

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Aby sprawdzić, czy program `CCNOT` wymaga siedmiu `T` operacji `ApplySampleWithCCNOT` , które uruchamiają osiem `T` operacji, użyj następującego kodu w języku C#:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Zostanie uruchomiona pierwsza część programu `ApplySampleWithCCNOT` . Druga część używa [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metody do pobierania liczby `T` operacji wykonywanych przez `ApplySampleWithCCNOT` : 

W przypadku wywołania `GetMetric` z dwoma parametrami typu zwraca wartość metryki skojarzonej z daną krawędzią grafu wywołania. W poprzednim przykładzie program wywołuje `Primitive.CCNOT` operację w ramach `ApplySampleWithCCNOT` i dlatego wykres wywołań zawiera krawędź `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Aby pobrać liczbę `CNOT` używanych operacji, Dodaj następujący wiersz:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Na koniec można wyprowadzić wszystkie dane statystyczne zebrane przez licznik operacji pierwotnych w formacie CSV, korzystając z następujących elementów:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Zobacz także

- Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>Dokumentacja interfejsu API.
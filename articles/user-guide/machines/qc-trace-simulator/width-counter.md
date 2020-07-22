---
title: Counter Width-Quantum Development Kit
description: 'Dowiedz się więcej o liczniku szerokości QDK firmy Microsoft, który używa symulatora śledzenia Quantum, aby policzyć liczbę qubits przydzieloną i zaciągniętych przez operacje w programie Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: af8609dc5c05f7a19b8d21755281427feb29b84c
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871524"
---
# <a name="quantum-trace-simulator-width-counter"></a>Symulator śledzenia Quantum: szerokość licznika

Licznik width jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit. Można jej użyć do zliczenia liczby qubits przydzielone i zapożyczone przez każdą operację w programie Q #. Niektóre operacje pierwotne mogą przydzielić dodatkowe qubits, na przykład pomnóż `X` operacje kontrolowane lub `T` operacje kontrolowane.

## <a name="invoking-the-width-counter"></a>Wywoływanie licznika szerokości

Aby uruchomić symulator śledzenia Quantum z licznikiem szerokości, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UseWidthCounter` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie przy użyciu `QCTraceSimulatorConfiguration` jako parametru. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>Używanie licznika Width w programie hosta C#

W poniższym przykładzie w języku C# jest obliczana liczba dodatkowych qubits przyznanych przez implementację <xref:microsoft.quantum.intrinsic.x> operacji mnożenia, na podstawie następującego przykładowego kodu Q #:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

Operacja mnożenia z mnożeniem <xref:microsoft.quantum.intrinsic.x> działa na ogół pięciu qubits, przydziela dwa [pomocnicze qubits](xref:microsoft.quantum.glossary#ancilla)i ma szerokość wejściową **5**. Aby sprawdzić liczbę liczników, użyj następującego programu w języku C#:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

W pierwszej części programu jest uruchamiana `ApplyMultiControlledX` operacja. Druga część używa [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) metody do pobierania liczby przydzielonej qubits oraz liczby qubits, które `Controlled X` operacja otrzymała jako dane wejściowe. 

Na koniec można wyprowadzić wszystkie dane statystyczne zebrane przez licznik szerokość w formacie CSV, korzystając z następujących informacji:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Zobacz także

- Omówienie zestawu Quantum Development Kit [Quantum Trace symulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>Dokumentacja interfejsu API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>Dokumentacja interfejsu API.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>Dokumentacja interfejsu API.

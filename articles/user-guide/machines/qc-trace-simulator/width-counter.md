---
title: Counter Width-Quantum Development Kit
description: Dowiedz się więcej o liczniku szerokości QDK firmy Microsoft, który używa symulatora śledzenia Quantum do policzania liczby qubits przydzielonej i zapożyczonej przez operacje w Q# programie.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: e9a526ee1440544aace922bd83c6ea39cb83c1ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858577"
---
# <a name="quantum-trace-simulator-width-counter"></a>Symulator śledzenia Quantum: szerokość licznika

Licznik width jest częścią [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro)zestawu Quantum Development Kit. Można jej użyć do zliczenia liczby qubits przydzielone i zapożyczone przez poszczególne operacje w Q# programie. Niektóre operacje pierwotne mogą przydzielić dodatkowe qubits, na przykład pomnóż `X` operacje kontrolowane lub `T` operacje kontrolowane.

## <a name="invoking-the-width-counter"></a>Wywoływanie licznika szerokości

Aby uruchomić symulator śledzenia Quantum z licznikiem szerokości, należy utworzyć <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> wystąpienie, ustawić `UseWidthCounter` Właściwość na **true**, a następnie utworzyć nowe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> wystąpienie przy użyciu `QCTraceSimulatorConfiguration` jako parametru. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>Używanie licznika Width w programie hosta C#

W poniższym przykładzie w języku C# jest obliczana liczba dodatkowych qubits przyznanych przez implementację <xref:Microsoft.Quantum.Intrinsic.X> operacji mnożenia, na podstawie następującego Q# przykładowego kodu:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

Operacja mnożenia z mnożeniem <xref:Microsoft.Quantum.Intrinsic.X> działa na ogół pięciu qubits, przydziela dwa [pomocnicze qubits](xref:microsoft.quantum.glossary#ancilla)i ma szerokość wejściową **5**. Aby sprawdzić liczbę liczników, użyj następującego programu w języku C#:

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

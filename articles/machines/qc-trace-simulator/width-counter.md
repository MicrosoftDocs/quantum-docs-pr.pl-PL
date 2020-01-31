---
title: Licznik szerokości | Symulator śledzenia komputerów Quantum | Microsoft Docs
description: Omówienie symulatora śledzenia komputera kwantowego
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: 9c3601e74eec17bd6b463e90f8f3085c959d6f95
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820372"
---
# <a name="width-counter"></a>Licznik szerokości

`Width Counter` liczy liczbę qubits przydzielone i pożyczone przez każdą operację.
Wszystkie operacje z przestrzeni nazw `Microsoft.Quantum.Intrinsic` są wyrażane w zakresie pojedynczych rotacji qubit, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów dla wieloqubit Pauli observables. Niektóre operacje pierwotne mogą przydzielić dodatkowe qubits. Na przykład pomnóż kontrolowane bramy `X` lub kontrolowane `T` bramy. Poinformuj nas o liczbie dodatkowych qubits przyznanych przez implementację pomnożenia `X` bramę:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Używanie licznika szerokości w ramach C# programu

Mnożenie kontrolowane `X` działające na ogół 5 qubits przydzieli 2 dodatkowe qubits, a Szerokość wejściowa będzie wynosić 5. Aby sprawdzić, czy tak jest, można użyć następującego C# programu:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
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

Pierwsza część programu jest wykonywana `ApplyMultiControlledX`. W drugiej części używamy metody `QCTraceSimulator.GetMetric`, aby uzyskać liczbę przydzieloną qubits oraz liczbę qubits, które są `X` kontrolowane jako dane wejściowe. 

Na koniec w celu wygenerowania wszystkich statystyk zbieranych przez licznik szerokości w formacie CSV można użyć następujących instrukcji:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Zobacz także ##

- Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.

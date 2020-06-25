---
title: Licznik szerokości
description: Dowiedz się więcej o liczniku szerokości QDK firmy Microsoft, który zlicza qubits przydzielone i pożyczone przez poszczególne operacje w programie Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275562"
---
# <a name="width-counter"></a>Licznik szerokości

`Width Counter`Liczy liczbę qubits przydzielone i pożyczone przez każdą operację.
Wszystkie operacje z `Microsoft.Quantum.Intrinsic` przestrzeni nazw są wyrażane w zakresie pojedynczych qubitych rotacji, bram T, pojedynczej bramy Clifford qubit, bram CNOT i pomiarów dla wieloqubit Pauli observables. Niektóre operacje pierwotne mogą przydzielić dodatkowe qubits. Na przykład pomnóż kontrolowane `X` bramy lub bramy sterowane `T` . Poinformuj nas o liczbie dodatkowych qubits przyznanych przez implementację wielokrotnie kontrolowanej `X` bramy:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Używanie licznika szerokości w programie w języku C#

Mnożenie kontroli `X` działające na ogół 5 qubits przydzieli 2 dodatkowe qubits, a Szerokość wejściowa to 5. Aby sprawdzić, czy tak jest, można użyć następującego programu w języku C#:

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

Zostanie wykonana pierwsza część programu `ApplyMultiControlledX` . W drugiej części użyjemy metody, `QCTraceSimulator.GetMetric` Aby uzyskać liczbę przydzieloną qubits oraz liczbę qubits, które zostały kontrolowane `X` jako dane wejściowe. 

Na koniec w celu wygenerowania wszystkich statystyk zbieranych przez licznik szerokości w formacie CSV można użyć następujących instrukcji:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Zobacz też ##

- Omówienie [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro) komputerów z interfejsem Quantum.

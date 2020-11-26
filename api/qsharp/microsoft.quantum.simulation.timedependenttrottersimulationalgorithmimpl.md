---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: f4f8a9265dc25305819da5ae1002f02b7efd1952
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203454"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a>TimeDependentTrotterSimulationAlgorithmImpl, operacja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementacja wielu kroków Trotter do przybliżonego operatora jednostki, który rozwiązuje zależne od czasu równanie Schrödinger.

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Czas trwania symulowanego czasu rozwoju w jednym kroku Trotter.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Kolejność integratora Trotter. Ta wartość musi być równa 1 lub parzysta.


### <a name="maxtime--double"></a>maxTime: [Double](xref:microsoft.quantum.lang-ref.double)

Łączny czas trwania symulacji $t $.


### <a name="evolutionschedule--evolutionschedule"></a>evolutionSchedule: [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)

Pełny opis systemu zależnego od czasu, który ma zostać symulowany.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits działały na podstawie symulacji.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


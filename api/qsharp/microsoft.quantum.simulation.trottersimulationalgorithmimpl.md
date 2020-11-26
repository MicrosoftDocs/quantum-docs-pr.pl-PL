---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 5b796245e2a4434228260a229cb61be66f3e38d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203404"
---
# <a name="trottersimulationalgorithmimpl-operation"></a>TrotterSimulationAlgorithmImpl, operacja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wykonuje powtórzone wywołania `TrotterStep` , aby przybliżyć czas trwania operacji (_-iHt_).

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Czas trwania symulowanego czasu rozwoju w jednym kroku Trotter.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Kolejność integratora Trotter. Ta wartość musi być równa 1 lub parzysta.


### <a name="maxtime--double"></a>maxTime: [Double](xref:microsoft.quantum.lang-ref.double)

Łączny czas trwania symulacji $t $.


### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Pełny opis systemu, który ma zostać symulowany.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits działały na podstawie symulacji.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


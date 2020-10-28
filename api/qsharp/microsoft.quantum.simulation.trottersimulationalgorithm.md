---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719865"
---
# <a name="trottersimulationalgorithm-function"></a>TrotterSimulationAlgorithm, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


`SimulationAlgorithm` Funkcja, która korzysta z dekompozycji Trotter – Suzuki, aby przybliżyć czas trwania operacji _(-iHt)_ .

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a>Dane wejściowe

### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Czas trwania symulowanego czasu rozwoju w jednym kroku Trotter.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Kolejność integratora Trotter. Ta wartość musi być równa 1 lub parzysta.



## <a name="output--simulationalgorithm"></a>Wynik: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)

`SimulationAlgorithm`Typ.
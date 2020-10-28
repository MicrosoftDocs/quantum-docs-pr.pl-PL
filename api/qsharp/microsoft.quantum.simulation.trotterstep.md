---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725353"
---
# <a name="trotterstep-function"></a>TrotterStep, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Implementuje jednokrotne przechodzenie czasowe przez system opisany w `EvolutionGenerator` Trotter – Suzuki dekompozycji.

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Pełny opis systemu, który ma zostać symulowany.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Kolejność integratora Trotter. Ta wartość musi być równa 1 lub parzysta.


### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Czas trwania symulowanego czasu rozwoju w jednym kroku Trotter.



## <a name="output--qubit--unit-adj--ctl"></a>Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Operacja jednostkowa, która przybliża jeden etap ewolucji czasu trwania `trotterStepSize` .

## <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat dekompozycji usługi Trotter – Suzuki, zobacz [kompozycja uporządkowana według czasu](/quantum/libraries/control-flow#time-ordered-composition).
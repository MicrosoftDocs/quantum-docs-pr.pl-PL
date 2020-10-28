---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ab964d2c43a13a5daf64aefdeccd1c26cd371ff4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722432"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Zwraca tablicę obrotów z pojedynczą qubitą wzdłuż danej osi, sparametryzowane według odrębnych parametrów modelu.

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Dane wejściowe

### <a name="idxsqubits--int"></a>idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]

Indeksy dla qubits mają być używane jako elementy docelowe dla każdego obrotu.


### <a name="axis--pauli"></a>oś: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Oś obrotu dla każdego obrotu w danej warstwie.



## <a name="output--controlledrotation"></a>Wynik: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Tablica kontrolowanych obrotów o podaną oś, jedna na każdej z `nQubits` qubits.
---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5421765e36ef3e8e744e118206dafcb2bb582cc2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211937"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Zwraca tablicę z pojedynczo kontrolowanymi obrotami wzdłuż danej osi, ułożone cyklicznie w rejestrze qubits i sparametryzowane według odrębnych parametrów modelu.

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Dane wejściowe

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits działań na podstawie danej warstwy.


### <a name="axis--pauli"></a>oś: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Oś obrotu dla każdego obrotu w danej warstwie.


### <a name="stride--int"></a>Krok: [int](xref:microsoft.quantum.lang-ref.int)

Rozdzielenie między elementami docelowymi a kontrolkami kontroli dla każdego obrotu.



## <a name="output--controlledrotation"></a>Wynik: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Tablica przekreśleń z dwoma qubitami, które są rozmieszczone cyklicznie przez rejestr `nQubits` qubits.
---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204542"
---
# <a name="weightonepaulis-function"></a>WeightOnePaulis, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca tablicę wszystkich operatorów Pauli wagi 1 w danej liczbie qubits.

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a>Dane wejściowe

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits, na których zdefiniowano zwrócone operatory Pauli.



## <a name="output--pauli"></a>Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tablica operatorów wieloqubitowych Pauli, z których każdy jest reprezentowany jako tablica o długości `nQubits` .
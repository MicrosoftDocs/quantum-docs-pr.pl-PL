---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 8aeea795ef5409339e8a1b39c3ffcfaf29d675b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851969"
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
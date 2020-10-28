---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715834"
---
# <a name="multiplexoperations-operation"></a>MultiplexOperations, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje tablicę operacji sterowaną przez tablicę liczb Stanów.

Oznacza to, że jest stosowana operacja jednostkowa o pomnożenia $U $, która stosuje $V jednostkowe _j $, gdy jest to kontrolowane przez $n $-qubit Number State $ \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="unitaries--t--unit-adj--ctl"></a>unitaries: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL []

Tablica operacji jednostkowych do $2 ^ n $. Operacja $j $ th jest indeksowana przez stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.


### <a name="index--littleendian"></a>indeks: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.


### <a name="target--t"></a>element docelowy: 'T

Ogólny rejestr qubit, który $V _j $ działa.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

`coefficients` zostaną uzupełnione elementami tożsamości, jeśli określono mniej niż $2 ^ n $. Ta implementacja używa qubits pomocniczego $n-$1.

## <a name="references"></a>Dokumentacja

- W kierunku pierwszej symulacji Quantum przy użyciu Quantum przyspieszenie Andrew M. Childs, Dmitri Maslov, Yunseong, Neila J. Ross, Juan Su https://arxiv.org/abs/1711.10980
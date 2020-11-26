---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funkcja _SwapOrderToPermuteArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221712"
---
# <a name="_swapordertopermutearray-function"></a>Funkcja _SwapOrderToPermuteArray

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca elementy zamówienia w tablicy, które muszą zostać zamienione w celu utworzenia uporządkowanej tablicy.
Przyjęto zamianę na miejsce.

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>Dane wejściowe

### <a name="neworder--int"></a>newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]

Tablica z Permutacją indeksów nowej tablicy. Powinny być $n elementy $, każda z nich jest unikatową liczbą całkowitą z zakresu od $0 do $n – $1.



## <a name="output--intint"></a>Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Krotka reprezentuje dwa indeksy, które mają zostać zamienione. Zamiany zaczynają się na najniższym indeksie.

## <a name="remarks"></a>Uwagi

## <a name="psuedocode"></a>Psuedocode

for (indeks in 0.. length (newOrder)-1) {while newOrder [index]! = index {Switch newOrder [index] with newOrder [newOrder [indeks]]}}
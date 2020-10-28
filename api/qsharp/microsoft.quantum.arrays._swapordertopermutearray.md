---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funkcja _SwapOrderToPermuteArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719493"
---
# <a name="_swapordertopermutearray-function"></a>Funkcja _SwapOrderToPermuteArray

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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
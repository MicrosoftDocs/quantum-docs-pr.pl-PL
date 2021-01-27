---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funkcja _SwapOrderToPermuteArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846288"
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

## <a name="example"></a>Przykład

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a>Uwagi

## <a name="psuedocode"></a>Psuedocode

for (indeks in 0.. length (newOrder)-1) {while newOrder [index]! = index {Switch newOrder [index] with newOrder [newOrder [indeks]]}}
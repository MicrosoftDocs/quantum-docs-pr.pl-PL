---
uid: Microsoft.Quantum.Arrays.Count
title: Count — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 408a4a42dda6a4827db6d5865e2b4b8a8df5b37a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719400"
---
# <a name="count-function"></a>Count — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, zwraca liczbę elementów tablicy, która składa się z tych elementów, które spełniają predykat.

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="predicate--t---bool"></a>predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja z `'T` do wartości logicznej, która jest używana do filtrowania elementów.


### <a name="array--t"></a>Tablica: t []

Tablica elementów `'T` .



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Liczba elementów w `array` , które spełniają predykat.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ `array` elementów.

## <a name="remarks"></a>Uwagi

Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i predykat `'T -> Bool` możemy filtrować elementy.
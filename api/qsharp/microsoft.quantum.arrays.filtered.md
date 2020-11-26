---
uid: Microsoft.Quantum.Arrays.Filtered
title: Funkcja filtrowana
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: fa8600f4d773daf6eabf8b9961ab46961155d1fd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221270"
---
# <a name="filtered-function"></a>Funkcja filtrowana

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, zwraca tablicę, która składa się z tych elementów, które spełniają predykat.

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="predicate--t---bool"></a>predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja z `'T` do wartości logicznej, która jest używana do filtrowania elementów.


### <a name="array--t"></a>Tablica: t []

Tablica elementów `'T` .



## <a name="output--t"></a>Wynik: t []

Tablica `'T[]` elementów, które spełniają predykat.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ `array` elementów.

## <a name="remarks"></a>Uwagi

Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i predykat `'T -> Bool` możemy filtrować elementy.
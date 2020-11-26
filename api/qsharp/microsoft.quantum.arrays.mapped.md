---
uid: Microsoft.Quantum.Arrays.Mapped
title: Mapowana funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220743"
---
# <a name="mapped-function"></a>Mapowana funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana tablica i funkcja, która jest zdefiniowana dla elementów tablicy, zwraca nową tablicę, która składa się z obrazów oryginalnej tablicy w funkcji.

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Dane wejściowe

### <a name="mapper--t---u"></a>Maper: brak > ' U

Funkcja z `'T` do `'U` , która jest używana do mapowania elementów.


### <a name="array--t"></a>Tablica: t []

Tablica elementów `'T` .



## <a name="output--u"></a>Wynik: "U []

Tablica `'U[]` elementów, które są mapowane przez `mapper` funkcję.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ `array` elementów.
### <a name="u"></a>' U

Typ wyniku `mapper` funkcji.

## <a name="remarks"></a>Uwagi

Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i funkcję, `mapper: 'T -> 'U` możemy zmapować elementy tablicy i utworzyć nową tablicę typu `'U[]` .
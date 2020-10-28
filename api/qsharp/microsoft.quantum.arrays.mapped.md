---
uid: Microsoft.Quantum.Arrays.Mapped
title: Mapowana funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719076"
---
# <a name="mapped-function"></a>Mapowana funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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
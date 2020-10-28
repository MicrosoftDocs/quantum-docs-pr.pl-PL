---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719040"
---
# <a name="mappedoverrange-function"></a>MappedOverRange, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Uwzględniając zakres i funkcję, która przyjmuje liczbę całkowitą jako dane wejściowe, zwraca nową tablicę, która składa się z obrazów wartości zakresu w ramach funkcji.

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="mapper--int---t"></a>Maper: [int](xref:microsoft.quantum.lang-ref.int) -> 't

Funkcja z `Int` do `'T` , która jest używana do mapowania wartości zakresu.


### <a name="range--range"></a>zakres: [zakres](xref:microsoft.quantum.lang-ref.range)

Zakres liczb całkowitych.



## <a name="output--t"></a>Wynik: t []

Tablica `'T[]` elementów, które są mapowane przez `mapper` funkcję.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wyniku `mapper` funkcji.

## <a name="remarks"></a>Uwagi

Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy funkcję, `mapper: Int -> 'T` możemy zmapować wartości zakresu i utworzyć tablicę typu `'T[]` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. zmapowane](xref:Microsoft.Quantum.Arrays.Mapped)
---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220692"
---
# <a name="mappedoverrange-function"></a>MappedOverRange, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
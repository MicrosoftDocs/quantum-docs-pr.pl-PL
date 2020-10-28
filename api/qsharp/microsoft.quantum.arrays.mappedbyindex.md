---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719052"
---
# <a name="mappedbyindex-function"></a>MappedByIndex, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Dana tablica i funkcja, która jest zdefiniowana dla indeksowanych elementów tablicy, zwraca nową tablicę, która składa się z obrazów oryginalnej tablicy w funkcji.

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Dane wejściowe

### <a name="mapper--intt---u"></a>Maper: ([int](xref:microsoft.quantum.lang-ref.int), t)-> ' U

Funkcja z `(Int, 'T)` do `'U` , która jest używana do mapowania elementów i ich indeksów.


### <a name="array--t"></a>Tablica: t []

Tablica elementów `'T` .



## <a name="output--u"></a>Wynik: "U []

Tablica `'U[]` elementów, które są mapowane przez `mapper` funkcję.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ `array` elementów.
### <a name="u"></a>' U

Typ wyniku `mapper` funkcji.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. zmapowane](xref:Microsoft.Quantum.Arrays.Mapped)
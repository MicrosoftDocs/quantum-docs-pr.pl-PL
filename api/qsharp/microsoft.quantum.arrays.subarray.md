---
uid: Microsoft.Quantum.Arrays.Subarray
title: Funkcja subarray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718845"
---
# <a name="subarray-function"></a>Funkcja subarray

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Pobiera tablicę i listę lokalizacji i tworzy nową tablicę utworzoną z elementów oryginalnej tablicy, które pasują do określonych lokalizacji.

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="indices--int"></a>indeksy: [int](xref:microsoft.quantum.lang-ref.int)[]

Lista liczb całkowitych, która jest używana do definiowania podtablicy.


### <a name="array--t"></a>Tablica: t []

Tablica elementów `'T` .



## <a name="output--t"></a>Wynik: t []

Tablica `out` elementów, których indeksy odpowiadają podtablicy, takiej jak `out[idx] == array[indices[idx]]` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ `array` elementów.

## <a name="remarks"></a>Uwagi

Funkcja jest definiowana dla typów ogólnych, tzn., gdy mamy tablicę `'T[]` i listę lokalizacji `Int[]` definiujących podtablicę.
Konstrukcja podtablicy jest oparta na generowaniu nowej, głębokiej kopii danej tablicy, w przeciwieństwie do obsługi odwołań.

Jeśli `Length(indices) < Length(array)` Ta funkcja zwróci podzestaw elementu `array` . Z drugiej strony, jeśli `indices` zawiera powtarzające się elementy, odpowiednie elementy `array` są również powtarzane.
Jeśli `indices` i `array` ma tę samą długość, ta funkcja zapewnia permutacje `array` .
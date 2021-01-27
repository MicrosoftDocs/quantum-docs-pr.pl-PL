---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848637"
---
# <a name="flatmapped-function"></a>FlatMapped, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Podaną tablicą i funkcją, która mapuje element tablicy na część tablicy wyjściowej, zwraca tablice wyjściowe połączone dla każdego elementu tablicy.

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>Dane wejściowe

### <a name="mapper--tinput---toutput"></a>Maper: "TInput->" TOutput []

Funkcja z `'TInput` do `'TOutput[]` , która jest używana do mapowania elementów tablicy.


### <a name="array--tinput"></a>Array: "TInput []

Tablica elementów.



## <a name="output--toutput"></a>Dane wyjściowe: "TOutput []

Tablica, `'TOutput[]` która jest połączeniem wszystkich tablic generowanych przez funkcję mapowania.

## <a name="type-parameters"></a>Parametry typu

### <a name="tinput"></a>'TInput

Typ `array` elementów.
### <a name="toutput"></a>'TOutput

`mapper`Funkcja zwraca tablice tego typu.

## <a name="example"></a>Przykład

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```
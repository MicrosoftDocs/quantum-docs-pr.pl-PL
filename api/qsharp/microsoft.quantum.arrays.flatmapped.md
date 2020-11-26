---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: e851e8503b3afcb4572f09fe39079247518c22c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221253"
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
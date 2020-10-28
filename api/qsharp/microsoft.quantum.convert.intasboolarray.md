---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713454"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Package [](https://nuget.org/packages/)


Tworzy binarną reprezentację dodatniej liczby całkowitej przy użyciu reprezentacji little-endian dla zwróconej tablicy.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Dane wejściowe

### <a name="number--int"></a>Liczba: [int](xref:microsoft.quantum.lang-ref.int)

Dodatnia liczba całkowita, która ma zostać przekonwertowana na tablicę wartości logicznych.


### <a name="bits--int"></a>bity: [int](xref:microsoft.quantum.lang-ref.int)

Liczba bitów w reprezentacji binarnej `number` .



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tablica wartości logicznych reprezentujących `number` .

## <a name="remarks"></a>Uwagi

Wartość wejściowa `bits` musi należeć do zakresu od 0 do 63.
Wartość wejściowa `number` musi należeć do zakresu od 0 do $2 ^ {\texttt{BITS}}-$1.
---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224347"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
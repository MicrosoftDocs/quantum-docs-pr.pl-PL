---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833309"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tworzy binarną reprezentację nieujemnej liczby całkowitej przy użyciu reprezentacji little-endian dla zwróconej tablicy.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Dane wejściowe

### <a name="number--int"></a>Liczba: [int](xref:microsoft.quantum.lang-ref.int)

Nieujemna liczba całkowita do przekonwertowania na tablicę wartości logicznych.


### <a name="bits--int"></a>bity: [int](xref:microsoft.quantum.lang-ref.int)

Liczba bitów w reprezentacji binarnej `number` .



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tablica wartości logicznych reprezentujących `number` .

## <a name="remarks"></a>Uwagi

Wartość wejściowa `bits` musi należeć do zakresu od 0 do 63.
Wartość wejściowa `number` musi należeć do zakresu od 0 do $2 ^ {\texttt{BITS}}-$1.
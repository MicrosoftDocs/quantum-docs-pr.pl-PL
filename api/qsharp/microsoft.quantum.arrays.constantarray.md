---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210067"
---
# <a name="constantarray-function"></a>ConstantArray, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tworzy tablicę o podaną długość ze wszystkimi elementami równymi podaną wartością.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="length--int"></a>Długość: [int](xref:microsoft.quantum.lang-ref.int)

Długość nowej tablicy.


### <a name="value--t"></a>wartość: 'T

Wartość każdego elementu nowej tablicy.



## <a name="output--t"></a>Wynik: t []

Nowa tablica o długości `length` , taka jak każdy element to `value` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C


---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719412"
---
# <a name="constantarray-function"></a>ConstantArray, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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


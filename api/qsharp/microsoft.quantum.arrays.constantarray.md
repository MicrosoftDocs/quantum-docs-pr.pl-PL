---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846220"
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



## <a name="example"></a>Przykład

Poniższy kod tworzy tablicę trzech wartości logicznych, z których każda jest równa `true` :

```qsharp
let array = ConstantArray(3, true);
```
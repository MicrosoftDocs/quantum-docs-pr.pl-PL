---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709982"
---
# <a name="greaterthani-function"></a>GreaterThanI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package [](https://nuget.org/packages/)


Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa niż inna liczba.

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--int"></a>Odp.: [int](xref:microsoft.quantum.lang-ref.int)

Pierwsza wartość do porównania.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Druga wartość do porównania.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy `a` jest ściśle większa niż `b` .

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```
---
uid: Microsoft.Quantum.Logical.EqualI
title: EqualI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 6b805e76217e033cb0135cf85bd8f37a3eb8636a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710052"
---
# <a name="equali-function"></a>EqualI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package [](https://nuget.org/packages/)


Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--int"></a>Odp.: [int](xref:microsoft.quantum.lang-ref.int)

Pierwsza wartość do porównania.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Druga wartość do porównania.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy `a` jest równa `b` .

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```
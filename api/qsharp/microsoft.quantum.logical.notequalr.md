---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197198"
---
# <a name="notequalr-function"></a>NotEqualR, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--__invalidresult__"></a>Odp. __: <Result> nieprawidłowe__

Pierwsza wartość do porównania.


### <a name="b--__invalidresult__"></a>b: __nieprawidłowe <Result>__

Druga wartość do porównania.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy `a` nie jest równa `b` .

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```
---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709795"
---
# <a name="notequalr-function"></a>NotEqualR, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package [](https://nuget.org/packages/)


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
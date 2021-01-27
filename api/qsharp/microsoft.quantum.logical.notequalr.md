---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848497"
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

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```
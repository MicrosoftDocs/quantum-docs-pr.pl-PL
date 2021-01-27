---
uid: Microsoft.Quantum.Logical.EqualR
title: Funkcja równości
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815971"
---
# <a name="equalr-function"></a>Funkcja równości

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--__invalidresult__"></a>Odp. __: <Result> nieprawidłowe__

Pierwsza wartość do porównania.


### <a name="b--__invalidresult__"></a>b: __nieprawidłowe <Result>__

Druga wartość do porównania.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy `a` jest równa `b` .

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```
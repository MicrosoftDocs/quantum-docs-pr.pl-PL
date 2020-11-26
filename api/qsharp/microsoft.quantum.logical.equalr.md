---
uid: Microsoft.Quantum.Logical.EqualR
title: Funkcja równości
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198010"
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

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```
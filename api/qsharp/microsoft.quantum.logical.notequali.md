---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814501"
---
# <a name="notequali-function"></a>NotEqualI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--int"></a>Odp.: [int](xref:microsoft.quantum.lang-ref.int)

Pierwsza wartość do porównania.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Druga wartość do porównania.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy `a` nie jest równa `b` .

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```
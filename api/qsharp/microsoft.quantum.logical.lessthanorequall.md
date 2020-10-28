---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 333b76fc4885104e107dd25003a4e0dd5a9dd4af
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709921"
---
# <a name="lessthanorequall-function"></a>LessThanOrEqualL, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package [](https://nuget.org/packages/)


Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza lub równa innej liczbie.

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--bigint"></a>Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Pierwsza wartość do porównania.


### <a name="b--bigint"></a>b: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Druga wartość do porównania.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy `a` jest mniejsza lub równa `b` .

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```
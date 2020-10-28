---
uid: Microsoft.Quantum.Logical.Or
title: Or — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719976"
---
# <a name="or-function"></a>Or — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package [](https://nuget.org/packages/)


Zwraca wartość logiczną, która powoduje odłączenie dwóch wartości.

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--bool"></a>Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)

Pierwsza wartość do uwzględnienia.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Druga wartość do uwzględnienia.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy `a` lub `b` są `true` .

## <a name="remarks"></a>Uwagi

W przeciwieństwie do `or` operatora, ta funkcja nie jest krótka obwód, tak że oba dane wejściowe są w pełni oceniane.

W przypadku zachowania do krótkiego obwodu następujące elementy są równoważne:

```Q#
let x = a or b;
let x = Or(a, b);
```
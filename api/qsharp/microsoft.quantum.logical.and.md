---
uid: Microsoft.Quantum.Logical.And
title: And — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720801"
---
# <a name="and-function"></a>And — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package [](https://nuget.org/packages/)


Zwraca wartość logiczną koniunkcji dwóch wartości.

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--bool"></a>Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)

Pierwsza wartość do uwzględnienia.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Druga wartość do uwzględnienia.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy `a` , gdy i `b` `true` .

## <a name="remarks"></a>Uwagi

W przeciwieństwie do `and` operatora, ta funkcja nie jest krótka obwód, tak że oba dane wejściowe są w pełni oceniane.

W przypadku zachowania do krótkiego obwodu następujące elementy są równoważne:

```Q#
let x = a and b;
let x = And(a, b);
```
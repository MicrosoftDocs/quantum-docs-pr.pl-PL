---
uid: Microsoft.Quantum.Logical.And
title: And — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849242"
---
# <a name="and-function"></a>And — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let x = a and b;
let x = And(a, b);
```
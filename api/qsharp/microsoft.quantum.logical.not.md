---
uid: Microsoft.Quantum.Logical.Not
title: Not — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709865"
---
# <a name="not-function"></a>Not — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package [](https://nuget.org/packages/)


Zwraca wartość logiczną negacji wartości.

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="value--bool"></a>wartość: [bool](xref:microsoft.quantum.lang-ref.bool)

Wartość, która ma być Negacja.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy `value` jest `false` .

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```Q#
let x = not value;
let x = Not(value);
```
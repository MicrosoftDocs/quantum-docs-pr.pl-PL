---
uid: Microsoft.Quantum.Logical.Not
title: Not — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197453"
---
# <a name="not-function"></a>Not — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
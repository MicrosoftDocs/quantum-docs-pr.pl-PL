---
uid: Microsoft.Quantum.Logical.Not
title: Not — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849086"
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

```qsharp
let x = not value;
let x = Not(value);
```
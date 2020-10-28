---
uid: Microsoft.Quantum.Logical.Xor
title: XOR — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723295"
---
# <a name="xor-function"></a>XOR — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package [](https://nuget.org/packages/)


Zwraca wartość logiczną bez odłączenia dwóch wartości.

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--bool"></a>Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)

Pierwsza wartość do uwzględnienia.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Druga wartość do uwzględnienia.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy dokładnie jeden z `a` i `b` jest `true` .
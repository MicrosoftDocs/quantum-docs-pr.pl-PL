---
uid: Microsoft.Quantum.Logical.EqualD
title: Funkcja równa się
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816866"
---
# <a name="equald-function"></a>Funkcja równa się

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--double"></a>Odp.: [Double](xref:microsoft.quantum.lang-ref.double)

Pierwsza wartość do porównania.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Druga wartość do porównania.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy `a` jest równa `b` .

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```
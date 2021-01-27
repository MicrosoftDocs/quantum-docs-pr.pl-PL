---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: fbbf1f7a59600ecc4a0a59d1c08cd0e1310d2d20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814371"
---
# <a name="nearlyequald-function"></a>NearlyEqualD, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są niemal równe (to jest, w ramach tolerancji o wartości 1e-12).

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--double"></a>Odp.: [Double](xref:microsoft.quantum.lang-ref.double)

Pierwsza wartość do porównania.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Druga wartość do porównania.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` if i tylko wtedy, gdy `a` jest niemal równe `b` .

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```
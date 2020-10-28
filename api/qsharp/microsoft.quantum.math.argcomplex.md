---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723267"
---
# <a name="argcomplex-function"></a>ArgComplex, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package [](https://nuget.org/packages/)


Zwraca fazę złożonej liczby typów `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="input--complex"></a>dane wejściowe: [złożone](xref:Microsoft.Quantum.Math.Complex)

Liczba złożona $c = x + i y $.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)

Faza $ \text{Arg} [c] = \text{ArcTan} (y, x) \In (-\pi, \pi] $.
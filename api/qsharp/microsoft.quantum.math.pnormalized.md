---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722287"
---
# <a name="pnormalized-function"></a>PNormalized, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package [](https://nuget.org/packages/)


Normalizuje wektor `Double` s w `L(p)` normie.

Oznacza to, że dana tablica $x $ typu `Double[]` zwraca tablicę, w której wszystkie elementy są podzielone przez $p $-norma $ \| x \| _p $.

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>Dane wejściowe

### <a name="p--double"></a>p: [Double](xref:microsoft.quantum.lang-ref.double)

Wykładnik $p $ w $p $-norma.


### <a name="array--double"></a>Array: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)[]

Tablica $x $ znormalizowana przez $p $-norma $ \| x \| _p $.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Math. PNorm](xref:Microsoft.Quantum.Math.PNorm)
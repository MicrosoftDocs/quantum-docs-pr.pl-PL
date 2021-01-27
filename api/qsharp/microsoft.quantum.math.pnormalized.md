---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854851"
---
# <a name="pnormalized-function"></a>PNormalized, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
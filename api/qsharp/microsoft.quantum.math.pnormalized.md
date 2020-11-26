---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227526"
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
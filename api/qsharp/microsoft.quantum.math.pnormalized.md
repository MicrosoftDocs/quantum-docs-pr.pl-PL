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
# <a name="pnormalized-function"></a><span data-ttu-id="6ab6a-102">PNormalized, funkcja</span><span class="sxs-lookup"><span data-stu-id="6ab6a-102">PNormalized function</span></span>

<span data-ttu-id="6ab6a-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6ab6a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6ab6a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ab6a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ab6a-105">Normalizuje wektor `Double` s w `L(p)` normie.</span><span class="sxs-lookup"><span data-stu-id="6ab6a-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="6ab6a-106">Oznacza to, że dana tablica $x $ typu `Double[]` zwraca tablicę, w której wszystkie elementy są podzielone przez $p $-norma $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="6ab6a-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="6ab6a-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6ab6a-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="6ab6a-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6ab6a-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6ab6a-109">Wykładnik $p $ w $p $-norma.</span><span class="sxs-lookup"><span data-stu-id="6ab6a-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="6ab6a-110">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6ab6a-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="6ab6a-111">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6ab6a-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6ab6a-112">Tablica $x $ znormalizowana przez $p $-norma $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="6ab6a-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ab6a-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6ab6a-113">See Also</span></span>

- [<span data-ttu-id="6ab6a-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="6ab6a-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)
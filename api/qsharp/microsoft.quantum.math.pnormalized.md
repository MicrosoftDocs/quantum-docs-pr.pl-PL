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
# <a name="pnormalized-function"></a><span data-ttu-id="6f23b-102">PNormalized, funkcja</span><span class="sxs-lookup"><span data-stu-id="6f23b-102">PNormalized function</span></span>

<span data-ttu-id="6f23b-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6f23b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6f23b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f23b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f23b-105">Normalizuje wektor `Double` s w `L(p)` normie.</span><span class="sxs-lookup"><span data-stu-id="6f23b-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="6f23b-106">Oznacza to, że dana tablica $x $ typu `Double[]` zwraca tablicę, w której wszystkie elementy są podzielone przez $p $-norma $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="6f23b-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="6f23b-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6f23b-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="6f23b-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6f23b-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6f23b-109">Wykładnik $p $ w $p $-norma.</span><span class="sxs-lookup"><span data-stu-id="6f23b-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="6f23b-110">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6f23b-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="6f23b-111">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6f23b-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6f23b-112">Tablica $x $ znormalizowana przez $p $-norma $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="6f23b-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f23b-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6f23b-113">See Also</span></span>

- [<span data-ttu-id="6f23b-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="6f23b-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)
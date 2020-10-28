---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722301"
---
# <a name="pnorm-function"></a><span data-ttu-id="c481b-102">PNorm, funkcja</span><span class="sxs-lookup"><span data-stu-id="c481b-102">PNorm function</span></span>

<span data-ttu-id="c481b-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c481b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c481b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c481b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c481b-105">Zwraca `L(p)` normę wektora `Double` s.</span><span class="sxs-lookup"><span data-stu-id="c481b-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="c481b-106">Oznacza to, że dana tablica $x $ typu `Double[]` zwraca $p $-norma $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.</span><span class="sxs-lookup"><span data-stu-id="c481b-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="c481b-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c481b-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="c481b-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c481b-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c481b-109">Wykładnik $p $ w $p $-norma.</span><span class="sxs-lookup"><span data-stu-id="c481b-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="c481b-110">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c481b-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="c481b-111">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c481b-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c481b-112">$P $-norma $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="c481b-112">The $p$-norm $\|x\|_p$.</span></span>
---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194733"
---
# <a name="pnorm-function"></a><span data-ttu-id="8f3fb-102">PNorm, funkcja</span><span class="sxs-lookup"><span data-stu-id="8f3fb-102">PNorm function</span></span>

<span data-ttu-id="8f3fb-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8f3fb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8f3fb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f3fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f3fb-105">Zwraca `L(p)` normę wektora `Double` s.</span><span class="sxs-lookup"><span data-stu-id="8f3fb-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="8f3fb-106">Oznacza to, że dana tablica $x $ typu `Double[]` zwraca $p $-norma $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.</span><span class="sxs-lookup"><span data-stu-id="8f3fb-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="8f3fb-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8f3fb-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="8f3fb-108">p: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8f3fb-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8f3fb-109">Wykładnik $p $ w $p $-norma.</span><span class="sxs-lookup"><span data-stu-id="8f3fb-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="8f3fb-110">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8f3fb-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="8f3fb-111">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8f3fb-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8f3fb-112">$P $-norma $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="8f3fb-112">The $p$-norm $\|x\|_p$.</span></span>
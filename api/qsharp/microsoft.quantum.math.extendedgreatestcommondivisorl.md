---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e671405045d6d2587a8c6ccbac4ae3402f92f722
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723715"
---
# <a name="extendedgreatestcommondivisorl-function"></a><span data-ttu-id="19877-102">ExtendedGreatestCommonDivisorL, funkcja</span><span class="sxs-lookup"><span data-stu-id="19877-102">ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="19877-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="19877-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="19877-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19877-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19877-105">Oblicza krotkę $ (u, v) $, która $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, gdzie $ \operatorname{GCD} $ jest $a $ największy wspólny dzielnik $a $ i $b $.</span><span class="sxs-lookup"><span data-stu-id="19877-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="19877-106">GCD jest zawsze dodatni.</span><span class="sxs-lookup"><span data-stu-id="19877-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="19877-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="19877-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="19877-108">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="19877-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="19877-109">Pierwsza liczba, dla których jest obliczany największy wspólny dzielnik.</span><span class="sxs-lookup"><span data-stu-id="19877-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="19877-110">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="19877-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="19877-111">Druga liczba, dla której obliczany jest rozszerzony największy wspólny dzielnik</span><span class="sxs-lookup"><span data-stu-id="19877-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigintbigint"></a><span data-ttu-id="19877-112">Wynik: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="19877-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

<span data-ttu-id="19877-113">Krotki $ (u, v) $ z właściwością $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="19877-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="19877-114">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="19877-114">References</span></span>

- <span data-ttu-id="19877-115">Ta implementacja jest zależna od https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="19877-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>
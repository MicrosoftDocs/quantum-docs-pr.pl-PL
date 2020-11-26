---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195531"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="d020f-102">ExtendedGreatestCommonDivisorI, funkcja</span><span class="sxs-lookup"><span data-stu-id="d020f-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="d020f-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d020f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d020f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d020f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d020f-105">Oblicza krotkę $ (u, v) $, która $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, gdzie $ \operatorname{GCD} $ jest $a $ największy wspólny dzielnik $a $ i $b $.</span><span class="sxs-lookup"><span data-stu-id="d020f-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="d020f-106">GCD jest zawsze dodatni.</span><span class="sxs-lookup"><span data-stu-id="d020f-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="d020f-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d020f-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d020f-108">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d020f-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d020f-109">Pierwsza liczba, dla których jest obliczany największy wspólny dzielnik.</span><span class="sxs-lookup"><span data-stu-id="d020f-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="d020f-110">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d020f-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d020f-111">Druga liczba, dla której obliczany jest rozszerzony największy wspólny dzielnik</span><span class="sxs-lookup"><span data-stu-id="d020f-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="d020f-112">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="d020f-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="d020f-113">Krotki $ (u, v) $ z właściwością $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="d020f-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="d020f-114">Odwołania</span><span class="sxs-lookup"><span data-stu-id="d020f-114">References</span></span>

- <span data-ttu-id="d020f-115">Ta implementacja jest zależna od https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="d020f-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>
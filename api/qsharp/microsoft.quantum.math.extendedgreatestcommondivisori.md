---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 8cb21ae5052ae6c5a8aed8be71d6bd3d32034272
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723720"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="d8219-102">ExtendedGreatestCommonDivisorI, funkcja</span><span class="sxs-lookup"><span data-stu-id="d8219-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="d8219-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d8219-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d8219-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8219-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8219-105">Oblicza krotkę $ (u, v) $, która $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, gdzie $ \operatorname{GCD} $ jest $a $ największy wspólny dzielnik $a $ i $b $.</span><span class="sxs-lookup"><span data-stu-id="d8219-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="d8219-106">GCD jest zawsze dodatni.</span><span class="sxs-lookup"><span data-stu-id="d8219-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="d8219-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d8219-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d8219-108">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8219-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8219-109">Pierwsza liczba, dla których jest obliczany największy wspólny dzielnik.</span><span class="sxs-lookup"><span data-stu-id="d8219-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="d8219-110">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8219-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8219-111">Druga liczba, dla której obliczany jest rozszerzony największy wspólny dzielnik</span><span class="sxs-lookup"><span data-stu-id="d8219-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="d8219-112">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="d8219-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="d8219-113">Krotki $ (u, v) $ z właściwością $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="d8219-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="d8219-114">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="d8219-114">References</span></span>

- <span data-ttu-id="d8219-115">Ta implementacja jest zależna od https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="d8219-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>
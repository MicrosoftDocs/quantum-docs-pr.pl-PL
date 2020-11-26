---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192914"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="4e8c3-102">DrawRandomInt, operacja</span><span class="sxs-lookup"><span data-stu-id="4e8c3-102">DrawRandomInt operation</span></span>

<span data-ttu-id="4e8c3-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="4e8c3-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="4e8c3-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4e8c3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4e8c3-105">Rysuje losową liczbę całkowitą w danym zakresie włącznie.</span><span class="sxs-lookup"><span data-stu-id="4e8c3-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="4e8c3-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4e8c3-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="4e8c3-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e8c3-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e8c3-108">Najmniejsza liczba całkowita do narysowania.</span><span class="sxs-lookup"><span data-stu-id="4e8c3-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="4e8c3-109">maks.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e8c3-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e8c3-110">Największa liczba całkowita do narysowania.</span><span class="sxs-lookup"><span data-stu-id="4e8c3-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="4e8c3-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e8c3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e8c3-112">Liczba całkowita w zakresie włącznie z `min` do z `max` jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="4e8c3-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e8c3-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4e8c3-113">Remarks</span></span>

<span data-ttu-id="4e8c3-114">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="4e8c3-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e8c3-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4e8c3-115">See Also</span></span>

- [<span data-ttu-id="4e8c3-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="4e8c3-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)
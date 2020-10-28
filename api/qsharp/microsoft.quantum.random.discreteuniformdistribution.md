---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720297"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="b5665-102">DiscreteUniformDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="b5665-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="b5665-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b5665-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b5665-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5665-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5665-105">Zwraca jednolitą dystrybucję dla danego zakresu włącznie.</span><span class="sxs-lookup"><span data-stu-id="b5665-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="b5665-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b5665-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="b5665-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5665-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5665-108">Najmniejsza liczba całkowita do narysowania.</span><span class="sxs-lookup"><span data-stu-id="b5665-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="b5665-109">maks.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5665-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5665-110">Największa liczba całkowita do narysowania.</span><span class="sxs-lookup"><span data-stu-id="b5665-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="b5665-111">Wynik: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="b5665-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="b5665-112">Rozkład, którego losowo variates są liczbami całkowitymi w łącznym zakresie od `min` do `max` z jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="b5665-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5665-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b5665-113">Remarks</span></span>

<span data-ttu-id="b5665-114">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="b5665-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5665-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b5665-115">See Also</span></span>

- [<span data-ttu-id="b5665-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="b5665-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)
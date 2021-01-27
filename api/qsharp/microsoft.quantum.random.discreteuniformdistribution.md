---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853722"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="c6066-102">DiscreteUniformDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="c6066-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="c6066-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c6066-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c6066-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c6066-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c6066-105">Zwraca jednolitą dystrybucję dla danego zakresu włącznie.</span><span class="sxs-lookup"><span data-stu-id="c6066-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="c6066-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c6066-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="c6066-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6066-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6066-108">Najmniejsza liczba całkowita do narysowania.</span><span class="sxs-lookup"><span data-stu-id="c6066-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="c6066-109">maks.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6066-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6066-110">Największa liczba całkowita do narysowania.</span><span class="sxs-lookup"><span data-stu-id="c6066-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="c6066-111">Wynik: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="c6066-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="c6066-112">Rozkład, którego losowo variates są liczbami całkowitymi w łącznym zakresie od `min` do `max` z jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="c6066-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="c6066-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="c6066-113">Example</span></span>

<span data-ttu-id="c6066-114">Poniższy fragment kodu Q # losowy rzutuje na sześć stron:</span><span class="sxs-lookup"><span data-stu-id="c6066-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="c6066-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c6066-115">Remarks</span></span>

<span data-ttu-id="c6066-116">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="c6066-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6066-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c6066-117">See Also</span></span>

- [<span data-ttu-id="c6066-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="c6066-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)
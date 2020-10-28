---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709431"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="34a74-102">ContinuousUniformDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="34a74-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="34a74-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="34a74-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="34a74-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34a74-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34a74-105">Zwraca jednolitą dystrybucję dla danego interwału włącznie.</span><span class="sxs-lookup"><span data-stu-id="34a74-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="34a74-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="34a74-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="34a74-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="34a74-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="34a74-108">Najmniejsza liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="34a74-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="34a74-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="34a74-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="34a74-110">Największa liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="34a74-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="34a74-111">Wynik: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="34a74-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="34a74-112">Rozkład, którego losowo variates są liczbami rzeczywistymi w interwale włącznie z `min` do, `max` z jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="34a74-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="34a74-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="34a74-113">Remarks</span></span>

<span data-ttu-id="34a74-114">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="34a74-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="34a74-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="34a74-115">See Also</span></span>

- [<span data-ttu-id="34a74-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="34a74-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)
---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193084"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="0ed3f-102">ContinuousUniformDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="0ed3f-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="0ed3f-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="0ed3f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="0ed3f-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0ed3f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0ed3f-105">Zwraca jednolitą dystrybucję dla danego interwału włącznie.</span><span class="sxs-lookup"><span data-stu-id="0ed3f-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="0ed3f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0ed3f-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="0ed3f-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0ed3f-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0ed3f-108">Najmniejsza liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="0ed3f-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="0ed3f-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0ed3f-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0ed3f-110">Największa liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="0ed3f-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="0ed3f-111">Wynik: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="0ed3f-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="0ed3f-112">Rozkład, którego losowo variates są liczbami rzeczywistymi w interwale włącznie z `min` do, `max` z jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="0ed3f-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="0ed3f-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0ed3f-113">Remarks</span></span>

<span data-ttu-id="0ed3f-114">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="0ed3f-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ed3f-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0ed3f-115">See Also</span></span>

- [<span data-ttu-id="0ed3f-116">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="0ed3f-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)
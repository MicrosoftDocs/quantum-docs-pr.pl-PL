---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842313"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="78bd8-102">ContinuousUniformDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="78bd8-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="78bd8-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="78bd8-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="78bd8-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="78bd8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="78bd8-105">Zwraca jednolitą dystrybucję dla danego interwału włącznie.</span><span class="sxs-lookup"><span data-stu-id="78bd8-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="78bd8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="78bd8-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="78bd8-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78bd8-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78bd8-108">Najmniejsza liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="78bd8-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="78bd8-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78bd8-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78bd8-110">Największa liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="78bd8-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="78bd8-111">Wynik: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="78bd8-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="78bd8-112">Rozkład, którego losowo variates są liczbami rzeczywistymi w interwale włącznie z `min` do, `max` z jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="78bd8-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="78bd8-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="78bd8-113">Example</span></span>

<span data-ttu-id="78bd8-114">Poniższy fragment kodu Q # losowo rysuje kąt między $0 $ i $2 \pi $:</span><span class="sxs-lookup"><span data-stu-id="78bd8-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="78bd8-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="78bd8-115">Remarks</span></span>

<span data-ttu-id="78bd8-116">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="78bd8-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="78bd8-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="78bd8-117">See Also</span></span>

- [<span data-ttu-id="78bd8-118">Microsoft. Quantum. DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="78bd8-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)
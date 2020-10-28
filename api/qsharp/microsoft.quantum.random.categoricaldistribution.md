---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722819"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="41766-102">CategoricalDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="41766-102">CategoricalDistribution function</span></span>

<span data-ttu-id="41766-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="41766-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="41766-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41766-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41766-105">Zwraca dyskretną dystrybucję kategorii, w której prawdopodobieństwo dla każdej ze skończonej listy podanych wyników jest jawnie określone.</span><span class="sxs-lookup"><span data-stu-id="41766-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="41766-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="41766-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="41766-107">PRAWDPD: [Podwójna](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="41766-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="41766-108">Prawdopodobieństwa dla każdego wyniku z rozkładu kategorii.</span><span class="sxs-lookup"><span data-stu-id="41766-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="41766-109">Te prawdopodobieństwa nie mogą być znormalizowane, ale muszą być nieujemne.</span><span class="sxs-lookup"><span data-stu-id="41766-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="41766-110">Wynik: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="41766-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="41766-111">Indeks `i` z prawdopodobieństwem `probs[i] / sum` , gdzie `sum` jest sumą `probs` podaną przez `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="41766-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>
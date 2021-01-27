---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842345"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="6a85e-102">CategoricalDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="6a85e-102">CategoricalDistribution function</span></span>

<span data-ttu-id="6a85e-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="6a85e-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="6a85e-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6a85e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6a85e-105">Zwraca dyskretną dystrybucję kategorii, w której prawdopodobieństwo dla każdej ze skończonej listy podanych wyników jest jawnie określone.</span><span class="sxs-lookup"><span data-stu-id="6a85e-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="6a85e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6a85e-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="6a85e-107">PRAWDPD: [Podwójna](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6a85e-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6a85e-108">Prawdopodobieństwa dla każdego wyniku z rozkładu kategorii.</span><span class="sxs-lookup"><span data-stu-id="6a85e-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="6a85e-109">Te prawdopodobieństwa nie mogą być znormalizowane, ale muszą być nieujemne.</span><span class="sxs-lookup"><span data-stu-id="6a85e-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="6a85e-110">Wynik: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="6a85e-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="6a85e-111">Indeks `i` z prawdopodobieństwem `probs[i] / sum` , gdzie `sum` jest sumą `probs` podaną przez `Fold(PlusD, 0.0, probs)` .</span><span class="sxs-lookup"><span data-stu-id="6a85e-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>

## <a name="example"></a><span data-ttu-id="6a85e-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="6a85e-112">Example</span></span>

<span data-ttu-id="6a85e-113">Poniższy kod Q # będzie wyświetlał 0 z prawdopodobieństwem 30% i 1 z prawdopodobieństwem 70%:</span><span class="sxs-lookup"><span data-stu-id="6a85e-113">The following Q# code will display 0 with probability 30% and 1 with probability 70%:</span></span>

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```
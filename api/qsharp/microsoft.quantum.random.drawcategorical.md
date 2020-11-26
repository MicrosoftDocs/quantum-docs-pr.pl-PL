---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192999"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="bdcf2-102">DrawCategorical, operacja</span><span class="sxs-lookup"><span data-stu-id="bdcf2-102">DrawCategorical operation</span></span>

<span data-ttu-id="bdcf2-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="bdcf2-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="bdcf2-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bdcf2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bdcf2-105">Rysuje losową próbkę z dystrybucji kategorii określonej przez listę probablities.</span><span class="sxs-lookup"><span data-stu-id="bdcf2-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="bdcf2-106">Opis</span><span class="sxs-lookup"><span data-stu-id="bdcf2-106">Description</span></span>

<span data-ttu-id="bdcf2-107">Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie.</span><span class="sxs-lookup"><span data-stu-id="bdcf2-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="bdcf2-108">Elementy tablicy, które są równe zeru, są ignorowane, a ich indeksy nigdy nie są zwracane.</span><span class="sxs-lookup"><span data-stu-id="bdcf2-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="bdcf2-109">Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="bdcf2-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="bdcf2-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bdcf2-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="bdcf2-111">PRAWDPD: [Podwójna](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bdcf2-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bdcf2-112">Tablica liczb zmiennoprzecinkowych proporcjonalnie do prawdopodobieństwa zaznaczenia poszczególnych indeksów.</span><span class="sxs-lookup"><span data-stu-id="bdcf2-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="bdcf2-113">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bdcf2-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bdcf2-114">Liczba całkowita $i $ z prawdopodobieństwem $ \Pr (i) = p_i/\ sum_i p_i $, gdzie $p _i $ to $i $ ty elementu `probs` .</span><span class="sxs-lookup"><span data-stu-id="bdcf2-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdcf2-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bdcf2-115">See Also</span></span>

- [<span data-ttu-id="bdcf2-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="bdcf2-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)
---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720285"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="442cc-102">DrawCategorical, operacja</span><span class="sxs-lookup"><span data-stu-id="442cc-102">DrawCategorical operation</span></span>

<span data-ttu-id="442cc-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="442cc-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="442cc-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="442cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="442cc-105">Rysuje losową próbkę z dystrybucji kategorii określonej przez listę probablities.</span><span class="sxs-lookup"><span data-stu-id="442cc-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="442cc-106">Opis</span><span class="sxs-lookup"><span data-stu-id="442cc-106">Description</span></span>

<span data-ttu-id="442cc-107">Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie.</span><span class="sxs-lookup"><span data-stu-id="442cc-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="442cc-108">Elementy tablicy, które są równe zeru, są ignorowane, a ich indeksy nigdy nie są zwracane.</span><span class="sxs-lookup"><span data-stu-id="442cc-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="442cc-109">Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="442cc-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="442cc-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="442cc-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="442cc-111">PRAWDPD: [Podwójna](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="442cc-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="442cc-112">Tablica liczb zmiennoprzecinkowych proporcjonalnie do prawdopodobieństwa zaznaczenia poszczególnych indeksów.</span><span class="sxs-lookup"><span data-stu-id="442cc-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="442cc-113">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="442cc-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="442cc-114">Liczba całkowita $i $ z prawdopodobieństwem $ \Pr (i) = p_i/\ sum_i p_i $, gdzie $p _i $ to $i $ ty elementu `probs` .</span><span class="sxs-lookup"><span data-stu-id="442cc-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="442cc-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="442cc-115">See Also</span></span>

- [<span data-ttu-id="442cc-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="442cc-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)
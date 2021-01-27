---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a9fe1b08e80abc65a5c4b803f0cb8a5e7a62759c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851149"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="f9e26-102">DrawCategorical, operacja</span><span class="sxs-lookup"><span data-stu-id="f9e26-102">DrawCategorical operation</span></span>

<span data-ttu-id="f9e26-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="f9e26-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="f9e26-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f9e26-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f9e26-105">Rysuje losową próbkę z dystrybucji kategorii określonej przez listę probablities.</span><span class="sxs-lookup"><span data-stu-id="f9e26-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="f9e26-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f9e26-106">Description</span></span>

<span data-ttu-id="f9e26-107">Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie.</span><span class="sxs-lookup"><span data-stu-id="f9e26-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="f9e26-108">Elementy tablicy, które są równe zeru, są ignorowane, a ich indeksy nigdy nie są zwracane.</span><span class="sxs-lookup"><span data-stu-id="f9e26-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="f9e26-109">Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="f9e26-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="f9e26-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f9e26-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="f9e26-111">PRAWDPD: [Podwójna](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f9e26-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f9e26-112">Tablica liczb zmiennoprzecinkowych proporcjonalnie do prawdopodobieństwa zaznaczenia poszczególnych indeksów.</span><span class="sxs-lookup"><span data-stu-id="f9e26-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="f9e26-113">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9e26-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9e26-114">Liczba całkowita $i $ z prawdopodobieństwem $ \Pr (i) = p_i/\ sum_i p_i $, gdzie $p _i $ to $i $ ty elementu `probs` .</span><span class="sxs-lookup"><span data-stu-id="f9e26-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9e26-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f9e26-115">See Also</span></span>

- [<span data-ttu-id="f9e26-116">Microsoft. Quantum. Random. CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="f9e26-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)
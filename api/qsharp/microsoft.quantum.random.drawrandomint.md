---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724658"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="2959b-102">DrawRandomInt, operacja</span><span class="sxs-lookup"><span data-stu-id="2959b-102">DrawRandomInt operation</span></span>

<span data-ttu-id="2959b-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="2959b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="2959b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2959b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2959b-105">Rysuje losową liczbę całkowitą w danym zakresie włącznie.</span><span class="sxs-lookup"><span data-stu-id="2959b-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="2959b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2959b-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="2959b-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2959b-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2959b-108">Najmniejsza liczba całkowita do narysowania.</span><span class="sxs-lookup"><span data-stu-id="2959b-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="2959b-109">maks.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2959b-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2959b-110">Największa liczba całkowita do narysowania.</span><span class="sxs-lookup"><span data-stu-id="2959b-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="2959b-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2959b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2959b-112">Liczba całkowita w zakresie włącznie z `min` do z `max` jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="2959b-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="2959b-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2959b-113">Remarks</span></span>

<span data-ttu-id="2959b-114">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="2959b-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2959b-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2959b-115">See Also</span></span>

- [<span data-ttu-id="2959b-116">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="2959b-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)
---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723986"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="0b655-102">DrawRandomDouble, operacja</span><span class="sxs-lookup"><span data-stu-id="0b655-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="0b655-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="0b655-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="0b655-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b655-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b655-105">Rysuje losową liczbę rzeczywistą w danym interwale włącznie.</span><span class="sxs-lookup"><span data-stu-id="0b655-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="0b655-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0b655-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="0b655-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0b655-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0b655-108">Najmniejsza liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="0b655-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="0b655-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0b655-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0b655-110">Największa liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="0b655-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="0b655-111">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0b655-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0b655-112">Losowa liczba rzeczywista w interwale łącznym od `min` do wartości `max` z jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="0b655-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b655-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0b655-113">Remarks</span></span>

<span data-ttu-id="0b655-114">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="0b655-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b655-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0b655-115">See Also</span></span>

- [<span data-ttu-id="0b655-116">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="0b655-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)
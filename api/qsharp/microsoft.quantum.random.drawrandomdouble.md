---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192948"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="3b8de-102">DrawRandomDouble, operacja</span><span class="sxs-lookup"><span data-stu-id="3b8de-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="3b8de-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3b8de-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3b8de-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3b8de-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3b8de-105">Rysuje losową liczbę rzeczywistą w danym interwale włącznie.</span><span class="sxs-lookup"><span data-stu-id="3b8de-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="3b8de-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3b8de-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="3b8de-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3b8de-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3b8de-108">Najmniejsza liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="3b8de-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="3b8de-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3b8de-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3b8de-110">Największa liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="3b8de-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="3b8de-111">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3b8de-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3b8de-112">Losowa liczba rzeczywista w interwale łącznym od `min` do wartości `max` z jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="3b8de-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b8de-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3b8de-113">Remarks</span></span>

<span data-ttu-id="3b8de-114">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="3b8de-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b8de-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3b8de-115">See Also</span></span>

- [<span data-ttu-id="3b8de-116">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="3b8de-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)
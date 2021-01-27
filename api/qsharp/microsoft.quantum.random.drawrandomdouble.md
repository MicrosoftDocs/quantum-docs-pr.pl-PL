---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847622"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="ec272-102">DrawRandomDouble, operacja</span><span class="sxs-lookup"><span data-stu-id="ec272-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="ec272-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ec272-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ec272-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ec272-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ec272-105">Rysuje losową liczbę rzeczywistą w danym interwale włącznie.</span><span class="sxs-lookup"><span data-stu-id="ec272-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="ec272-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ec272-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="ec272-107">min: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ec272-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ec272-108">Najmniejsza liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="ec272-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="ec272-109">Max: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ec272-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ec272-110">Największa liczba rzeczywista do narysowania.</span><span class="sxs-lookup"><span data-stu-id="ec272-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="ec272-111">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ec272-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ec272-112">Losowa liczba rzeczywista w interwale łącznym od `min` do wartości `max` z jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="ec272-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="ec272-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="ec272-113">Example</span></span>

<span data-ttu-id="ec272-114">Poniższy fragment kodu Q # losowo rysuje kąt między $0 $ i $2 \pi $:</span><span class="sxs-lookup"><span data-stu-id="ec272-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="ec272-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ec272-115">Remarks</span></span>

<span data-ttu-id="ec272-116">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="ec272-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec272-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ec272-117">See Also</span></span>

- [<span data-ttu-id="ec272-118">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="ec272-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)
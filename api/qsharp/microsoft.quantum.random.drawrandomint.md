---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851140"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="92e47-102">DrawRandomInt, operacja</span><span class="sxs-lookup"><span data-stu-id="92e47-102">DrawRandomInt operation</span></span>

<span data-ttu-id="92e47-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="92e47-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="92e47-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="92e47-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="92e47-105">Rysuje losową liczbę całkowitą w danym zakresie włącznie.</span><span class="sxs-lookup"><span data-stu-id="92e47-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="92e47-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="92e47-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="92e47-107">min: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92e47-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92e47-108">Najmniejsza liczba całkowita do narysowania.</span><span class="sxs-lookup"><span data-stu-id="92e47-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="92e47-109">maks.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92e47-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92e47-110">Największa liczba całkowita do narysowania.</span><span class="sxs-lookup"><span data-stu-id="92e47-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="92e47-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92e47-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92e47-112">Liczba całkowita w zakresie włącznie z `min` do z `max` jednolitym prawdopodobieństwem.</span><span class="sxs-lookup"><span data-stu-id="92e47-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="92e47-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="92e47-113">Example</span></span>

<span data-ttu-id="92e47-114">Poniższy fragment kodu Q # losowy rzutuje na sześć stron:</span><span class="sxs-lookup"><span data-stu-id="92e47-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="92e47-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="92e47-115">Remarks</span></span>

<span data-ttu-id="92e47-116">Kończy się niepowodzeniem, jeśli `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="92e47-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="92e47-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="92e47-117">See Also</span></span>

- [<span data-ttu-id="92e47-118">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="92e47-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)
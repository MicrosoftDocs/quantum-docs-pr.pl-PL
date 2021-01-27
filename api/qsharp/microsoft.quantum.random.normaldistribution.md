---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814180"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="3a1cb-102">NormalDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="3a1cb-102">NormalDistribution function</span></span>

<span data-ttu-id="3a1cb-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3a1cb-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3a1cb-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3a1cb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3a1cb-105">Zwraca rozkład normalny z określoną średnią i wariancją.</span><span class="sxs-lookup"><span data-stu-id="3a1cb-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="3a1cb-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3a1cb-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="3a1cb-107">średnia: [Podwójna](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3a1cb-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="3a1cb-108">WARIANCJA: [Podwójna](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3a1cb-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="3a1cb-109">Wynik: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="3a1cb-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="3a1cb-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="3a1cb-110">Example</span></span>

<span data-ttu-id="3a1cb-111">Poniżej przedstawiono 10 próbek z rozkładu normalnego ze znakiem 2 i odchylenie standardowe 0,1:</span><span class="sxs-lookup"><span data-stu-id="3a1cb-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="3a1cb-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3a1cb-112">See Also</span></span>

- [<span data-ttu-id="3a1cb-113">Microsoft. Quantum. Random. StandardNormalDistribution</span><span class="sxs-lookup"><span data-stu-id="3a1cb-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)
---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191452"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="185d3-102">FixedPointReflectionPhases, funkcja</span><span class="sxs-lookup"><span data-stu-id="185d3-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="185d3-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="185d3-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="185d3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="185d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="185d3-105">Oblicza częściowe fazy odbicia dla wzmocnienia amplitudy stałej.</span><span class="sxs-lookup"><span data-stu-id="185d3-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="185d3-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="185d3-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="185d3-107">nQueries: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="185d3-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="185d3-108">Liczba zapytań do przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="185d3-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="185d3-109">Musi być nieparzystą liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="185d3-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="185d3-110">successMin: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="185d3-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="185d3-111">Minimalne prawdopodobieństwo sukcesu.</span><span class="sxs-lookup"><span data-stu-id="185d3-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="185d3-112">Wynik: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="185d3-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="185d3-113">Tablica faz, które mogą być używane w implementacji algorytmu Quantum w ramach amplitudy stałych punktów.</span><span class="sxs-lookup"><span data-stu-id="185d3-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="185d3-114">Odwołania</span><span class="sxs-lookup"><span data-stu-id="185d3-114">References</span></span>

<span data-ttu-id="185d3-115">Używamy faz w "wzmocnienia amplitudy stałej" z optymalną liczbą zapytań "</span><span class="sxs-lookup"><span data-stu-id="185d3-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="185d3-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Zobacz również "Metodologia złożonych bram Quantum"</span><span class="sxs-lookup"><span data-stu-id="185d3-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="185d3-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) dla faz w `RotationPhases` formacie.</span><span class="sxs-lookup"><span data-stu-id="185d3-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>
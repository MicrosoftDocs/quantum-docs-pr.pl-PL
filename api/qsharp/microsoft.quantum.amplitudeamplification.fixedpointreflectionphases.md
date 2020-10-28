---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721858"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="298ba-102">FixedPointReflectionPhases, funkcja</span><span class="sxs-lookup"><span data-stu-id="298ba-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="298ba-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="298ba-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="298ba-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="298ba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="298ba-105">Oblicza częściowe fazy odbicia dla wzmocnienia amplitudy stałej.</span><span class="sxs-lookup"><span data-stu-id="298ba-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="298ba-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="298ba-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="298ba-107">nQueries: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="298ba-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="298ba-108">Liczba zapytań do przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="298ba-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="298ba-109">Musi być nieparzystą liczbą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="298ba-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="298ba-110">successMin: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="298ba-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="298ba-111">Minimalne prawdopodobieństwo sukcesu.</span><span class="sxs-lookup"><span data-stu-id="298ba-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="298ba-112">Wynik: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="298ba-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="298ba-113">Tablica faz, które mogą być używane w implementacji algorytmu Quantum w ramach amplitudy stałych punktów.</span><span class="sxs-lookup"><span data-stu-id="298ba-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="298ba-114">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="298ba-114">References</span></span>

<span data-ttu-id="298ba-115">Używamy faz w "wzmocnienia amplitudy stałej" z optymalną liczbą zapytań "</span><span class="sxs-lookup"><span data-stu-id="298ba-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="298ba-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Zobacz również "Metodologia złożonych bram Quantum"</span><span class="sxs-lookup"><span data-stu-id="298ba-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="298ba-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) dla faz w `RotationPhases` formacie.</span><span class="sxs-lookup"><span data-stu-id="298ba-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>
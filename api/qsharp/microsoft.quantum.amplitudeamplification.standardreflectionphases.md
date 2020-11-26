---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 316c8f22a16859ebb439824eda9a5aa02c750b5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191129"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="02425-102">StandardReflectionPhases, funkcja</span><span class="sxs-lookup"><span data-stu-id="02425-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="02425-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="02425-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="02425-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02425-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02425-105">Oblicza częściowe fazy odbicia w przypadku wzmocnienia amplitudy standardowej.</span><span class="sxs-lookup"><span data-stu-id="02425-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="02425-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="02425-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="02425-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="02425-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="02425-108">Liczba iteracji wzmocnienia amplitudy, dla których mają zostać wygenerowane częściowe fazy odbicia.</span><span class="sxs-lookup"><span data-stu-id="02425-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="02425-109">Wynik: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="02425-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="02425-110">Operacja implementująca fazy określone jako częściowe odbicie</span><span class="sxs-lookup"><span data-stu-id="02425-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="02425-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="02425-111">Remarks</span></span>

<span data-ttu-id="02425-112">Wszystkie fazy to $ \pi $, z wyjątkiem pierwszego odbicia stanu początkowego i ostatniego odbicia w stanie docelowym, które są $0 $.</span><span class="sxs-lookup"><span data-stu-id="02425-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>
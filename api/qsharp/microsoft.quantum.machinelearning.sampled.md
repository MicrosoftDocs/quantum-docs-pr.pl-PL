---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Próbkowanie funkcji
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211631"
---
# <a name="sampled-function"></a><span data-ttu-id="48062-102">Próbkowanie funkcji</span><span class="sxs-lookup"><span data-stu-id="48062-102">Sampled function</span></span>

<span data-ttu-id="48062-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="48062-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="48062-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="48062-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="48062-105">Próbkuje daną tablicę przy użyciu danego harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="48062-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="48062-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="48062-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="48062-107">Harmonogram: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="48062-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="48062-108">Harmonogram do użycia w wartościach próbkowania.</span><span class="sxs-lookup"><span data-stu-id="48062-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="48062-109">wartości: t []</span><span class="sxs-lookup"><span data-stu-id="48062-109">values : 'T[]</span></span>

<span data-ttu-id="48062-110">Tablica wartości do próbkowania.</span><span class="sxs-lookup"><span data-stu-id="48062-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="48062-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="48062-111">Output : 'T[]</span></span>

<span data-ttu-id="48062-112">Tablica elementów z wartości, zgodnie z podanym harmonogramem.</span><span class="sxs-lookup"><span data-stu-id="48062-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="48062-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="48062-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48062-114">'C</span><span class="sxs-lookup"><span data-stu-id="48062-114">'T</span></span>


---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Próbkowanie funkcji
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854948"
---
# <a name="sampled-function"></a><span data-ttu-id="82b4c-102">Próbkowanie funkcji</span><span class="sxs-lookup"><span data-stu-id="82b4c-102">Sampled function</span></span>

<span data-ttu-id="82b4c-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="82b4c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="82b4c-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="82b4c-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="82b4c-105">Próbkuje daną tablicę przy użyciu danego harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="82b4c-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="82b4c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="82b4c-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="82b4c-107">Harmonogram: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="82b4c-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="82b4c-108">Harmonogram do użycia w wartościach próbkowania.</span><span class="sxs-lookup"><span data-stu-id="82b4c-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="82b4c-109">wartości: t []</span><span class="sxs-lookup"><span data-stu-id="82b4c-109">values : 'T[]</span></span>

<span data-ttu-id="82b4c-110">Tablica wartości do próbkowania.</span><span class="sxs-lookup"><span data-stu-id="82b4c-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="82b4c-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="82b4c-111">Output : 'T[]</span></span>

<span data-ttu-id="82b4c-112">Tablica elementów z wartości, zgodnie z podanym harmonogramem.</span><span class="sxs-lookup"><span data-stu-id="82b4c-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="82b4c-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="82b4c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="82b4c-114">'C</span><span class="sxs-lookup"><span data-stu-id="82b4c-114">'T</span></span>


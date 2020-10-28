---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Próbkowanie funkcji
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722427"
---
# <a name="sampled-function"></a><span data-ttu-id="08312-102">Próbkowanie funkcji</span><span class="sxs-lookup"><span data-stu-id="08312-102">Sampled function</span></span>

<span data-ttu-id="08312-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="08312-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="08312-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08312-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08312-105">Próbkuje daną tablicę przy użyciu danego harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="08312-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="08312-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="08312-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="08312-107">Harmonogram: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="08312-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="08312-108">Harmonogram do użycia w wartościach próbkowania.</span><span class="sxs-lookup"><span data-stu-id="08312-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="08312-109">wartości: t []</span><span class="sxs-lookup"><span data-stu-id="08312-109">values : 'T[]</span></span>

<span data-ttu-id="08312-110">Tablica wartości do próbkowania.</span><span class="sxs-lookup"><span data-stu-id="08312-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="08312-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="08312-111">Output : 'T[]</span></span>

<span data-ttu-id="08312-112">Tablica elementów z wartości, zgodnie z podanym harmonogramem.</span><span class="sxs-lookup"><span data-stu-id="08312-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="08312-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="08312-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="08312-114">'C</span><span class="sxs-lookup"><span data-stu-id="08312-114">'T</span></span>


---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 008bdcdc0a7c0ad2775dea65ebba46556092beed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211597"
---
# <a name="schedulelength-function"></a><span data-ttu-id="04127-102">ScheduleLength, funkcja</span><span class="sxs-lookup"><span data-stu-id="04127-102">ScheduleLength function</span></span>

<span data-ttu-id="04127-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="04127-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="04127-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="04127-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="04127-105">Zwraca liczbę elementów w danym harmonogramie próbkowania.</span><span class="sxs-lookup"><span data-stu-id="04127-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="04127-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="04127-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="04127-107">Harmonogram: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="04127-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="04127-108">Harmonogram próbkowania, którego długość ma zostać zwrócona.</span><span class="sxs-lookup"><span data-stu-id="04127-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="04127-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04127-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04127-110">Liczba elementów w danym harmonogramie próbkowania.</span><span class="sxs-lookup"><span data-stu-id="04127-110">The number of elements in the given sampling schedule.</span></span>
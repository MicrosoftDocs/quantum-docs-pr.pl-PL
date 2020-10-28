---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 77538984fbd7334712df423b991ef43ce31ed849
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722404"
---
# <a name="schedulelength-function"></a><span data-ttu-id="16237-102">ScheduleLength, funkcja</span><span class="sxs-lookup"><span data-stu-id="16237-102">ScheduleLength function</span></span>

<span data-ttu-id="16237-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="16237-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="16237-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="16237-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="16237-105">Zwraca liczbę elementów w danym harmonogramie próbkowania.</span><span class="sxs-lookup"><span data-stu-id="16237-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="16237-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="16237-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="16237-107">Harmonogram: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="16237-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="16237-108">Harmonogram próbkowania, którego długość ma zostać zwrócona.</span><span class="sxs-lookup"><span data-stu-id="16237-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="16237-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="16237-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="16237-110">Liczba elementów w danym harmonogramie próbkowania.</span><span class="sxs-lookup"><span data-stu-id="16237-110">The number of elements in the given sampling schedule.</span></span>
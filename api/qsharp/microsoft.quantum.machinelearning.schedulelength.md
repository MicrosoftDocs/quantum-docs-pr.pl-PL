---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: dd042b1282d2f5386ee0b67bf57ad4027eefd493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854904"
---
# <a name="schedulelength-function"></a><span data-ttu-id="2dce5-102">ScheduleLength, funkcja</span><span class="sxs-lookup"><span data-stu-id="2dce5-102">ScheduleLength function</span></span>

<span data-ttu-id="2dce5-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2dce5-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2dce5-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2dce5-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2dce5-105">Zwraca liczbę elementów w danym harmonogramie próbkowania.</span><span class="sxs-lookup"><span data-stu-id="2dce5-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="2dce5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2dce5-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="2dce5-107">Harmonogram: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="2dce5-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="2dce5-108">Harmonogram próbkowania, którego długość ma zostać zwrócona.</span><span class="sxs-lookup"><span data-stu-id="2dce5-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="2dce5-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2dce5-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2dce5-110">Liczba elementów w danym harmonogramie próbkowania.</span><span class="sxs-lookup"><span data-stu-id="2dce5-110">The number of elements in the given sampling schedule.</span></span>
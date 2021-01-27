---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856006"
---
# <a name="defaulttrainingoptions-function"></a><span data-ttu-id="7fd59-102">DefaultTrainingOptions, funkcja</span><span class="sxs-lookup"><span data-stu-id="7fd59-102">DefaultTrainingOptions function</span></span>

<span data-ttu-id="7fd59-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7fd59-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7fd59-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7fd59-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7fd59-105">Zwraca domyślny zestaw opcji dla klasyfikatora szkoleniowego.</span><span class="sxs-lookup"><span data-stu-id="7fd59-105">Returns a default set of options for training classifiers.</span></span>

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a><span data-ttu-id="7fd59-106">Wynik: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="7fd59-106">Output : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="7fd59-107">Rozsądny zestaw domyślnych opcji szkolenia do użycia w przypadku klasyfikatorów szkoleniowych.</span><span class="sxs-lookup"><span data-stu-id="7fd59-107">A reasonable set of default training options for use when training classifiers.</span></span>

## <a name="example"></a><span data-ttu-id="7fd59-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="7fd59-108">Example</span></span>

<span data-ttu-id="7fd59-109">Aby użyć opcji domyślnych, ale z dodatkowymi pomiarami, użyj `w/` operatora:</span><span class="sxs-lookup"><span data-stu-id="7fd59-109">To use the default options, but with additional measurements, use the `w/` operator:</span></span>

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```
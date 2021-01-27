---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: TrainSequentialClassifier, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 97865965bef831eeb53245ba0c23d6bce54643ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847707"
---
# <a name="trainsequentialclassifier-operation"></a><span data-ttu-id="d7b7c-102">TrainSequentialClassifier, operacja</span><span class="sxs-lookup"><span data-stu-id="d7b7c-102">TrainSequentialClassifier operation</span></span>

<span data-ttu-id="d7b7c-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d7b7c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d7b7c-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d7b7c-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d7b7c-105">Ze względu na strukturę klasyfikatora sekwencyjnego, pociąga klasyfikatora w danym zestawie szkoleń z etykietami.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set.</span></span>

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="d7b7c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d7b7c-106">Input</span></span>

### <a name="models--sequentialmodel"></a><span data-ttu-id="d7b7c-107">modele: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span><span class="sxs-lookup"><span data-stu-id="d7b7c-107">models : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span></span>

<span data-ttu-id="d7b7c-108">Tablica modeli do użycia jako punkty wyjścia podczas szkolenia.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-108">An array of models to be used as starting points during training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="d7b7c-109">Przykłady: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="d7b7c-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="d7b7c-110">Zestaw etykietowych danych szkoleniowych, które zostaną użyte do przeprowadzenia szkolenia.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="d7b7c-111">Opcje: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="d7b7c-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="d7b7c-112">Konfiguracja używana do uczenia się; Zobacz @"microsoft.quantum.machinelearning.trainingoptions" i, @"microsoft.quantum.machinelearning.defaulttrainingoptions" Aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="d7b7c-113">trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="d7b7c-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="d7b7c-114">Harmonogram próbkowania do użycia podczas wybierania próbek z danych szkoleniowych podczas wykonywania kroków szkoleniowych.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="d7b7c-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="d7b7c-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="d7b7c-116">Harmonogram próbkowania, który ma być używany podczas wybierania próbek z danych szkoleniowych w przypadku wybrania, który punkt początkowy spowodował wynik najlepszego klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="d7b7c-117">Wynik: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="d7b7c-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="d7b7c-118">Parametryzacja danego klasyfikatora i różnica między tymi dwoma klasami, łącznie z najlepszymi wynikami z poszczególnych punktów początkowych.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="d7b7c-119">Liczba chybień obserwowanych w modelu najlepszego klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="d7b7c-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7b7c-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d7b7c-120">See Also</span></span>

- [<span data-ttu-id="d7b7c-121">Microsoft. Quantum. MachineLearning. TrainSequentialClassifierAtModel</span><span class="sxs-lookup"><span data-stu-id="d7b7c-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [<span data-ttu-id="d7b7c-122">Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="d7b7c-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)
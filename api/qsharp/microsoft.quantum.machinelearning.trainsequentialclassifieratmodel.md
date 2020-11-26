---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 02a300a2e1029d0e09aba19d090e15128fede717
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211471"
---
# <a name="trainsequentialclassifieratmodel-operation"></a><span data-ttu-id="d0cec-102">TrainSequentialClassifierAtModel, operacja</span><span class="sxs-lookup"><span data-stu-id="d0cec-102">TrainSequentialClassifierAtModel operation</span></span>

<span data-ttu-id="d0cec-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d0cec-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d0cec-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d0cec-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d0cec-105">Ze względu na strukturę klasyfikatora sekwencyjnego, pociąga klasyfikatora z danego zestawu szkoleniowego z etykietą, rozpoczynając od określonego modelu.</span><span class="sxs-lookup"><span data-stu-id="d0cec-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.</span></span>

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="d0cec-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d0cec-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="d0cec-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="d0cec-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="d0cec-108">Sekwencyjny model, który ma być używany jako punkt wyjścia do szkoleń.</span><span class="sxs-lookup"><span data-stu-id="d0cec-108">The sequential model to be used as a starting point for training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="d0cec-109">Przykłady: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="d0cec-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="d0cec-110">Zestaw etykietowych danych szkoleniowych, które zostaną użyte do przeprowadzenia szkolenia.</span><span class="sxs-lookup"><span data-stu-id="d0cec-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="d0cec-111">Opcje: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="d0cec-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="d0cec-112">Konfiguracja używana do uczenia się; Zobacz @"microsoft.quantum.machinelearning.trainingoptions" i, @"microsoft.quantum.machinelearning.defaulttrainingoptions" Aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="d0cec-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="d0cec-113">trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="d0cec-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="d0cec-114">Harmonogram próbkowania do użycia podczas wybierania próbek z danych szkoleniowych podczas wykonywania kroków szkoleniowych.</span><span class="sxs-lookup"><span data-stu-id="d0cec-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="d0cec-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="d0cec-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="d0cec-116">Harmonogram próbkowania, który ma być używany podczas wybierania próbek z danych szkoleniowych w przypadku wybrania, który punkt początkowy spowodował wynik najlepszego klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="d0cec-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="d0cec-117">Wynik: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="d0cec-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="d0cec-118">Parametryzacja danego klasyfikatora i różnica między tymi dwoma klasami, łącznie z najlepszymi wynikami z poszczególnych punktów początkowych.</span><span class="sxs-lookup"><span data-stu-id="d0cec-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="d0cec-119">Liczba chybień obserwowanych w modelu najlepszego klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="d0cec-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0cec-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d0cec-120">See Also</span></span>

- [<span data-ttu-id="d0cec-121">Microsoft. Quantum. MachineLearning. TrainSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="d0cec-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [<span data-ttu-id="d0cec-122">Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="d0cec-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)
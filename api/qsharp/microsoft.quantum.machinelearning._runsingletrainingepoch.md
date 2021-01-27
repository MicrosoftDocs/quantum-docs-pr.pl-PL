---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: Operacja _RunSingleTrainingEpoch
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: a8ae35fdd6c4e219444e7d6f7587ea31603b9999
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856180"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="0009d-102">Operacja _RunSingleTrainingEpoch</span><span class="sxs-lookup"><span data-stu-id="0009d-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="0009d-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0009d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0009d-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0009d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="0009d-105">Wykonaj jedną epokę szkolenia klasyfikatora sekwencyjnego na podzestawie próbek danych.</span><span class="sxs-lookup"><span data-stu-id="0009d-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="0009d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0009d-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="0009d-107">encodedSamples: ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="0009d-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="0009d-108">Harmonogram: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="0009d-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="0009d-109">periodScore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0009d-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0009d-110">Liczba kroków gradientu do wykonania między punktami oceniania.</span><span class="sxs-lookup"><span data-stu-id="0009d-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="0009d-111">W celu uzyskania najlepszej dokładności ustaw wartość 1.</span><span class="sxs-lookup"><span data-stu-id="0009d-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="0009d-112">Opcje: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="0009d-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="0009d-113">Opcje do użycia w szkoleniu.</span><span class="sxs-lookup"><span data-stu-id="0009d-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="0009d-114">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="0009d-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="0009d-115">Model sekwencyjny, który ma być szkolony.</span><span class="sxs-lookup"><span data-stu-id="0009d-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="0009d-116">nPreviousBestMisses: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0009d-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0009d-117">Najlepsza liczba błędnych klasyfikacji zaobserwowanych w poprzednich epokach.</span><span class="sxs-lookup"><span data-stu-id="0009d-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="0009d-118">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="0009d-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="0009d-119">Najmniejsza liczba błędnych klasyfikacji zaobserwowanych przez tę epokę.</span><span class="sxs-lookup"><span data-stu-id="0009d-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="0009d-120">Znaleziono nowy najlepszy model sekwencyjny.</span><span class="sxs-lookup"><span data-stu-id="0009d-120">The new best sequential model found.</span></span>
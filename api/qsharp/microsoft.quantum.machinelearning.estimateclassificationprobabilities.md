---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211903"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="698ee-102">EstimateClassificationProbabilities, operacja</span><span class="sxs-lookup"><span data-stu-id="698ee-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="698ee-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="698ee-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="698ee-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="698ee-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="698ee-105">Uwzględniając zestaw próbek i klasyfikator sekwencyjny, szacuje prawdopodobieństwo klasyfikacji dla tych próbek przez wielokrotne mierzenie danych wyjściowych klasyfikatora dla każdej próbki.</span><span class="sxs-lookup"><span data-stu-id="698ee-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="698ee-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="698ee-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="698ee-107">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="698ee-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="698ee-108">Tolerancja umożliwiająca kodowanie próbki do operacji przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="698ee-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="698ee-109">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="698ee-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="698ee-110">Sekwencyjny model używany do oszacowania prawdopodobieństwa klasyfikacji dla danego przykładu.</span><span class="sxs-lookup"><span data-stu-id="698ee-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="698ee-111">Przykłady: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="698ee-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="698ee-112">Tablica wektorów funkcji dla każdej próbki, która ma zostać sklasyfikowana.</span><span class="sxs-lookup"><span data-stu-id="698ee-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="698ee-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="698ee-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="698ee-114">Liczba pomiarów do użycia podczas szacowania prawdopodobieństwa klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="698ee-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="698ee-115">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="698ee-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="698ee-116">Tablica szacunków prawdopodobieństwa klasyfikacji dla każdej podanej próbki.</span><span class="sxs-lookup"><span data-stu-id="698ee-116">An array of estimates of the classification probability for each given sample.</span></span>
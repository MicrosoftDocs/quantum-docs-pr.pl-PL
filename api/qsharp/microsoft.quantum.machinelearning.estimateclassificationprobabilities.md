---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709786"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="9565c-102">EstimateClassificationProbabilities, operacja</span><span class="sxs-lookup"><span data-stu-id="9565c-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="9565c-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9565c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9565c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9565c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9565c-105">Uwzględniając zestaw próbek i klasyfikator sekwencyjny, szacuje prawdopodobieństwo klasyfikacji dla tych próbek przez wielokrotne mierzenie danych wyjściowych klasyfikatora dla każdej próbki.</span><span class="sxs-lookup"><span data-stu-id="9565c-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="9565c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9565c-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="9565c-107">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9565c-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9565c-108">Tolerancja umożliwiająca kodowanie próbki do operacji przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="9565c-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="9565c-109">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="9565c-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="9565c-110">Sekwencyjny model używany do oszacowania prawdopodobieństwa klasyfikacji dla danego przykładu.</span><span class="sxs-lookup"><span data-stu-id="9565c-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="9565c-111">Przykłady: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="9565c-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="9565c-112">Tablica wektorów funkcji dla każdej próbki, która ma zostać sklasyfikowana.</span><span class="sxs-lookup"><span data-stu-id="9565c-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="9565c-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9565c-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9565c-114">Liczba pomiarów do użycia podczas szacowania prawdopodobieństwa klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="9565c-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="9565c-115">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9565c-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9565c-116">Tablica szacunków prawdopodobieństwa klasyfikacji dla każdej podanej próbki.</span><span class="sxs-lookup"><span data-stu-id="9565c-116">An array of estimates of the classification probability for each given sample.</span></span>
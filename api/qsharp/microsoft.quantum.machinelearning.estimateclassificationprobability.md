---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: c2b74bc55ad9005a8f52d05796e856f4f2fb62ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853938"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="461f2-102">EstimateClassificationProbability, operacja</span><span class="sxs-lookup"><span data-stu-id="461f2-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="461f2-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="461f2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="461f2-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="461f2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="461f2-105">W przypadku przykładu i klasyfikatora sekwencyjnego szacuje prawdopodobieństwo klasyfikacji dla tego przykładu, wielokrotnie mierząc dane wyjściowe klasyfikatora dla danego przykładu.</span><span class="sxs-lookup"><span data-stu-id="461f2-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="461f2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="461f2-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="461f2-107">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="461f2-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="461f2-108">Tolerancja umożliwiająca kodowanie próbki do operacji przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="461f2-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="461f2-109">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="461f2-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="461f2-110">Sekwencyjny model używany do oszacowania prawdopodobieństwa klasyfikacji dla danego przykładu.</span><span class="sxs-lookup"><span data-stu-id="461f2-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="461f2-111">przykład: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="461f2-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="461f2-112">Wektor funkcji dla przykładu, który ma zostać sklasyfikowany.</span><span class="sxs-lookup"><span data-stu-id="461f2-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="461f2-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="461f2-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="461f2-114">Liczba pomiarów do użycia podczas szacowania prawdopodobieństwa klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="461f2-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="461f2-115">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="461f2-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="461f2-116">Oszacowanie prawdopodobieństwa klasyfikacji dla danego przykładu.</span><span class="sxs-lookup"><span data-stu-id="461f2-116">An estimate of the classification probability for the given sample.</span></span>
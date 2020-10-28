---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709772"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="a3b8b-102">EstimateClassificationProbability, operacja</span><span class="sxs-lookup"><span data-stu-id="a3b8b-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="a3b8b-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a3b8b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a3b8b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3b8b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3b8b-105">W przypadku przykładu i klasyfikatora sekwencyjnego szacuje prawdopodobieństwo klasyfikacji dla tego przykładu, wielokrotnie mierząc dane wyjściowe klasyfikatora dla danego przykładu.</span><span class="sxs-lookup"><span data-stu-id="a3b8b-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="a3b8b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a3b8b-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="a3b8b-107">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a3b8b-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a3b8b-108">Tolerancja umożliwiająca kodowanie próbki do operacji przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="a3b8b-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="a3b8b-109">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="a3b8b-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="a3b8b-110">Sekwencyjny model używany do oszacowania prawdopodobieństwa klasyfikacji dla danego przykładu.</span><span class="sxs-lookup"><span data-stu-id="a3b8b-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="a3b8b-111">przykład: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a3b8b-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a3b8b-112">Wektor funkcji dla przykładu, który ma zostać sklasyfikowany.</span><span class="sxs-lookup"><span data-stu-id="a3b8b-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="a3b8b-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3b8b-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3b8b-114">Liczba pomiarów do użycia podczas szacowania prawdopodobieństwa klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="a3b8b-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="a3b8b-115">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a3b8b-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a3b8b-116">Oszacowanie prawdopodobieństwa klasyfikacji dla danego przykładu.</span><span class="sxs-lookup"><span data-stu-id="a3b8b-116">An estimate of the classification probability for the given sample.</span></span>
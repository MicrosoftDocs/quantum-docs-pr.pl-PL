---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719973"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="f047f-102">EstimateGradient, operacja</span><span class="sxs-lookup"><span data-stu-id="f047f-102">EstimateGradient operation</span></span>

<span data-ttu-id="f047f-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f047f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f047f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f047f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f047f-105">Szacuje gradient szkoleniowy dla klasyfikatora sekwencyjnego w określonym modelu i dla danych wejściowych zakodowanych.</span><span class="sxs-lookup"><span data-stu-id="f047f-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="f047f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f047f-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="f047f-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="f047f-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="f047f-108">Model sekwencyjny, którego gradient ma zostać oszacowany.</span><span class="sxs-lookup"><span data-stu-id="f047f-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="f047f-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="f047f-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="f047f-110">Dane wejściowe klasyfikatora sekwencyjnego zakodowane w operacji przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="f047f-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="f047f-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f047f-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f047f-112">Liczba pomiarów do użycia podczas szacowania gradientu.</span><span class="sxs-lookup"><span data-stu-id="f047f-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="f047f-113">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f047f-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f047f-114">Oszacowanie gradientu szkoleniowego pod kątem danych wejściowych i parametrów modelu.</span><span class="sxs-lookup"><span data-stu-id="f047f-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="f047f-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f047f-115">Remarks</span></span>

<span data-ttu-id="f047f-116">Ta operacja służy do oceny gradientu przy użyciu testu Hadamard i techniki przesunięcia parametrów.</span><span class="sxs-lookup"><span data-stu-id="f047f-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>
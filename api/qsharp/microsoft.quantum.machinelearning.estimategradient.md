---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844384"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="e8489-102">EstimateGradient, operacja</span><span class="sxs-lookup"><span data-stu-id="e8489-102">EstimateGradient operation</span></span>

<span data-ttu-id="e8489-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e8489-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e8489-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e8489-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="e8489-105">Szacuje gradient szkoleniowy dla klasyfikatora sekwencyjnego w określonym modelu i dla danych wejściowych zakodowanych.</span><span class="sxs-lookup"><span data-stu-id="e8489-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="e8489-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e8489-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="e8489-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="e8489-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="e8489-108">Model sekwencyjny, którego gradient ma zostać oszacowany.</span><span class="sxs-lookup"><span data-stu-id="e8489-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="e8489-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="e8489-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="e8489-110">Dane wejściowe klasyfikatora sekwencyjnego zakodowane w operacji przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="e8489-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="e8489-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8489-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8489-112">Liczba pomiarów do użycia podczas szacowania gradientu.</span><span class="sxs-lookup"><span data-stu-id="e8489-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="e8489-113">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e8489-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e8489-114">Oszacowanie gradientu szkoleniowego pod kątem danych wejściowych i parametrów modelu.</span><span class="sxs-lookup"><span data-stu-id="e8489-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8489-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e8489-115">Remarks</span></span>

<span data-ttu-id="e8489-116">Ta operacja służy do oceny gradientu przy użyciu testu Hadamard i techniki przesunięcia parametrów.</span><span class="sxs-lookup"><span data-stu-id="e8489-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>
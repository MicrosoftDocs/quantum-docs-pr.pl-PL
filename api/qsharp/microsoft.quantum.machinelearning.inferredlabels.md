---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848405"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="2e9ea-102">InferredLabels, funkcja</span><span class="sxs-lookup"><span data-stu-id="2e9ea-102">InferredLabels function</span></span>

<span data-ttu-id="2e9ea-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2e9ea-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2e9ea-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2e9ea-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2e9ea-105">Dana tablica prawdopodobieństwa klasyfikacji i bias zwraca etykietę wywnioskowaną z każdego prawdopodobieństwa.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="2e9ea-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2e9ea-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="2e9ea-107">różnica: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2e9ea-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2e9ea-108">Różnica między dwiema klasami, zazwyczaj wynikiem szkolenia klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="2e9ea-109">prawdopodobieństwa: [Podwójna](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2e9ea-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2e9ea-110">Tablica prawdopodobieństwa klasyfikacji dla zestawu próbek zazwyczaj wynika z oszacowania częstotliwości klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="2e9ea-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2e9ea-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2e9ea-112">Etykieta wywnioskowana z każdego prawdopodobieństwa klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="2e9ea-112">The label inferred from each classification probability.</span></span>
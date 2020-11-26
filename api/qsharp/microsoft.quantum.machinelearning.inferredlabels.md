---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196365"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="0974a-102">InferredLabels, funkcja</span><span class="sxs-lookup"><span data-stu-id="0974a-102">InferredLabels function</span></span>

<span data-ttu-id="0974a-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0974a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0974a-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0974a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="0974a-105">Dana tablica prawdopodobieństwa klasyfikacji i bias zwraca etykietę wywnioskowaną z każdego prawdopodobieństwa.</span><span class="sxs-lookup"><span data-stu-id="0974a-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="0974a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0974a-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="0974a-107">różnica: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0974a-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0974a-108">Różnica między dwiema klasami, zazwyczaj wynikiem szkolenia klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="0974a-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="0974a-109">prawdopodobieństwa: [Podwójna](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0974a-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0974a-110">Tablica prawdopodobieństwa klasyfikacji dla zestawu próbek zazwyczaj wynika z oszacowania częstotliwości klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="0974a-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="0974a-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0974a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0974a-112">Etykieta wywnioskowana z każdego prawdopodobieństwa klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="0974a-112">The label inferred from each classification probability.</span></span>
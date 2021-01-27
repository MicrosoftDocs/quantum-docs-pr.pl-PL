---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848423"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="3ddc1-102">InferredLabel, funkcja</span><span class="sxs-lookup"><span data-stu-id="3ddc1-102">InferredLabel function</span></span>

<span data-ttu-id="3ddc1-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3ddc1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3ddc1-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3ddc1-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3ddc1-105">Podajesz prawdopodobieństwo klasyfikacji i bias zwraca etykietę wywnioskowaną z tego prawdopodobieństwa.</span><span class="sxs-lookup"><span data-stu-id="3ddc1-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="3ddc1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3ddc1-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="3ddc1-107">różnica: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3ddc1-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3ddc1-108">Różnica między dwiema klasami, zazwyczaj wynikiem szkolenia klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="3ddc1-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="3ddc1-109">prawdopodobieństwo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3ddc1-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3ddc1-110">Klasyfikacja prawdopodobieństwa dla konkretnej próbki zwykle wynika z oszacowania jej częstotliwości klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="3ddc1-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="3ddc1-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ddc1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ddc1-112">Etykieta wywnioskowana z danego prawdopodobieństwa klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="3ddc1-112">The label inferred from the given classification probability.</span></span>
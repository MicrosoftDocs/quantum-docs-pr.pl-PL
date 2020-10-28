---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722516"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="36c91-102">InferredLabel, funkcja</span><span class="sxs-lookup"><span data-stu-id="36c91-102">InferredLabel function</span></span>

<span data-ttu-id="36c91-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="36c91-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="36c91-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36c91-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36c91-105">Podajesz prawdopodobieństwo klasyfikacji i bias zwraca etykietę wywnioskowaną z tego prawdopodobieństwa.</span><span class="sxs-lookup"><span data-stu-id="36c91-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="36c91-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="36c91-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="36c91-107">różnica: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="36c91-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="36c91-108">Różnica między dwiema klasami, zazwyczaj wynikiem szkolenia klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="36c91-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="36c91-109">prawdopodobieństwo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="36c91-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="36c91-110">Klasyfikacja prawdopodobieństwa dla konkretnej próbki zwykle wynika z oszacowania jej częstotliwości klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="36c91-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="36c91-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36c91-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36c91-112">Etykieta wywnioskowana z danego prawdopodobieństwa klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="36c91-112">The label inferred from the given classification probability.</span></span>
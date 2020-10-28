---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Niesklasyfikowane funkcje
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723580"
---
# <a name="misclassifications-function"></a><span data-ttu-id="e427b-102">Niesklasyfikowane funkcje</span><span class="sxs-lookup"><span data-stu-id="e427b-102">Misclassifications function</span></span>

<span data-ttu-id="e427b-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e427b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e427b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e427b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e427b-105">Po otrzymaniu zestawu etykiet wywnioskowanych i zestawu prawidłowych etykiet zwraca indeksy, dla których każdy zestaw etykiet różni się.</span><span class="sxs-lookup"><span data-stu-id="e427b-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="e427b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e427b-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="e427b-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e427b-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e427b-108">Etykiety wywnioskowane dla danego szkolenia lub zestawu walidacji.</span><span class="sxs-lookup"><span data-stu-id="e427b-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="e427b-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e427b-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e427b-110">Prawdziwe etykiety dla danego szkolenia lub zestawu walidacji.</span><span class="sxs-lookup"><span data-stu-id="e427b-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="e427b-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e427b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e427b-112">Tablica indeksów `idx` , takich jak `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="e427b-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>
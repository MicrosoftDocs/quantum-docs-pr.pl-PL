---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Niesklasyfikowane funkcje
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211682"
---
# <a name="misclassifications-function"></a><span data-ttu-id="f6aff-102">Niesklasyfikowane funkcje</span><span class="sxs-lookup"><span data-stu-id="f6aff-102">Misclassifications function</span></span>

<span data-ttu-id="f6aff-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f6aff-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f6aff-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f6aff-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="f6aff-105">Po otrzymaniu zestawu etykiet wywnioskowanych i zestawu prawidłowych etykiet zwraca indeksy, dla których każdy zestaw etykiet różni się.</span><span class="sxs-lookup"><span data-stu-id="f6aff-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="f6aff-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f6aff-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="f6aff-107">inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f6aff-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f6aff-108">Etykiety wywnioskowane dla danego szkolenia lub zestawu walidacji.</span><span class="sxs-lookup"><span data-stu-id="f6aff-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="f6aff-109">actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f6aff-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f6aff-110">Prawdziwe etykiety dla danego szkolenia lub zestawu walidacji.</span><span class="sxs-lookup"><span data-stu-id="f6aff-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="f6aff-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f6aff-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f6aff-112">Tablica indeksów `idx` , takich jak `inferredLabels[idx] != actualLabels[idx]` .</span><span class="sxs-lookup"><span data-stu-id="f6aff-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>
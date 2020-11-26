---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: e910edb9bf432e6acb5c349ee6b9d65797aaaba7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211665"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="6d6d3-102">NQubitsRequired, funkcja</span><span class="sxs-lookup"><span data-stu-id="6d6d3-102">NQubitsRequired function</span></span>

<span data-ttu-id="6d6d3-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6d6d3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6d6d3-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6d6d3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="6d6d3-105">Zwraca liczbę qubits wymaganych do zastosowania danego klasyfikatora sekwencyjnego.</span><span class="sxs-lookup"><span data-stu-id="6d6d3-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="6d6d3-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6d6d3-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="6d6d3-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="6d6d3-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="6d6d3-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6d6d3-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6d6d3-109">Minimalny rozmiar rejestru, w którym można zastosować klasyfikator sekwencyjny.</span><span class="sxs-lookup"><span data-stu-id="6d6d3-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>
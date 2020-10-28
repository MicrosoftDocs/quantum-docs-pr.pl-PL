---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: d7ed687e9c75ed7cc71917aa1cdf32a6fbb93106
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723575"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="fdfeb-102">NQubitsRequired, funkcja</span><span class="sxs-lookup"><span data-stu-id="fdfeb-102">NQubitsRequired function</span></span>

<span data-ttu-id="fdfeb-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fdfeb-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="fdfeb-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fdfeb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fdfeb-105">Zwraca liczbę qubits wymaganych do zastosowania danego klasyfikatora sekwencyjnego.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="fdfeb-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fdfeb-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="fdfeb-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="fdfeb-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="fdfeb-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fdfeb-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fdfeb-109">Minimalny rozmiar rejestru, w którym można zastosować klasyfikator sekwencyjny.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>
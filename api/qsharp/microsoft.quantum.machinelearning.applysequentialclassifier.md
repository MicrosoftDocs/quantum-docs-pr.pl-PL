---
uid: Microsoft.Quantum.MachineLearning.ApplySequentialClassifier
title: ApplySequentialClassifier, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApplySequentialClassifier
qsharp.summary: Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.
ms.openlocfilehash: 1b4b4853491489f11f222507bb14b48e941e7859
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720549"
---
# <a name="applysequentialclassifier-operation"></a><span data-ttu-id="a0cdf-102">ApplySequentialClassifier, operacja</span><span class="sxs-lookup"><span data-stu-id="a0cdf-102">ApplySequentialClassifier operation</span></span>

<span data-ttu-id="a0cdf-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a0cdf-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a0cdf-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a0cdf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a0cdf-105">Mając na względzie strukturę i parametryzacja klasyfikatora sekwencyjnego, stosuje klasyfikator do rejestru qubits.</span><span class="sxs-lookup"><span data-stu-id="a0cdf-105">Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.</span></span>

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a0cdf-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a0cdf-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="a0cdf-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="a0cdf-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="a0cdf-108">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a0cdf-108">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a0cdf-109">Rejestr docelowy, do którego ma zostać zastosowany klasyfikator.</span><span class="sxs-lookup"><span data-stu-id="a0cdf-109">A target register to which the classifier should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a0cdf-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a0cdf-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


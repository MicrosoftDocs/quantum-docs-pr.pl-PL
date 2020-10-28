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
# <a name="applysequentialclassifier-operation"></a>ApplySequentialClassifier, operacja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Mając na względzie strukturę i parametryzacja klasyfikatora sekwencyjnego, stosuje klasyfikator do rejestru qubits.

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)




### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr docelowy, do którego ma zostać zastosowany klasyfikator.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


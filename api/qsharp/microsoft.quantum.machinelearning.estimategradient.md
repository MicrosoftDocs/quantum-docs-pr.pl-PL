---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719973"
---
# <a name="estimategradient-operation"></a>EstimateGradient, operacja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Szacuje gradient szkoleniowy dla klasyfikatora sekwencyjnego w określonym modelu i dla danych wejściowych zakodowanych.

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>Dane wejściowe

### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Model sekwencyjny, którego gradient ma zostać oszacowany.


### <a name="encodedinput--stategenerator"></a>encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Dane wejściowe klasyfikatora sekwencyjnego zakodowane w operacji przygotowania stanu.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Liczba pomiarów do użycia podczas szacowania gradientu.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)[]

Oszacowanie gradientu szkoleniowego pod kątem danych wejściowych i parametrów modelu.

## <a name="remarks"></a>Uwagi

Ta operacja służy do oceny gradientu przy użyciu testu Hadamard i techniki przesunięcia parametrów.
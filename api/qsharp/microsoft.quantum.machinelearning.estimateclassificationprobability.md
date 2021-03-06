---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: c2b74bc55ad9005a8f52d05796e856f4f2fb62ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853938"
---
# <a name="estimateclassificationprobability-operation"></a>EstimateClassificationProbability, operacja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


W przypadku przykładu i klasyfikatora sekwencyjnego szacuje prawdopodobieństwo klasyfikacji dla tego przykładu, wielokrotnie mierząc dane wyjściowe klasyfikatora dla danego przykładu.

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Tolerancja umożliwiająca kodowanie próbki do operacji przygotowania stanu.


### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Sekwencyjny model używany do oszacowania prawdopodobieństwa klasyfikacji dla danego przykładu.


### <a name="sample--double"></a>przykład: [Double](xref:microsoft.quantum.lang-ref.double)[]

Wektor funkcji dla przykładu, który ma zostać sklasyfikowany.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Liczba pomiarów do użycia podczas szacowania prawdopodobieństwa klasyfikacji.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)

Oszacowanie prawdopodobieństwa klasyfikacji dla danego przykładu.
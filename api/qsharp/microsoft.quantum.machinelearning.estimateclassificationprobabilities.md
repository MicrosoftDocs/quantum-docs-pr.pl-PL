---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709786"
---
# <a name="estimateclassificationprobabilities-operation"></a>EstimateClassificationProbabilities, operacja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Uwzględniając zestaw próbek i klasyfikator sekwencyjny, szacuje prawdopodobieństwo klasyfikacji dla tych próbek przez wielokrotne mierzenie danych wyjściowych klasyfikatora dla każdej próbki.

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a>Dane wejściowe

### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Tolerancja umożliwiająca kodowanie próbki do operacji przygotowania stanu.


### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Sekwencyjny model używany do oszacowania prawdopodobieństwa klasyfikacji dla danego przykładu.


### <a name="samples--double"></a>Przykłady: [Double](xref:microsoft.quantum.lang-ref.double)[] []

Tablica wektorów funkcji dla każdej próbki, która ma zostać sklasyfikowana.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Liczba pomiarów do użycia podczas szacowania prawdopodobieństwa klasyfikacji.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)[]

Tablica szacunków prawdopodobieństwa klasyfikacji dla każdej podanej próbki.
---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720444"
---
# <a name="validatesequentialclassifier-operation"></a>ValidateSequentialClassifier, operacja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Sprawdza poprawność danego klasyfikatora sekwencyjnego względem danego zestawu próbek wstępnie oznaczonych.

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a>Dane wejściowe

### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Sekwencyjny model do zweryfikowania.


### <a name="samples--labeledsample"></a>Przykłady: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Przykłady, które mają być używane do sprawdzania poprawności danego modelu.


### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Przybliżona tolerancja do użycia w kodowaniu każdego przykładu jako dane wejściowe do klasyfikatora sekwencyjnego.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Liczba pomiarów do użycia w klasyfikowaniu poszczególnych próbek.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Harmonogram, według którego próbki mają być rysowane z zestawu walidacji.



## <a name="output--validationresults"></a>Wynik: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)

Wyniki danej walidacji.
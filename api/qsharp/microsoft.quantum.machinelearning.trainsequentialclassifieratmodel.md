---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 4164c190cb19b6d3ea74d9803a77d2b19607279b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857159"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>TrainSequentialClassifierAtModel, operacja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Ze względu na strukturę klasyfikatora sekwencyjnego, pociąga klasyfikatora z danego zestawu szkoleniowego z etykietą, rozpoczynając od określonego modelu.

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Dane wejściowe

### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Sekwencyjny model, który ma być używany jako punkt wyjścia do szkoleń.


### <a name="samples--labeledsample"></a>Przykłady: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Zestaw etykietowych danych szkoleniowych, które zostaną użyte do przeprowadzenia szkolenia.


### <a name="options--trainingoptions"></a>Opcje: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Konfiguracja używana do uczenia się; Zobacz @"microsoft.quantum.machinelearning.trainingoptions" i, @"microsoft.quantum.machinelearning.defaulttrainingoptions" Aby uzyskać więcej szczegółów.


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Harmonogram próbkowania do użycia podczas wybierania próbek z danych szkoleniowych podczas wykonywania kroków szkoleniowych.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Harmonogram próbkowania, który ma być używany podczas wybierania próbek z danych szkoleniowych w przypadku wybrania, który punkt początkowy spowodował wynik najlepszego klasyfikatora.



## <a name="output--sequentialmodelint"></a>Wynik: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))

- Parametryzacja danego klasyfikatora i różnica między tymi dwoma klasami, łącznie z najlepszymi wynikami z poszczególnych punktów początkowych.
- Liczba chybień obserwowanych w modelu najlepszego klasyfikatora.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. MachineLearning. TrainSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)
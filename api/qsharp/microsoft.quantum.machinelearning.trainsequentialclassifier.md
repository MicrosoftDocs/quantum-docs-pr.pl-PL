---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: TrainSequentialClassifier, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: d0b0587ffa93141739bcd6f39324571ffc28dacc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228665"
---
# <a name="trainsequentialclassifier-operation"></a>TrainSequentialClassifier, operacja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Ze względu na strukturę klasyfikatora sekwencyjnego, pociąga klasyfikatora w danym zestawie szkoleń z etykietami.

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Dane wejściowe

### <a name="models--sequentialmodel"></a>modele: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]

Tablica modeli do użycia jako punkty wyjścia podczas szkolenia.


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

- [Microsoft. Quantum. MachineLearning. TrainSequentialClassifierAtModel](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)
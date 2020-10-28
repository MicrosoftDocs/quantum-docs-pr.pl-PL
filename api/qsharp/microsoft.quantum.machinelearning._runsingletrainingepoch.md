---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: Operacja _RunSingleTrainingEpoch
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 2b4f629eac0bd8e60bd4d86077521c60085d4809
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720633"
---
# <a name="_runsingletrainingepoch-operation"></a>Operacja _RunSingleTrainingEpoch

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Wykonaj jedną epokę szkolenia klasyfikatora sekwencyjnego na podzestawie próbek danych.

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>Dane wejściowe

### <a name="encodedsamples--labeledsamplestategenerator"></a>encodedSamples: ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []




### <a name="schedule--samplingschedule"></a>Harmonogram: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)




### <a name="periodscore--int"></a>periodScore: [int](xref:microsoft.quantum.lang-ref.int)

Liczba kroków gradientu do wykonania między punktami oceniania.
W celu uzyskania najlepszej dokładności ustaw wartość 1.


### <a name="options--trainingoptions"></a>Opcje: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Opcje do użycia w szkoleniu.


### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Model sekwencyjny, który ma być szkolony.


### <a name="npreviousbestmisses--int"></a>nPreviousBestMisses: [int](xref:microsoft.quantum.lang-ref.int)

Najlepsza liczba błędnych klasyfikacji zaobserwowanych w poprzednich epokach.



## <a name="output--intsequentialmodel"></a>Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))

- Najmniejsza liczba błędnych klasyfikacji zaobserwowanych przez tę epokę.
- Znaleziono nowy najlepszy model sekwencyjny.
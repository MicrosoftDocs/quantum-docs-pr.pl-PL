---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842780"
---
# <a name="trainingoptions-user-defined-type"></a>TrainingOptions typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Kolekcja opcji do użycia w szkoleniach klasyfikatora Quantum.

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>Nazwane elementy

### <a name="learningrate--double"></a>Wartość learningrate: [Double](xref:microsoft.quantum.lang-ref.double)

Stawka szkoleniowa, w której gradienty należy zmienić podczas aktualizowania parametrów modelu podczas wykonywania kroków szkoleniowych.
### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Przybliżona tolerancja do użycia podczas przygotowywania próbek jako Stanów Quantum.
### <a name="minibatchsize--int"></a>MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)

Liczba próbek do użycia w każdym minibatch szkoleniowym.
### <a name="nmeasurements--int"></a>NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Liczba przypadków mierzenia poszczególnych wyników klasyfikacji w celu oszacowania prawdopodobieństwa klasyfikacji.
### <a name="maxepochs--int"></a>MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)

Maksymalna liczba epok, dla których ma być nauczeni każdy model.
### <a name="maxstalls--int"></a>MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)

Maksymalna liczba przypadków, gdy Epoka szkoleniowa może się zawiesić (w przybliżeniu zero gradientu) przed awarią.
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)

Kwota do ponownego skalowania modeli zablokowanych przez przed ponowieniem próby aktualizacji.
### <a name="scoringperiod--int"></a>ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)

Liczba kroków gradientu do wykonania między punktami oceniania.
W celu uzyskania najlepszej dokładności ustaw wartość 1.
### <a name="verbosemessage--string---unit"></a>VerboseMessage: [](xref:microsoft.quantum.lang-ref.string) -> [Jednostka](xref:microsoft.quantum.lang-ref.unit) ciągu

Funkcja, która może służyć do przekazywania pełnych informacji zwrotnych.

## <a name="remarks"></a>Uwagi

Tego UDT nie należy tworzyć bezpośrednio, ale raczej należy określić przez wywołanie, @"microsoft.quantum.machinelearning.defaulttrainingoptions" a następnie użycie `w/` operatora w celu zastąpienia różnych wartości domyślnych.

Na przykład, aby użyć 100 000 pomiarów i maksymalnie 8 epoki szkoleniowej:

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>Odwołania

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)
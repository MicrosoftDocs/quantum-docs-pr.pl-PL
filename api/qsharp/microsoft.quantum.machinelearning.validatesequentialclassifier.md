---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 5174085edbfd846e8f6649f33e325fd1979ae6a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196110"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="058b0-102">ValidateSequentialClassifier, operacja</span><span class="sxs-lookup"><span data-stu-id="058b0-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="058b0-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="058b0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="058b0-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="058b0-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="058b0-105">Sprawdza poprawność danego klasyfikatora sekwencyjnego względem danego zestawu próbek wstępnie oznaczonych.</span><span class="sxs-lookup"><span data-stu-id="058b0-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="058b0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="058b0-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="058b0-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="058b0-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="058b0-108">Sekwencyjny model do zweryfikowania.</span><span class="sxs-lookup"><span data-stu-id="058b0-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="058b0-109">Przykłady: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="058b0-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="058b0-110">Przykłady, które mają być używane do sprawdzania poprawności danego modelu.</span><span class="sxs-lookup"><span data-stu-id="058b0-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="058b0-111">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="058b0-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="058b0-112">Przybliżona tolerancja do użycia w kodowaniu każdego przykładu jako dane wejściowe do klasyfikatora sekwencyjnego.</span><span class="sxs-lookup"><span data-stu-id="058b0-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="058b0-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="058b0-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="058b0-114">Liczba pomiarów do użycia w klasyfikowaniu poszczególnych próbek.</span><span class="sxs-lookup"><span data-stu-id="058b0-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="058b0-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="058b0-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="058b0-116">Harmonogram, według którego próbki mają być rysowane z zestawu walidacji.</span><span class="sxs-lookup"><span data-stu-id="058b0-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="058b0-117">Wynik: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="058b0-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="058b0-118">Wyniki danej walidacji.</span><span class="sxs-lookup"><span data-stu-id="058b0-118">The results of the given validation.</span></span>
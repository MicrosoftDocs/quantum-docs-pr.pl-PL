---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 5ecc2b5175a4e8db78f72311ac1d5ff964bae811
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722376"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="a3362-102">TrainingOptions typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="a3362-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="a3362-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a3362-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a3362-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3362-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3362-105">Kolekcja opcji do użycia w szkoleniach klasyfikatora Quantum.</span><span class="sxs-lookup"><span data-stu-id="a3362-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="a3362-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="a3362-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="a3362-107">Wartość learningrate: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a3362-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a3362-108">Stawka szkoleniowa, w której gradienty należy zmienić podczas aktualizowania parametrów modelu podczas wykonywania kroków szkoleniowych.</span><span class="sxs-lookup"><span data-stu-id="a3362-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="a3362-109">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a3362-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a3362-110">Przybliżona tolerancja do użycia podczas przygotowywania próbek jako Stanów Quantum.</span><span class="sxs-lookup"><span data-stu-id="a3362-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="a3362-111">MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3362-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3362-112">Liczba próbek do użycia w każdym minibatch szkoleniowym.</span><span class="sxs-lookup"><span data-stu-id="a3362-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="a3362-113">NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3362-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3362-114">Liczba przypadków mierzenia poszczególnych wyników klasyfikacji w celu oszacowania prawdopodobieństwa klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="a3362-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="a3362-115">MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3362-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3362-116">Maksymalna liczba epok, dla których ma być nauczeni każdy model.</span><span class="sxs-lookup"><span data-stu-id="a3362-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="a3362-117">MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3362-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3362-118">Maksymalna liczba przypadków, gdy Epoka szkoleniowa może się zawiesić (w przybliżeniu zero gradientu) przed awarią.</span><span class="sxs-lookup"><span data-stu-id="a3362-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="a3362-119">StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a3362-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a3362-120">Kwota do ponownego skalowania modeli zablokowanych przez przed ponowieniem próby aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="a3362-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="a3362-121">ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3362-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3362-122">Liczba kroków gradientu do wykonania między punktami oceniania.</span><span class="sxs-lookup"><span data-stu-id="a3362-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="a3362-123">W celu uzyskania najlepszej dokładności ustaw wartość 1.</span><span class="sxs-lookup"><span data-stu-id="a3362-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="a3362-124">VerboseMessage: [String](xref:microsoft.quantum.lang-ref.string) -> [Jednostka](xref:microsoft.quantum.lang-ref.unit) ciągu</span><span class="sxs-lookup"><span data-stu-id="a3362-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="a3362-125">Funkcja, która może służyć do przekazywania pełnych informacji zwrotnych.</span><span class="sxs-lookup"><span data-stu-id="a3362-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3362-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a3362-126">Remarks</span></span>

<span data-ttu-id="a3362-127">Tego UDT nie należy tworzyć bezpośrednio, ale raczej należy określić przez wywołanie, @"microsoft.quantum.machinelearning.defaulttrainingoptions" a następnie użycie `w/` operatora w celu zastąpienia różnych wartości domyślnych.</span><span class="sxs-lookup"><span data-stu-id="a3362-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="a3362-128">Na przykład, aby użyć 100 000 pomiarów i maksymalnie 8 epoki szkoleniowej:</span><span class="sxs-lookup"><span data-stu-id="a3362-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="a3362-129">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="a3362-129">References</span></span>

- [<span data-ttu-id="a3362-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="a3362-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)
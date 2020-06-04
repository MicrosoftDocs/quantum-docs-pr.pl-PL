---
title: Podstawowa Klasyfikacja z biblioteką Machine Learning Quantum
description: 'Dowiedz się, jak wykonać klasyfikator sekwencyjny Quantum zapisany w Q # przy użyciu biblioteki Quantum Machine Learning w QDK firmy Microsoft.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: ddd889fdfabb505d7118c1eff551a6fbfa757309
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327649"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="eb07b-103">Podstawowa Klasyfikacja: klasyfikowanie danych za pomocą QDK</span><span class="sxs-lookup"><span data-stu-id="eb07b-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="eb07b-104">W tym przewodniku szybki start dowiesz się, jak wykonać klasyfikator sekwencyjny Quantum zapisany w Q # przy użyciu biblioteki Quantum Machine Learning QDK.</span><span class="sxs-lookup"><span data-stu-id="eb07b-104">In this Quickstart, you will learn how to execute a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="eb07b-105">W tym przewodniku użyjemy zestawu danych o połowie księżyca przy użyciu struktury klasyfikatora zdefiniowanej w Q #.</span><span class="sxs-lookup"><span data-stu-id="eb07b-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb07b-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="eb07b-106">Prerequisites</span></span>

- <span data-ttu-id="eb07b-107">Zestaw Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="eb07b-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="eb07b-108">Utwórz projekt Q # dla [programu hosta Python](xref:microsoft.quantum.install.python) lub [programu hosta języka C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="eb07b-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="eb07b-109">Program hosta</span><span class="sxs-lookup"><span data-stu-id="eb07b-109">Host program</span></span>

<span data-ttu-id="eb07b-110">Program hosta składa się z trzech części:</span><span class="sxs-lookup"><span data-stu-id="eb07b-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="eb07b-111">Załaduj zestaw danych i wybierz zestaw parametrów uruchamiania dla modelu.</span><span class="sxs-lookup"><span data-stu-id="eb07b-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="eb07b-112">Wykonaj szkolenie, aby określić parametry i odchylenia modelu.</span><span class="sxs-lookup"><span data-stu-id="eb07b-112">Execute training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="eb07b-113">Weryfikowanie modelu w celu określenia jego dokładności</span><span class="sxs-lookup"><span data-stu-id="eb07b-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="eb07b-114">Język Python z programem Visual Studio Code lub wierszem polecenia</span><span class="sxs-lookup"><span data-stu-id="eb07b-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="eb07b-115">Aby uruchomić, jesteś klasyfikatorem Q # z języka Python, Zapisz Poniższy kod jako `host.py` .</span><span class="sxs-lookup"><span data-stu-id="eb07b-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="eb07b-116">Należy pamiętać, że wymagany jest również plik Q # `Training.qs` opisany w dalszej części tego samouczka.</span><span class="sxs-lookup"><span data-stu-id="eb07b-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="eb07b-117">Następnie możesz uruchomić program hosta języka Python z poziomu wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="eb07b-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="eb07b-118">Język C# z programem Visual Studio Code lub wierszem polecenia</span><span class="sxs-lookup"><span data-stu-id="eb07b-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="eb07b-119">Aby uruchomić, jesteś klasyfikatorem Q # z C#, Zapisz Poniższy kod jako `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="eb07b-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="eb07b-120">Należy pamiętać, że wymagany jest również plik Q # `Training.qs` opisany w dalszej części tego samouczka.</span><span class="sxs-lookup"><span data-stu-id="eb07b-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="eb07b-121">Następnie możesz uruchomić program hosta języka C# z poziomu wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="eb07b-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="eb07b-122">Język C# w programie Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="eb07b-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="eb07b-123">Aby uruchomić nowy program Q # z poziomu języka C# w programie Visual Studio, należy zmodyfikować, `Host.cs` Aby uwzględnić Poniższy kod w języku C#.</span><span class="sxs-lookup"><span data-stu-id="eb07b-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="eb07b-124">Należy pamiętać, że wymagany jest również plik Q # `Training.qs` opisany w dalszej części tego samouczka.</span><span class="sxs-lookup"><span data-stu-id="eb07b-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="eb07b-125">Następnie naciśnij klawisz F5. Program zacznie działać i pojawią się nowe okna z następującymi wynikami:</span><span class="sxs-lookup"><span data-stu-id="eb07b-125">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="eb07b-126">\#Kod klasyfikatora Q</span><span class="sxs-lookup"><span data-stu-id="eb07b-126">Q\# classifier code</span></span>

<span data-ttu-id="eb07b-127">Teraz zobaczmy, jak operacje wywoływane przez program hosta są zdefiniowane w Q #.</span><span class="sxs-lookup"><span data-stu-id="eb07b-127">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="eb07b-128">Zapiszemy następujący kod w pliku o nazwie `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="eb07b-128">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="eb07b-129">Najważniejsze funkcje i operacje zdefiniowane w powyższym kodzie są następujące:</span><span class="sxs-lookup"><span data-stu-id="eb07b-129">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="eb07b-130">`ClassifierStructure() : ControlledRotation[]`: w tej funkcji ustawimy strukturę modelu obwodu przez dodanie warstw kontrolowanej bramy.</span><span class="sxs-lookup"><span data-stu-id="eb07b-130">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="eb07b-131">Ten krok jest analogiczny do deklaracji warstw neurons w modelu uczenia głębokiego.</span><span class="sxs-lookup"><span data-stu-id="eb07b-131">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="eb07b-132">`TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)`: Ta operacja jest podstawową częścią kodu i definiuje szkolenie.</span><span class="sxs-lookup"><span data-stu-id="eb07b-132">`TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="eb07b-133">Tutaj ładujemy przykłady z zestawu danych zawartego w bibliotece, ustawimy parametry funkcji Hyper-i początkowe parametry szkolenia i zaczniemy szkolenie przez wywołanie operacji `TrainSequentialClassifier` zawartej w bibliotece.</span><span class="sxs-lookup"><span data-stu-id="eb07b-133">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="eb07b-134">Zwraca parametry i bias określające klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="eb07b-134">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="eb07b-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: Ta operacja definiuje proces walidacji w celu oszacowania modelu.</span><span class="sxs-lookup"><span data-stu-id="eb07b-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="eb07b-136">Tutaj ładujemy próbki do walidacji, liczbę pomiarów na próbkę i tolerancję.</span><span class="sxs-lookup"><span data-stu-id="eb07b-136">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="eb07b-137">Zwraca liczbę błędów klasyfikacji na wybranej partii próbek do walidacji.</span><span class="sxs-lookup"><span data-stu-id="eb07b-137">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="eb07b-138">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="eb07b-138">Next steps</span></span>

<span data-ttu-id="eb07b-139">Najpierw można zagrać z kodem i próbować zmienić niektóre parametry, aby zobaczyć, jak ma to wpływ na szkolenie.</span><span class="sxs-lookup"><span data-stu-id="eb07b-139">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="eb07b-140">Następnie w następnym samouczku [Zaprojektuj własny klasyfikator](xref:microsoft.quantum.libraries.machine-learning.design), dowiesz się, jak zdefiniować strukturę klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="eb07b-140">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>

---
title: Programowanie w języku Q# przy użyciu notesów Jupyter Notebook
description: Dowiedz się, jak utworzyć aplikację Q# przy użyciu notesów Jupyter.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51de510907ea087d1f23d3ff65d268d6d455a493
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834316"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a><span data-ttu-id="a11ad-103">Programowanie w języku Q# przy użyciu notesów Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="a11ad-103">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="a11ad-104">Zainstaluj zestaw QDK na potrzeby opracowywania operacji języka Q# w notesach Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="a11ad-104">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="a11ad-105">Notesy Jupyter zapewniają możliwość obliczania kodu w miejscu, a także instrukcje, notatki i inną zawartość.</span><span class="sxs-lookup"><span data-stu-id="a11ad-105">Jupyter Notebooks allow in-place code computation alongside instructions, notes, and other content.</span></span> <span data-ttu-id="a11ad-106">Jest to idealne środowisko do pisania kodu Q# z osadzonymi wyjaśnieniami lub interaktywnych samouczków wykonywania obliczeń kwantowych.</span><span class="sxs-lookup"><span data-stu-id="a11ad-106">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="a11ad-107">Oto jak zacząć tworzenie własnych notesów języka Q#.</span><span class="sxs-lookup"><span data-stu-id="a11ad-107">Here's what you need to do to start creating your own Q# notebooks.</span></span>

## <a name="install-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="a11ad-108">Instalowanie jądra Jupyter IQ#</span><span class="sxs-lookup"><span data-stu-id="a11ad-108">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="a11ad-109">IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie zestawu .NET Core SDK używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="a11ad-109">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="a11ad-110">Instalowanie przy użyciu środowiska conda (zalecane)</span><span class="sxs-lookup"><span data-stu-id="a11ad-110">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="a11ad-111">Zainstaluj narzędzie [Miniconda](https://docs.conda.io/en/latest/miniconda.html) lub [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="a11ad-111">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="a11ad-112">**Uwaga:** Wymagana jest instalacja 64-bitowa.</span><span class="sxs-lookup"><span data-stu-id="a11ad-112">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="a11ad-113">Otwórz program Anaconda Prompt.</span><span class="sxs-lookup"><span data-stu-id="a11ad-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="a11ad-114">Lub, jeśli wolisz używać programu PowerShell albo pwsh: otwórz powłokę, uruchom polecenie `conda init powershell`, a następnie zamknij i ponownie otwórz powłokę.</span><span class="sxs-lookup"><span data-stu-id="a11ad-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="a11ad-115">Utwórz i aktywuj nowe środowisko conda o nazwie `qsharp-env` z wymaganymi pakietami (w tym Jupyter Notebook i IQ#), uruchamiając następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="a11ad-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="a11ad-116">Uruchom polecenie `python -c "import qsharp"` z tego samego terminalu, aby zweryfikować instalację i wypełnić pamięć podręczną pakietów lokalnych wszystkimi wymaganymi składnikami zestawu QDK.</span><span class="sxs-lookup"><span data-stu-id="a11ad-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="a11ad-117">Instalowanie przy użyciu interfejsu wiersza polecenia platformy .NET (zaawansowane)</span><span class="sxs-lookup"><span data-stu-id="a11ad-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="a11ad-118">Wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="a11ad-118">Prerequisites:</span></span>

    - <span data-ttu-id="a11ad-119">Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="a11ad-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="a11ad-120">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="a11ad-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="a11ad-121">Zestaw .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="a11ad-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="a11ad-122">Zainstaluj pakiet `Microsoft.Quantum.IQSharp`.</span><span class="sxs-lookup"><span data-stu-id="a11ad-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> <span data-ttu-id="a11ad-123">Jeśli w kroku `dotnet iqsharp install` wystąpił błąd, otwórz nowe okno terminalu i spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="a11ad-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
> <span data-ttu-id="a11ad-124">Jeśli to nadal nie działa, spróbuj znaleźć zainstalowane narzędzie `dotnet-iqsharp` (w systemie Windows `dotnet-iqsharp.exe`) i uruchomić następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="a11ad-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> <span data-ttu-id="a11ad-125">gdzie `/path/to/dotnet-iqsharp` należy zastąpić ścieżką bezwzględną narzędzia `dotnet-iqsharp` w systemie plików.</span><span class="sxs-lookup"><span data-stu-id="a11ad-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
> <span data-ttu-id="a11ad-126">Zwykle znajduje się ono w podfolderze `.dotnet/tools` w folderze profilu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a11ad-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="a11ad-127">Gotowe.</span><span class="sxs-lookup"><span data-stu-id="a11ad-127">That's it!</span></span> <span data-ttu-id="a11ad-128">Masz teraz jądro IQ# dla środowiska Jupyter, które udostępnia podstawowe funkcje kompilowania i uruchamiania operacji języka Q# z poziomu notesów Jupyter języka Q#.</span><span class="sxs-lookup"><span data-stu-id="a11ad-128">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and running Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-no-locq-notebook"></a><span data-ttu-id="a11ad-129">Tworzenie pierwszego notesu języka Q#</span><span class="sxs-lookup"><span data-stu-id="a11ad-129">Create your first Q# notebook</span></span>

<span data-ttu-id="a11ad-130">Teraz możesz zweryfikować instalację notesu Jupyter języka Q#, pisząc i uruchamiając prostą operację w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="a11ad-130">Now you are ready to verify your Q# Jupyter Notebook installation by writing and running a simple Q# operation.</span></span>

1. <span data-ttu-id="a11ad-131">Ze środowiska utworzonego podczas instalacji (tj. utworzonego środowiska conda lub środowiska języka Python, w którym zainstalowano pakiet Jupyter) uruchom następujące polecenie, aby uruchomić serwer notesu Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="a11ad-131">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="a11ad-132">Jeśli notes Jupyter Notebook nie zostanie otwarty automatycznie w przeglądarce, skopiuj i wklej adres URL otrzymany w wierszu polecenia do okna przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="a11ad-132">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="a11ad-133">Wybierz pozycję **New → Q#** (Nowy → Q#), aby utworzyć notes Jupyter z jądrem Q#, i dodaj następujący kod do pierwszej komórki notesu:</span><span class="sxs-lookup"><span data-stu-id="a11ad-133">Choose **New → Q#** to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="a11ad-134">Uruchom tę komórkę notesu:</span><span class="sxs-lookup"><span data-stu-id="a11ad-134">Run this cell of the notebook:</span></span>

    ![Komórka notesu Jupyter Notebook z kodem języka Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="a11ad-136">W danych wyjściowych komórki powinien zostać wyświetlony element `SampleQuantumRandomNumberGenerator`.</span><span class="sxs-lookup"><span data-stu-id="a11ad-136">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="a11ad-137">W przypadku uruchamiania w notesach Jupyter Notebook kod Q# jest kompilowany, a komórka zwraca w danych wyjściowych nazwy wszystkich znalezionych operacji.</span><span class="sxs-lookup"><span data-stu-id="a11ad-137">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="a11ad-138">W nowej komórce uruchom utworzoną operację w symulatorze za pomocą polecenia `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="a11ad-138">In a new cell, run the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Komórka notesu Jupyter Notebook z poleceniem magic %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="a11ad-140">Powinien zostać wyświetlony wynik wywołanej operacji.</span><span class="sxs-lookup"><span data-stu-id="a11ad-140">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="a11ad-141">W tym przypadku, ponieważ operacja generuje losowy wynik, na ekranie zostanie wyświetlona wartość `Zero` lub `One`.</span><span class="sxs-lookup"><span data-stu-id="a11ad-141">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="a11ad-142">W przypadku wielokrotnego uruchamiania komórki każdy wynik powinien być wyświetlany w przybliżeniu przez połowę czasu.</span><span class="sxs-lookup"><span data-stu-id="a11ad-142">If you run the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a11ad-143">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="a11ad-143">Next steps</span></span>

<span data-ttu-id="a11ad-144">Po zainstalowaniu zestawu QDK na potrzeby notesów Jupyter Notebook języka Q# możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng), pisząc kod języka Q# bezpośrednio w środowisku Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="a11ad-144">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="a11ad-145">Aby znaleźć więcej przykładów zastosowań notesów Jupyter Notebook języka Q#, zobacz:</span><span class="sxs-lookup"><span data-stu-id="a11ad-145">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="a11ad-146">[Wprowadzenie do języka Q# i notesów Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="a11ad-146">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="a11ad-147">Tam znajdziesz notes Jupyter Notebook języka Q# zawierający więcej szczegółów dotyczących tego, jak używać języka Q# w środowisku Jupyter.</span><span class="sxs-lookup"><span data-stu-id="a11ad-147">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="a11ad-148">[Quantum Katas](xref:microsoft.quantum.overview.katas) to kolekcja typu open-source zawierająca realizowane samodzielnie samouczki oraz zestawy ćwiczeń programistycznych w formie notesów Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="a11ad-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="a11ad-149">[Notesy samouczków Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) to dobry sposób, aby zacząć.</span><span class="sxs-lookup"><span data-stu-id="a11ad-149">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="a11ad-150">Celem samouczków Quantum Katas jest połączenie nauki elementów obliczeń kwantowych i tworzenia zawartości w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="a11ad-150">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="a11ad-151">To doskonały przykład zawartości, którą można tworzyć za pomocą notesów Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="a11ad-151">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>

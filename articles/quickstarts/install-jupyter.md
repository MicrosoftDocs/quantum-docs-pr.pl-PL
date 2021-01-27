---
title: Programowanie w języku Q# przy użyciu notesów Jupyter Notebook
description: Dowiedz się, jak utworzyć aplikację Q# przy użyciu notesów Jupyter.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4cef9b7252a2199b2ea995c4cf819a3582d9ca8f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844294"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a><span data-ttu-id="b6870-103">Programowanie w języku Q# przy użyciu notesów Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="b6870-103">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="b6870-104">Zainstaluj zestaw QDK na potrzeby opracowywania operacji języka Q# w notesach Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="b6870-104">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="b6870-105">Notesy Jupyter Notebook umożliwiają uruchamianie kodu w miejscu, a także instrukcje, notatki i inną zawartość.</span><span class="sxs-lookup"><span data-stu-id="b6870-105">Jupyter Notebooks allow running code in-place alongside instructions, notes, and other content.</span></span> <span data-ttu-id="b6870-106">Jest to idealne środowisko do pisania kodu Q# z osadzonymi wyjaśnieniami lub interaktywnych samouczków wykonywania obliczeń kwantowych.</span><span class="sxs-lookup"><span data-stu-id="b6870-106">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="b6870-107">Oto jak zacząć tworzenie własnych notesów języka Q#.</span><span class="sxs-lookup"><span data-stu-id="b6870-107">Here's what you need to do to start creating your own Q# notebooks.</span></span>

## <a name="install-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="b6870-108">Instalowanie jądra Jupyter IQ#</span><span class="sxs-lookup"><span data-stu-id="b6870-108">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="b6870-109">IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie zestawu .NET Core SDK używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="b6870-109">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="b6870-110">Instalowanie przy użyciu środowiska conda (zalecane)</span><span class="sxs-lookup"><span data-stu-id="b6870-110">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="b6870-111">Zainstaluj narzędzie [Miniconda](https://docs.conda.io/en/latest/miniconda.html) lub [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="b6870-111">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="b6870-112">**Uwaga:** Wymagana jest instalacja 64-bitowa.</span><span class="sxs-lookup"><span data-stu-id="b6870-112">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="b6870-113">Otwórz program Anaconda Prompt.</span><span class="sxs-lookup"><span data-stu-id="b6870-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="b6870-114">Lub, jeśli wolisz używać programu PowerShell albo pwsh: otwórz powłokę, uruchom polecenie `conda init powershell`, a następnie zamknij i ponownie otwórz powłokę.</span><span class="sxs-lookup"><span data-stu-id="b6870-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="b6870-115">Utwórz i aktywuj nowe środowisko conda o nazwie `qsharp-env` z wymaganymi pakietami (w tym Jupyter Notebook i IQ#), uruchamiając następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="b6870-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="b6870-116">Uruchom polecenie `python -c "import qsharp"` z tego samego terminalu, aby zweryfikować instalację i wypełnić pamięć podręczną pakietów lokalnych wszystkimi wymaganymi składnikami zestawu QDK.</span><span class="sxs-lookup"><span data-stu-id="b6870-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="b6870-117">Instalowanie przy użyciu interfejsu wiersza polecenia platformy .NET (zaawansowane)</span><span class="sxs-lookup"><span data-stu-id="b6870-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="b6870-118">Wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="b6870-118">Prerequisites:</span></span>

    - <span data-ttu-id="b6870-119">Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="b6870-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="b6870-120">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="b6870-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="b6870-121">Zestaw .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="b6870-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="b6870-122">Zainstaluj pakiet `Microsoft.Quantum.IQSharp`.</span><span class="sxs-lookup"><span data-stu-id="b6870-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> <span data-ttu-id="b6870-123">Jeśli w kroku `dotnet iqsharp install` wystąpił błąd, otwórz nowe okno terminalu i spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="b6870-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
> <span data-ttu-id="b6870-124">Jeśli to nadal nie działa, spróbuj znaleźć zainstalowane narzędzie `dotnet-iqsharp` (w systemie Windows `dotnet-iqsharp.exe`) i uruchomić następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="b6870-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> <span data-ttu-id="b6870-125">gdzie `/path/to/dotnet-iqsharp` należy zastąpić ścieżką bezwzględną narzędzia `dotnet-iqsharp` w systemie plików.</span><span class="sxs-lookup"><span data-stu-id="b6870-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
> <span data-ttu-id="b6870-126">Zwykle znajduje się ono w podfolderze `.dotnet/tools` w folderze profilu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b6870-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
<span data-ttu-id="b6870-127">\*\*_</span><span class="sxs-lookup"><span data-stu-id="b6870-127">\*\*_</span></span>

<span data-ttu-id="b6870-128">Gotowe.</span><span class="sxs-lookup"><span data-stu-id="b6870-128">That's it!</span></span> <span data-ttu-id="b6870-129">Masz teraz jądro IQ# dla środowiska Jupyter, które udostępnia podstawowe funkcje kompilowania i uruchamiania operacji języka Q# z poziomu notesów Jupyter języka Q#.</span><span class="sxs-lookup"><span data-stu-id="b6870-129">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and running Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-no-locq-notebook"></a><span data-ttu-id="b6870-130">Tworzenie pierwszego notesu języka Q#</span><span class="sxs-lookup"><span data-stu-id="b6870-130">Create your first Q# notebook</span></span>

<span data-ttu-id="b6870-131">Teraz możesz zweryfikować instalację notesu Jupyter języka Q#, pisząc i uruchamiając prostą operację w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="b6870-131">Now you are ready to verify your Q# Jupyter Notebook installation by writing and running a simple Q# operation.</span></span>

1. <span data-ttu-id="b6870-132">Ze środowiska utworzonego podczas instalacji (tj. utworzonego środowiska conda lub środowiska języka Python, w którym zainstalowano pakiet Jupyter) uruchom następujące polecenie, aby uruchomić serwer notesu Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="b6870-132">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="b6870-133">Jeśli notes Jupyter Notebook nie zostanie otwarty automatycznie w przeglądarce, skopiuj i wklej adres URL otrzymany w wierszu polecenia do okna przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="b6870-133">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="b6870-134">Wybierz _ \*New → Q#\*\*, aby utworzyć Jupyter notebook z Q# jądrem, i Dodaj następujący kod do pierwszej komórki notesu:</span><span class="sxs-lookup"><span data-stu-id="b6870-134">Choose _ *New → Q#*\* to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="b6870-135">Uruchom tę komórkę notesu:</span><span class="sxs-lookup"><span data-stu-id="b6870-135">Run this cell of the notebook:</span></span>

    ![Komórka notesu Jupyter Notebook z kodem języka Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="b6870-137">W danych wyjściowych komórki powinien zostać wyświetlony element `SampleQuantumRandomNumberGenerator`.</span><span class="sxs-lookup"><span data-stu-id="b6870-137">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="b6870-138">W przypadku uruchamiania w notesach Jupyter Notebook kod Q# jest kompilowany, a komórka zwraca w danych wyjściowych nazwy wszystkich znalezionych operacji.</span><span class="sxs-lookup"><span data-stu-id="b6870-138">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="b6870-139">W nowej komórce uruchom utworzoną operację w symulatorze za pomocą polecenia `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="b6870-139">In a new cell, run the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Komórka notesu Jupyter Notebook z poleceniem magic %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="b6870-141">Powinien zostać wyświetlony wynik wywołanej operacji.</span><span class="sxs-lookup"><span data-stu-id="b6870-141">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="b6870-142">W tym przypadku, ponieważ operacja generuje losowy wynik, na ekranie zostanie wyświetlona wartość `Zero` lub `One`.</span><span class="sxs-lookup"><span data-stu-id="b6870-142">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="b6870-143">W przypadku wielokrotnego uruchamiania komórki każdy wynik powinien być wyświetlany w przybliżeniu przez połowę czasu.</span><span class="sxs-lookup"><span data-stu-id="b6870-143">If you run the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b6870-144">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="b6870-144">Next steps</span></span>

<span data-ttu-id="b6870-145">Po zainstalowaniu zestawu QDK na potrzeby notesów Jupyter Notebook języka Q# możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng), pisząc kod języka Q# bezpośrednio w środowisku Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="b6870-145">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="b6870-146">Aby znaleźć więcej przykładów zastosowań notesów Jupyter Notebook języka Q#, zobacz:</span><span class="sxs-lookup"><span data-stu-id="b6870-146">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="b6870-147">[Wprowadzenie do języka Q# i notesów Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="b6870-147">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="b6870-148">Tam znajdziesz notes Jupyter Notebook języka Q# zawierający więcej szczegółów dotyczących tego, jak używać języka Q# w środowisku Jupyter.</span><span class="sxs-lookup"><span data-stu-id="b6870-148">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="b6870-149">[Quantum Katas](xref:microsoft.quantum.overview.katas) to kolekcja typu open-source zawierająca realizowane samodzielnie samouczki oraz zestawy ćwiczeń programistycznych w formie notesów Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="b6870-149">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="b6870-150">[Notesy samouczków Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) to dobry sposób, aby zacząć.</span><span class="sxs-lookup"><span data-stu-id="b6870-150">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="b6870-151">Celem samouczków Quantum Katas jest połączenie nauki elementów obliczeń kwantowych i tworzenia zawartości w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="b6870-151">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="b6870-152">To doskonały przykład zawartości, którą można tworzyć za pomocą notesów Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="b6870-152">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>

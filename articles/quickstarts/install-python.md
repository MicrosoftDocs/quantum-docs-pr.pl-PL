---
title: Programowanie przy użyciu języków Q# i Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: 01a5c31a7a920a69f4f90701d370f3a772d2c4d2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866744"
---
# <a name="develop-with-no-locq-and-python"></a><span data-ttu-id="6fa46-102">Programowanie przy użyciu języków Q# i Python</span><span class="sxs-lookup"><span data-stu-id="6fa46-102">Develop with Q# and Python</span></span>

<span data-ttu-id="6fa46-103">Zainstaluj zestaw QDK, aby tworzyć programy hosta w języku Python umożliwiające wywoływanie operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="6fa46-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="6fa46-104">Instalowanie pakietu `qsharp` języka Python</span><span class="sxs-lookup"><span data-stu-id="6fa46-104">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="6fa46-105">Instalowanie przy użyciu środowiska conda (zalecane)</span><span class="sxs-lookup"><span data-stu-id="6fa46-105">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="6fa46-106">Zainstaluj narzędzie [Miniconda](https://docs.conda.io/en/latest/miniconda.html) lub [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="6fa46-106">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="6fa46-107">**Uwaga:** Wymagana jest instalacja 64-bitowa.</span><span class="sxs-lookup"><span data-stu-id="6fa46-107">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="6fa46-108">Otwórz program Anaconda Prompt.</span><span class="sxs-lookup"><span data-stu-id="6fa46-108">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="6fa46-109">Lub, jeśli wolisz używać programu PowerShell albo pwsh: otwórz powłokę, uruchom polecenie `conda init powershell`, a następnie zamknij i ponownie otwórz powłokę.</span><span class="sxs-lookup"><span data-stu-id="6fa46-109">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="6fa46-110">Utwórz i aktywuj nowe środowisko conda o nazwie `qsharp-env` z wymaganymi pakietami (w tym Jupyter Notebook i IQ#), uruchamiając następujące polecenia:</span><span class="sxs-lookup"><span data-stu-id="6fa46-110">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="6fa46-111">Uruchom polecenie `python -c "import qsharp"` z tego samego terminalu, aby zweryfikować instalację i wypełnić pamięć podręczną pakietów lokalnych wszystkimi wymaganymi składnikami zestawu QDK.</span><span class="sxs-lookup"><span data-stu-id="6fa46-111">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="6fa46-112">Instalowanie przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP (zaawansowane)</span><span class="sxs-lookup"><span data-stu-id="6fa46-112">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="6fa46-113">Wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="6fa46-113">Prerequisites:</span></span>

    - <span data-ttu-id="6fa46-114">Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="6fa46-114">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="6fa46-115">Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="6fa46-115">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="6fa46-116">Zestaw .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="6fa46-116">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="6fa46-117">Zainstaluj `qsharp`, pakiet języka Python, który umożliwia współdziałanie między językami Q# i Python.</span><span class="sxs-lookup"><span data-stu-id="6fa46-117">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="6fa46-118">Zainstaluj IQ#, jądro używane w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i wykonywania operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="6fa46-118">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="6fa46-119">Jeśli w kroku `dotnet iqsharp install` wystąpił błąd, otwórz nowe okno terminalu i spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="6fa46-119">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="6fa46-120">Jeśli to nadal nie działa, spróbuj znaleźć zainstalowane narzędzie `dotnet-iqsharp` (w systemie Windows `dotnet-iqsharp.exe`) i uruchomić następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="6fa46-120">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="6fa46-121">gdzie `/path/to/dotnet-iqsharp` należy zastąpić ścieżką bezwzględną narzędzia `dotnet-iqsharp` w systemie plików.</span><span class="sxs-lookup"><span data-stu-id="6fa46-121">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="6fa46-122">Zwykle znajduje się ono w podfolderze `.dotnet/tools` w folderze profilu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6fa46-122">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="6fa46-123">Gotowe.</span><span class="sxs-lookup"><span data-stu-id="6fa46-123">That's it!</span></span> <span data-ttu-id="6fa46-124">Masz teraz zarówno pakiet `qsharp` języka Python, jak i jądro IQ# dla środowiska Jupyter, które udostępnia podstawowe funkcje kompilowania i wykonywania operacji języka Q# z poziomu środowiska Python i umożliwia korzystanie z notesów Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="6fa46-124">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="6fa46-125">Wybieranie środowiska IDE</span><span class="sxs-lookup"><span data-stu-id="6fa46-125">Choose your IDE</span></span>

<span data-ttu-id="6fa46-126">Chociaż języka Q# wraz z językiem Python można używać w dowolnym środowisku IDE, zdecydowanie zalecamy korzystanie z programu Visual Studio Code (VS Code) jako środowiska IDE na potrzeby aplikacji tworzonych przy użyciu języków Q# i Python.</span><span class="sxs-lookup"><span data-stu-id="6fa46-126">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="6fa46-127">Dzięki rozszerzeniu QDK programu Visual Studio Code uzyskasz dostęp do bogatszej funkcjonalności, takiej jak ostrzeżenia, wyróżnianie składni, szablony projektów i inne.</span><span class="sxs-lookup"><span data-stu-id="6fa46-127">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="6fa46-128">Jeśli chcesz użyć programu VS Code:</span><span class="sxs-lookup"><span data-stu-id="6fa46-128">If you would like to use VS Code:</span></span>

- <span data-ttu-id="6fa46-129">Zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac).</span><span class="sxs-lookup"><span data-stu-id="6fa46-129">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="6fa46-130">Zainstaluj [rozszerzenie QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="6fa46-130">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="6fa46-131">Jeśli chcesz użyć innego edytora, powyższe instrukcje przygotują Cię do wszystkiego.</span><span class="sxs-lookup"><span data-stu-id="6fa46-131">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-no-locq-program"></a><span data-ttu-id="6fa46-132">Pisanie pierwszego programu w języku Q#</span><span class="sxs-lookup"><span data-stu-id="6fa46-132">Write your first Q# program</span></span>

<span data-ttu-id="6fa46-133">Teraz możesz już zweryfikować instalację pakietu `qsharp` języka Python, pisząc i wykonując prosty program w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="6fa46-133">Now you are ready to verify your `qsharp` Python package installation by writing and executing a simple Q# program.</span></span>

1. <span data-ttu-id="6fa46-134">Utwórz minimalną operację języka Q#, tworząc plik o nazwie `Operation.qs` i dodając do niego następujący kod:</span><span class="sxs-lookup"><span data-stu-id="6fa46-134">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="6fa46-135">W tym samym folderze, w którym znajduje się plik `Operation.qs`, utwórz program w języku Python o nazwie `host.py`, aby symulować operację `SampleQuantumRandomNumberGenerator()` języka Q#:</span><span class="sxs-lookup"><span data-stu-id="6fa46-135">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="6fa46-136">Ze środowiska utworzonego podczas instalacji (tj. środowiska conda lub środowiska języka Python, w którym zainstalowano element `qsharp`), uruchom program:</span><span class="sxs-lookup"><span data-stu-id="6fa46-136">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="6fa46-137">Powinien zostać wyświetlony wynik wywołanej operacji.</span><span class="sxs-lookup"><span data-stu-id="6fa46-137">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="6fa46-138">W tym przypadku, ponieważ operacja generuje losowy wynik, na ekranie zostanie wyświetlona wartość `0` lub `1`.</span><span class="sxs-lookup"><span data-stu-id="6fa46-138">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="6fa46-139">W przypadku wielokrotnego uruchamiania programu każdy wynik powinien być wyświetlany przez w przybliżeniu połowę czasu.</span><span class="sxs-lookup"><span data-stu-id="6fa46-139">If you execute the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="6fa46-140">Ten kod języka Python to zwykły program w języku Python.</span><span class="sxs-lookup"><span data-stu-id="6fa46-140">The Python code is just a normal Python program.</span></span> <span data-ttu-id="6fa46-141">Możesz użyć dowolnego środowiska języka Python, w tym notesów Jupyter Notebook opartych na języku Python, aby napisać program w języku Python i wywołać operacje języka Q#.</span><span class="sxs-lookup"><span data-stu-id="6fa46-141">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="6fa46-142">Program w języku Python może zaimportować operacje języka Q# z dowolnych plików qs znajdujących się w tym samym folderze co sam kod języka Python.</span><span class="sxs-lookup"><span data-stu-id="6fa46-142">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6fa46-143">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="6fa46-143">Next steps</span></span>

<span data-ttu-id="6fa46-144">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz postępować zgodnie z tym samouczkiem, aby napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="6fa46-144">Now that you have installed the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

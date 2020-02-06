---
title: 'Dowiedz się, jak utworzyć projekt Q # przy użyciu zestawu Quantum Development Kit (QDK)'
description: 'Zainicjuj projekt dla rozwoju Quantum przy użyciu QDK i Q # w wybranym środowisku programistycznym'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: c093284f1ea33b72d4d264992b0ba6bf6bc72782
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036444"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="2e282-103">Tworzenie projektu Q # w środowisku deweloperskim</span><span class="sxs-lookup"><span data-stu-id="2e282-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="2e282-104">Dowiedz się, jak utworzyć projekt Q # z QDK.</span><span class="sxs-lookup"><span data-stu-id="2e282-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="2e282-105">Projekt Q # zawiera pliki Q # zawierające kod Quantum oraz program hosta służący do uruchamiania programu Quantum.</span><span class="sxs-lookup"><span data-stu-id="2e282-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="2e282-106">Program hosta można napisać w językach .NET, takich jak C#, lub w języku Python.</span><span class="sxs-lookup"><span data-stu-id="2e282-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="2e282-107">Możesz również uruchomić kod Q w notesie Jupyter przy użyciu jądra IQ #.</span><span class="sxs-lookup"><span data-stu-id="2e282-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="2e282-108">Wybierz środowisko deweloperskie i język w poniższych sekcjach:</span><span class="sxs-lookup"><span data-stu-id="2e282-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="2e282-109">Python</span><span class="sxs-lookup"><span data-stu-id="2e282-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="2e282-110">Notesy Q # Jupyter</span><span class="sxs-lookup"><span data-stu-id="2e282-110">Q# Jupyter notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="2e282-111">C#za pomocą programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e282-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="2e282-112">C#z VS Code</span><span class="sxs-lookup"><span data-stu-id="2e282-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="2e282-113">C#przy użyciu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="2e282-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="2e282-114">Tworzenie projektu w języku Python</span><span class="sxs-lookup"><span data-stu-id="2e282-114">Create a Python project</span></span>

1. <span data-ttu-id="2e282-115">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2e282-115">Pre-requisites</span></span>

     * <span data-ttu-id="2e282-116">Instalowanie [zestawu Quantum Development Kit dla języka Python](xref:microsoft.quantum.install.python)</span><span class="sxs-lookup"><span data-stu-id="2e282-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="2e282-117">Utwórz folder dla projektu i przejdź do tego folderu</span><span class="sxs-lookup"><span data-stu-id="2e282-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="2e282-118">Utwórz plik Q # o nazwie `Operation.qs`i Dodaj do niego kod Q.</span><span class="sxs-lookup"><span data-stu-id="2e282-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="2e282-119">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="2e282-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="2e282-120">Utwórz plik hosta języka Python o nazwie `host.py`, aby wywołać operację Q #.</span><span class="sxs-lookup"><span data-stu-id="2e282-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="2e282-121">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="2e282-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="2e282-122">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="2e282-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="2e282-123">Sprawdź dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="2e282-123">Verify the output.</span></span> <span data-ttu-id="2e282-124">Program powinien zwrócić następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="2e282-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="2e282-125">Teraz można kontynuować opracowywanie programu Quantum.</span><span class="sxs-lookup"><span data-stu-id="2e282-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="2e282-126">Utwórz projekt Q # Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2e282-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="2e282-127">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2e282-127">Pre-requisites</span></span>

    * <span data-ttu-id="2e282-128">Instalowanie [zestawu Quantum Development Kit dla notesów Jupyter](xref:microsoft.quantum.install.jupyter)</span><span class="sxs-lookup"><span data-stu-id="2e282-128">Install the [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="2e282-129">Uruchom następujące polecenie, aby uruchomić serwer notesów:</span><span class="sxs-lookup"><span data-stu-id="2e282-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="2e282-130">Przejdź do adresu URL podanego w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="2e282-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="2e282-131">Na przykład: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span><span class="sxs-lookup"><span data-stu-id="2e282-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="2e282-132">W przeglądarce pojawi się Strona Jupyter.</span><span class="sxs-lookup"><span data-stu-id="2e282-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="2e282-133">Na karcie **pliki** wybierz pozycję **Nowy** > **Q #** , aby utworzyć Notes Jupyter z jądrem Q #.</span><span class="sxs-lookup"><span data-stu-id="2e282-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="2e282-134">Dodaj następujący kod do pierwszej komórki notesu:</span><span class="sxs-lookup"><span data-stu-id="2e282-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="2e282-135">Zaznacz **komórkę** > **Run Cells** , aby uruchomić Notes.</span><span class="sxs-lookup"><span data-stu-id="2e282-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="2e282-136">`SayHello` pojawi się wkrótce w danych wyjściowych komórki:</span><span class="sxs-lookup"><span data-stu-id="2e282-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Komórka notesu Jupyter z kodem języka Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="2e282-138">W przypadku uruchamiania w notesach Jupyter kod Q # jest kompilowany, a Notes będzie wyprowadzał nazwę znalezionych operacji.</span><span class="sxs-lookup"><span data-stu-id="2e282-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="2e282-139">W nowej komórce zasymuluj wykonywanie na komputerze kwantowym właśnie utworzonej operacji przy użyciu polecenia magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="2e282-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Komórka notesu Jupyter z poleceniem magic %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="2e282-141">Na ekranie powinien zostać wyświetlony komunikat oraz wynik wywołanej operacji (w tym przypadku pusty).</span><span class="sxs-lookup"><span data-stu-id="2e282-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="2e282-142">Teraz możesz dodać inne operacje pytań i odpowiedzi, aby kontynuować tworzenie procesów Quantum.</span><span class="sxs-lookup"><span data-stu-id="2e282-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="2e282-143">Tworzenie C# projektu w systemie Windows przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e282-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="2e282-144">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2e282-144">Pre-requisites</span></span>

    * <span data-ttu-id="2e282-145">Zainstaluj [rozszerzenie Quantum Development Kit dla programu Visual Studio](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="2e282-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="2e282-146">Tworzenie nowej aplikacji w języku Q#</span><span class="sxs-lookup"><span data-stu-id="2e282-146">Create a new Q# application</span></span>

    * <span data-ttu-id="2e282-147">Przejdź do pozycji **Plik** -> **Nowy** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="2e282-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="2e282-148">Wpisz `Q#` w polu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="2e282-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="2e282-149">Wybierz pozycję **Aplikacja Q#**</span><span class="sxs-lookup"><span data-stu-id="2e282-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="2e282-150">Wybierz pozycję **Dalej**</span><span class="sxs-lookup"><span data-stu-id="2e282-150">Select **Next**</span></span>
    * <span data-ttu-id="2e282-151">Wybierz nazwę i lokalizację dla aplikacji</span><span class="sxs-lookup"><span data-stu-id="2e282-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="2e282-152">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="2e282-152">Select **Create**</span></span>

1. <span data-ttu-id="2e282-153">Inspekcja projektu</span><span class="sxs-lookup"><span data-stu-id="2e282-153">Inspect the project</span></span>

    <span data-ttu-id="2e282-154">Powinny być widoczne dwa utworzone pliki: plik `Driver.cs`, który jest aplikacją hosta języka C#, i plik `Operation.qs`, czyli program języka Q# definiujący prostą operację w celu wydrukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="2e282-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="2e282-155">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="2e282-155">Run the application</span></span>

    * <span data-ttu-id="2e282-156">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**</span><span class="sxs-lookup"><span data-stu-id="2e282-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="2e282-157">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="2e282-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="2e282-158">Teraz możesz kontynuować opracowywanie Quantum przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e282-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="2e282-159">Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="2e282-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="2e282-160">Tworzenie C# projektu przy użyciu vs Code</span><span class="sxs-lookup"><span data-stu-id="2e282-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="2e282-161">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2e282-161">Pre-requisites</span></span>

    * <span data-ttu-id="2e282-162">Zainstaluj [rozszerzenie Quantum Development Kit dla vs Code](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="2e282-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="2e282-163">Tworzenie nowego projektu:</span><span class="sxs-lookup"><span data-stu-id="2e282-163">Create a new project:</span></span>

    * <span data-ttu-id="2e282-164">Przejdź do pozycji **Widok** -> **Paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="2e282-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="2e282-165">Wybierz pozycję **Q #: Utwórz nowy projekt**</span><span class="sxs-lookup"><span data-stu-id="2e282-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="2e282-166">Wybierz **autonomiczną aplikację konsolową**</span><span class="sxs-lookup"><span data-stu-id="2e282-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="2e282-167">Przejdź do lokalizacji w systemie plików, w której chcesz utworzyć aplikację</span><span class="sxs-lookup"><span data-stu-id="2e282-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="2e282-168">Po utworzeniu projektu kliknij przycisk **Otwórz nowy projekt**</span><span class="sxs-lookup"><span data-stu-id="2e282-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="2e282-169">Uruchom aplikację:</span><span class="sxs-lookup"><span data-stu-id="2e282-169">Run the application:</span></span>

    * <span data-ttu-id="2e282-170">Przejdź do **terminalu** -> **nowym terminalu**</span><span class="sxs-lookup"><span data-stu-id="2e282-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="2e282-171">Wprowadź `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="2e282-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="2e282-172">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2e282-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="2e282-173">Teraz możesz kontynuować tworzenie aplikacji Quantum przy użyciu Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2e282-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="2e282-174">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2e282-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="2e282-175">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="2e282-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="2e282-176">Tworzenie C# projektu przy użyciu narzędzia wiersza polecenia `dotnet`</span><span class="sxs-lookup"><span data-stu-id="2e282-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="2e282-177">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2e282-177">Pre-requisites</span></span>

    * <span data-ttu-id="2e282-178">Instalowanie [zestawu Quantum Development Kit dla wiersza polecenia](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="2e282-178">Install the [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="2e282-179">Tworzenie nowej aplikacji</span><span class="sxs-lookup"><span data-stu-id="2e282-179">Create a new application</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="2e282-180">Przechodzenie do nowego katalogu aplikacji</span><span class="sxs-lookup"><span data-stu-id="2e282-180">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="2e282-181">Powinny zostać wyświetlone dwa utworzone pliki wraz z plikami projektu aplikacji: plik języka Q# (`Operation.qs`) i plik hosta języka C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="2e282-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="2e282-182">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="2e282-182">Run the application</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="2e282-183">Powinny zostać wyświetlone następujące dane wyjściowe: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2e282-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="2e282-184">Teraz Kontynuuj programowanie w usłudze Quantum przy użyciu narzędzi wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="2e282-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="2e282-185">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="2e282-185">What's next?</span></span>

<span data-ttu-id="2e282-186">Teraz, po utworzeniu projektu w preferowanym środowisku, można kontynuować programowanie w usłudze Quantum.</span><span class="sxs-lookup"><span data-stu-id="2e282-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>

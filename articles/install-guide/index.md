---
title: Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035305"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="4b09a-102">Instalowanie zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="4b09a-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="4b09a-103">Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym.</span><span class="sxs-lookup"><span data-stu-id="4b09a-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="4b09a-104">Zestaw QDK składa się z:</span><span class="sxs-lookup"><span data-stu-id="4b09a-104">The QDK consists of:</span></span>

- <span data-ttu-id="4b09a-105">języka programowania Q#</span><span class="sxs-lookup"><span data-stu-id="4b09a-105">the Q# programming language</span></span>
- <span data-ttu-id="4b09a-106">zestawu bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#</span><span class="sxs-lookup"><span data-stu-id="4b09a-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="4b09a-107">aplikacja hosta (napisana w języku Python lub języku .NET), która uruchamia operacje kwantowe napisane w języku Q#</span><span class="sxs-lookup"><span data-stu-id="4b09a-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="4b09a-108">narzędzia ułatwiające programowanie</span><span class="sxs-lookup"><span data-stu-id="4b09a-108">tools to facilitate your development</span></span>

<span data-ttu-id="4b09a-109">W zależności od wybranego środowiska programistycznego istnieją różne kroki instalacji.</span><span class="sxs-lookup"><span data-stu-id="4b09a-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="4b09a-110">Wybierz odpowiednie środowisko w poniższych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="4b09a-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="4b09a-111">Programowanie przy użyciu platformy Python</span><span class="sxs-lookup"><span data-stu-id="4b09a-111">Develop with Python</span></span>

1. <span data-ttu-id="4b09a-112">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4b09a-112">Pre-requisites</span></span>

    - <span data-ttu-id="4b09a-113">Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="4b09a-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="4b09a-114">Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="4b09a-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="4b09a-115">Zestaw .NET Core SDK 2.1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="4b09a-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4b09a-116">Instalowanie pakietu `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="4b09a-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="4b09a-117">Instalowanie pakietu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="4b09a-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="4b09a-118">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="4b09a-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4b09a-119">Utwórz minimalną operację języka Q#, tworząc plik o nazwie `Operation.qs` i dodając do niego następujący kod:</span><span class="sxs-lookup"><span data-stu-id="4b09a-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="4b09a-120">Utwórz program w języku Python o nazwie `hello_world.py` do wywołania operacji `SayHello()` języka Q#:</span><span class="sxs-lookup"><span data-stu-id="4b09a-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="4b09a-121">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="4b09a-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="4b09a-122">Sprawdź dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="4b09a-122">Verify the output.</span></span> <span data-ttu-id="4b09a-123">Program powinien zwrócić następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="4b09a-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="4b09a-124">Programowanie za pomocą notesów Jupyter</span><span class="sxs-lookup"><span data-stu-id="4b09a-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="4b09a-125">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4b09a-125">Pre-requisites</span></span>

    - <span data-ttu-id="4b09a-126">Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="4b09a-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="4b09a-127">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="4b09a-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="4b09a-128">Zestaw .NET Core SDK 2.1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="4b09a-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4b09a-129">Instalowanie pakietu `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="4b09a-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="4b09a-130">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="4b09a-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4b09a-131">Uruchom następujące polecenie, aby uruchomić serwer notesów:</span><span class="sxs-lookup"><span data-stu-id="4b09a-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="4b09a-132">Przejdź do adresu URL podanego w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="4b09a-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="4b09a-133">Na przykład: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="4b09a-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="4b09a-134">Utwórz notes Jupyter z jądrem Q# i dodaj następujący kod do pierwszej komórki notesu:</span><span class="sxs-lookup"><span data-stu-id="4b09a-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="4b09a-135">Uruchom tę komórkę notesu:</span><span class="sxs-lookup"><span data-stu-id="4b09a-135">Run this cell of the notebook:</span></span>

        ![Komórka notesu Jupyter](~/media/install-guide-jupyter.png)

        <span data-ttu-id="4b09a-137">W danych wyjściowych komórki powinien zostać wyświetlony element `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="4b09a-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="4b09a-138">W przypadku uruchamiania w notesach Jupyter kod języka Q# jest kompilowany, a notes zwraca w danych wyjściowych nazwę znalezionych operacji.</span><span class="sxs-lookup"><span data-stu-id="4b09a-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="4b09a-139">Programowanie w języku C# w systemie Windows przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4b09a-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="4b09a-140">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4b09a-140">Pre-requisites</span></span>

    - <span data-ttu-id="4b09a-141">Program [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 z włączonym obciążeniem programu .NET Core obsługującym projektowanie dla wielu platform</span><span class="sxs-lookup"><span data-stu-id="4b09a-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="4b09a-142">Instalowanie rozszerzenia programu Visual Studio dla języka Q#</span><span class="sxs-lookup"><span data-stu-id="4b09a-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="4b09a-143">Pobierz [rozszerzenie programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="4b09a-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="4b09a-144">Dodaj rozszerzenie do programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4b09a-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="4b09a-145">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="4b09a-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4b09a-146">Tworzenie nowej aplikacji w języku Q#</span><span class="sxs-lookup"><span data-stu-id="4b09a-146">Create a new Q# application</span></span>

        - <span data-ttu-id="4b09a-147">Przejdź do pozycji **Plik** -> **Nowy** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="4b09a-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="4b09a-148">Wpisz `Q#` w polu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="4b09a-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="4b09a-149">Wybierz pozycję **Aplikacja Q#**</span><span class="sxs-lookup"><span data-stu-id="4b09a-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="4b09a-150">Wybierz pozycję **Dalej**</span><span class="sxs-lookup"><span data-stu-id="4b09a-150">Select **Next**</span></span>
        - <span data-ttu-id="4b09a-151">Wybierz nazwę i lokalizację dla aplikacji</span><span class="sxs-lookup"><span data-stu-id="4b09a-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="4b09a-152">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="4b09a-152">Select **Create**</span></span>

    - <span data-ttu-id="4b09a-153">Inspekcja projektu</span><span class="sxs-lookup"><span data-stu-id="4b09a-153">Inspect the project</span></span>

        <span data-ttu-id="4b09a-154">Powinny być widoczne dwa utworzone pliki: plik `Driver.cs`, który jest aplikacją hosta języka C#, i plik `Operation.qs`, czyli program języka Q# definiujący prostą operację w celu wydrukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="4b09a-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="4b09a-155">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="4b09a-155">Run the application</span></span>

        - <span data-ttu-id="4b09a-156">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**</span><span class="sxs-lookup"><span data-stu-id="4b09a-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="4b09a-157">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="4b09a-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="4b09a-158">Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="4b09a-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="4b09a-159">Programowanie w języku C# przy użyciu programu VS Code</span><span class="sxs-lookup"><span data-stu-id="4b09a-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="4b09a-160">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4b09a-160">Pre-requisites</span></span>

   - [<span data-ttu-id="4b09a-161">VS Code</span><span class="sxs-lookup"><span data-stu-id="4b09a-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="4b09a-162">Zestaw .NET Core SDK 2.1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="4b09a-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4b09a-163">Instalowanie rozszerzenia programu VS Code dla obliczeń kwantowych</span><span class="sxs-lookup"><span data-stu-id="4b09a-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="4b09a-164">Zainstaluj [rozszerzenie programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="4b09a-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="4b09a-165">Instalowanie szablonów projektów kwantowych:</span><span class="sxs-lookup"><span data-stu-id="4b09a-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="4b09a-166">Przejdź do pozycji **Widok** -> **Paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="4b09a-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="4b09a-167">Wybierz pozycję **Q#: Instalowanie szablonów projektów**</span><span class="sxs-lookup"><span data-stu-id="4b09a-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="4b09a-168">Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.</span><span class="sxs-lookup"><span data-stu-id="4b09a-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="4b09a-169">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="4b09a-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4b09a-170">Tworzenie nowego projektu:</span><span class="sxs-lookup"><span data-stu-id="4b09a-170">Create a new project:</span></span>

        - <span data-ttu-id="4b09a-171">Przejdź do pozycji **Widok** -> **Paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="4b09a-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="4b09a-172">Wybierz pozycję **Q#: Utwórz nowy projekt**</span><span class="sxs-lookup"><span data-stu-id="4b09a-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="4b09a-173">Przejdź do lokalizacji w systemie plików, w której chcesz utworzyć aplikację</span><span class="sxs-lookup"><span data-stu-id="4b09a-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="4b09a-174">Po utworzeniu projektu kliknij przycisk **Otwórz nowy projekt**</span><span class="sxs-lookup"><span data-stu-id="4b09a-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="4b09a-175">Uruchom aplikację:</span><span class="sxs-lookup"><span data-stu-id="4b09a-175">Run the application:</span></span>

        - <span data-ttu-id="4b09a-176">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**</span><span class="sxs-lookup"><span data-stu-id="4b09a-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="4b09a-177">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4b09a-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="4b09a-178">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4b09a-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="4b09a-179">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="4b09a-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="4b09a-180">Programowanie w języku C# przy użyciu narzędzia wiersza polecenia `dotnet`</span><span class="sxs-lookup"><span data-stu-id="4b09a-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="4b09a-181">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="4b09a-181">Pre-requisites</span></span>

    - [<span data-ttu-id="4b09a-182">Zestaw .NET Core SDK 2.1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="4b09a-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4b09a-183">Instalowanie szablonów projektów kwantowych dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="4b09a-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="4b09a-184">Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.</span><span class="sxs-lookup"><span data-stu-id="4b09a-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="4b09a-185">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="4b09a-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4b09a-186">Tworzenie nowej aplikacji</span><span class="sxs-lookup"><span data-stu-id="4b09a-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="4b09a-187">Przechodzenie do nowego katalogu aplikacji</span><span class="sxs-lookup"><span data-stu-id="4b09a-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="4b09a-188">Powinny zostać wyświetlone dwa utworzone pliki wraz z plikami projektu aplikacji: plik języka Q# (`Operation.qs`) i plik hosta języka C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="4b09a-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="4b09a-189">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="4b09a-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="4b09a-190">Powinny zostać wyświetlone następujące dane wyjściowe: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4b09a-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="4b09a-191">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="4b09a-191">What's next?</span></span>

<span data-ttu-id="4b09a-192">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="4b09a-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>

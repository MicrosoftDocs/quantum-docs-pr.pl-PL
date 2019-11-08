---
title: Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799163"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="93a20-102">Instalowanie zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="93a20-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="93a20-103">Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym.</span><span class="sxs-lookup"><span data-stu-id="93a20-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="93a20-104">Zestaw QDK składa się z:</span><span class="sxs-lookup"><span data-stu-id="93a20-104">The QDK consists of:</span></span>

- <span data-ttu-id="93a20-105">języka programowania Q#</span><span class="sxs-lookup"><span data-stu-id="93a20-105">the Q# programming language</span></span>
- <span data-ttu-id="93a20-106">zestawu bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#</span><span class="sxs-lookup"><span data-stu-id="93a20-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="93a20-107">aplikacja hosta (napisana w języku Python lub języku .NET), która uruchamia operacje kwantowe napisane w języku Q#</span><span class="sxs-lookup"><span data-stu-id="93a20-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="93a20-108">narzędzia ułatwiające programowanie</span><span class="sxs-lookup"><span data-stu-id="93a20-108">tools to facilitate your development</span></span>

<span data-ttu-id="93a20-109">W zależności od wybranego środowiska programistycznego istnieją różne kroki instalacji.</span><span class="sxs-lookup"><span data-stu-id="93a20-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="93a20-110">Wybierz odpowiednie środowisko w poniższych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="93a20-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="93a20-111">Programowanie przy użyciu platformy Python</span><span class="sxs-lookup"><span data-stu-id="93a20-111">Develop with Python</span></span>

<span data-ttu-id="93a20-112">Pakiet qsharp dla języka Python ułatwia symulowanie operacji i funkcji języka Q# z poziomu języka Python.</span><span class="sxs-lookup"><span data-stu-id="93a20-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="93a20-113">IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="93a20-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="93a20-114">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="93a20-114">Pre-requisites</span></span>

    - <span data-ttu-id="93a20-115">Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="93a20-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="93a20-116">Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="93a20-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="93a20-117">Zestaw .NET Core SDK 3.0 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="93a20-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="93a20-118">Instalowanie pakietu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="93a20-118">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="93a20-119">Instalowanie pakietu `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="93a20-119">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="93a20-120">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="93a20-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="93a20-121">Utwórz minimalną operację języka Q#, tworząc plik o nazwie `Operation.qs` i dodając do niego następujący kod:</span><span class="sxs-lookup"><span data-stu-id="93a20-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="93a20-122">Utwórz program w języku Python o nazwie `hello_world.py` do wywołania operacji `SayHello()` języka Q#:</span><span class="sxs-lookup"><span data-stu-id="93a20-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="93a20-123">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="93a20-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="93a20-124">Sprawdź dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="93a20-124">Verify the output.</span></span> <span data-ttu-id="93a20-125">Program powinien zwrócić następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="93a20-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="93a20-126">Programowanie za pomocą notesów Jupyter</span><span class="sxs-lookup"><span data-stu-id="93a20-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="93a20-127">Notesy programu Jupyter to ulubione rozwiązanie na uczelniach i w laboratoriach naukowych oraz podczas wspólnego programowania w trybie online. Oferują one wykonywanie kodu w miejscu — teraz także kodu języka Q# — a także instrukcje, notesy oraz inną zawartość.</span><span class="sxs-lookup"><span data-stu-id="93a20-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="93a20-128">Oto jak zacząć tworzyć własne notesy języka Q#.</span><span class="sxs-lookup"><span data-stu-id="93a20-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="93a20-129">IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie zestawu .NET Core SDK używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="93a20-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="93a20-130">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="93a20-130">Pre-requisites</span></span>

    - <span data-ttu-id="93a20-131">Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="93a20-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="93a20-132">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="93a20-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="93a20-133">Zestaw .NET Core SDK 3.0 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="93a20-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="93a20-134">Instalowanie pakietu `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="93a20-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="93a20-135">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="93a20-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="93a20-136">Uruchom następujące polecenie, aby uruchomić serwer notesów:</span><span class="sxs-lookup"><span data-stu-id="93a20-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="93a20-137">Przejdź do adresu URL podanego w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="93a20-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="93a20-138">Na przykład: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="93a20-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="93a20-139">Utwórz notes Jupyter z jądrem Q# i dodaj następujący kod do pierwszej komórki notesu:</span><span class="sxs-lookup"><span data-stu-id="93a20-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="93a20-140">Uruchom tę komórkę notesu:</span><span class="sxs-lookup"><span data-stu-id="93a20-140">Run this cell of the notebook:</span></span>

        ![Komórka notesu Jupyter z kodem języka Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="93a20-142">W danych wyjściowych komórki powinien zostać wyświetlony element `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="93a20-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="93a20-143">W przypadku uruchamiania w notesach Jupyter kod języka Q# jest kompilowany, a notes zwraca w danych wyjściowych nazwę znalezionych operacji.</span><span class="sxs-lookup"><span data-stu-id="93a20-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="93a20-144">W nowej komórce zasymuluj wykonywanie na komputerze kwantowym właśnie utworzonej operacji przy użyciu polecenia magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="93a20-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![Komórka notesu Jupyter z poleceniem magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="93a20-146">Na ekranie powinien zostać wyświetlony komunikat oraz wynik wywołanej operacji (w tym przypadku pusty).</span><span class="sxs-lookup"><span data-stu-id="93a20-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="93a20-147">Programowanie w języku C# w systemie Windows przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93a20-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="93a20-148">Program Visual Studio zapewnia zaawansowane środowisko tworzenia programów w języku Q# oraz doskonałe opcje takie jak uzupełnianie kodu i wyróżnianie składni, które ułatwiają deweloperom tworzenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="93a20-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="93a20-149">Rozszerzenie Q# w programie Visual Studio zawiera szablony dla plików i projektów Q# oraz obsługę wyróżniania składni i funkcji IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="93a20-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="93a20-150">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="93a20-150">Pre-requisites</span></span>

    - <span data-ttu-id="93a20-151">Program [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 z włączonym obciążeniem programu .NET Core obsługującym projektowanie dla wielu platform</span><span class="sxs-lookup"><span data-stu-id="93a20-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="93a20-152">Instalowanie rozszerzenia programu Visual Studio dla języka Q#</span><span class="sxs-lookup"><span data-stu-id="93a20-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="93a20-153">Pobierz [rozszerzenie programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="93a20-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="93a20-154">Dodaj rozszerzenie do programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93a20-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="93a20-155">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="93a20-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="93a20-156">Tworzenie nowej aplikacji w języku Q#</span><span class="sxs-lookup"><span data-stu-id="93a20-156">Create a new Q# application</span></span>

        - <span data-ttu-id="93a20-157">Przejdź do pozycji **Plik** -> **Nowy** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="93a20-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="93a20-158">Wpisz `Q#` w polu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="93a20-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="93a20-159">Wybierz pozycję **Aplikacja Q#**</span><span class="sxs-lookup"><span data-stu-id="93a20-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="93a20-160">Wybierz pozycję **Dalej**</span><span class="sxs-lookup"><span data-stu-id="93a20-160">Select **Next**</span></span>
        - <span data-ttu-id="93a20-161">Wybierz nazwę i lokalizację dla aplikacji</span><span class="sxs-lookup"><span data-stu-id="93a20-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="93a20-162">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="93a20-162">Select **Create**</span></span>

    - <span data-ttu-id="93a20-163">Inspekcja projektu</span><span class="sxs-lookup"><span data-stu-id="93a20-163">Inspect the project</span></span>

        <span data-ttu-id="93a20-164">Powinny być widoczne dwa utworzone pliki: plik `Driver.cs`, który jest aplikacją hosta języka C#, i plik `Operation.qs`, czyli program języka Q# definiujący prostą operację w celu wydrukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="93a20-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="93a20-165">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="93a20-165">Run the application</span></span>

        - <span data-ttu-id="93a20-166">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**</span><span class="sxs-lookup"><span data-stu-id="93a20-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="93a20-167">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="93a20-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="93a20-168">Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="93a20-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="93a20-169">Programowanie w języku C# w programie Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="93a20-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="93a20-170">Program Visual Studio Code (VS Code) zapewnia zaawansowane środowisko tworzenia programów w języku Q# w wielu środowiskach z wieloma komputerami, takich jak systemy Windows i Linux oraz komputery Mac, a także doskonałe opcje takie jak uzupełnianie kodu i wyróżnianie składni, które ułatwiają deweloperom tworzenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="93a20-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="93a20-171">Rozszerzenia Q# programu VS Code zawiera funkcję wyróżniania składni oraz fragmenty kodu języka Q#.</span><span class="sxs-lookup"><span data-stu-id="93a20-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="93a20-172">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="93a20-172">Pre-requisites</span></span>

   - [<span data-ttu-id="93a20-173">VS Code</span><span class="sxs-lookup"><span data-stu-id="93a20-173">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="93a20-174">Zestaw .NET Core SDK 3.0 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="93a20-174">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="93a20-175">Instalowanie rozszerzenia programu VS Code dla obliczeń kwantowych</span><span class="sxs-lookup"><span data-stu-id="93a20-175">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="93a20-176">Zainstaluj [rozszerzenie programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="93a20-176">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="93a20-177">Instalowanie szablonów projektów kwantowych:</span><span class="sxs-lookup"><span data-stu-id="93a20-177">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="93a20-178">Przejdź do pozycji **Widok** -> **Paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="93a20-178">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="93a20-179">Wybierz pozycję **Q#: Instalowanie szablonów projektów**</span><span class="sxs-lookup"><span data-stu-id="93a20-179">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="93a20-180">Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.</span><span class="sxs-lookup"><span data-stu-id="93a20-180">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="93a20-181">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="93a20-181">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="93a20-182">Tworzenie nowego projektu:</span><span class="sxs-lookup"><span data-stu-id="93a20-182">Create a new project:</span></span>

        - <span data-ttu-id="93a20-183">Przejdź do pozycji **Widok** -> **Paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="93a20-183">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="93a20-184">Wybierz pozycję **Q#: Utwórz nowy projekt**</span><span class="sxs-lookup"><span data-stu-id="93a20-184">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="93a20-185">Przejdź do lokalizacji w systemie plików, w której chcesz utworzyć aplikację</span><span class="sxs-lookup"><span data-stu-id="93a20-185">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="93a20-186">Po utworzeniu projektu kliknij przycisk **Otwórz nowy projekt**</span><span class="sxs-lookup"><span data-stu-id="93a20-186">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="93a20-187">Uruchom aplikację:</span><span class="sxs-lookup"><span data-stu-id="93a20-187">Run the application:</span></span>

        - <span data-ttu-id="93a20-188">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**</span><span class="sxs-lookup"><span data-stu-id="93a20-188">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="93a20-189">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="93a20-189">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="93a20-190">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="93a20-190">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="93a20-191">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="93a20-191">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="93a20-192">Programowanie w języku C# przy użyciu narzędzia wiersza polecenia `dotnet`</span><span class="sxs-lookup"><span data-stu-id="93a20-192">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="93a20-193">Oczywiście programy Q# możesz kompilować i uruchamiać z poziomu wiersza polecenia, po prostu instalując zestaw SDK .NET Core i szablony projektów QDK.</span><span class="sxs-lookup"><span data-stu-id="93a20-193">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="93a20-194">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="93a20-194">Pre-requisites</span></span>

    - [<span data-ttu-id="93a20-195">Zestaw .NET Core SDK 3.0 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="93a20-195">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="93a20-196">Instalowanie szablonów projektów kwantowych dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="93a20-196">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="93a20-197">Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.</span><span class="sxs-lookup"><span data-stu-id="93a20-197">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="93a20-198">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="93a20-198">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="93a20-199">Tworzenie nowej aplikacji</span><span class="sxs-lookup"><span data-stu-id="93a20-199">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="93a20-200">Przechodzenie do nowego katalogu aplikacji</span><span class="sxs-lookup"><span data-stu-id="93a20-200">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="93a20-201">Powinny zostać wyświetlone dwa utworzone pliki wraz z plikami projektu aplikacji: plik języka Q# (`Operation.qs`) i plik hosta języka C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="93a20-201">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="93a20-202">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="93a20-202">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="93a20-203">Powinny zostać wyświetlone następujące dane wyjściowe: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="93a20-203">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="93a20-204">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="93a20-204">What's next?</span></span>

<span data-ttu-id="93a20-205">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="93a20-205">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>

---
title: 'Programowanie przy użyciu narzędzia Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831022"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="b632b-102">Programowanie przy użyciu narzędzia Q # +C#</span><span class="sxs-lookup"><span data-stu-id="b632b-102">Develop with Q# + C#</span></span>

<span data-ttu-id="b632b-103">Zainstaluj program QDK, aby C# opracowywać programy hosta do wywoływania operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="b632b-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="b632b-104">Program Q # jest zbudowany w celu pomyślnego C#odtwarzania z językami .NET — w tym celu.</span><span class="sxs-lookup"><span data-stu-id="b632b-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="b632b-105">Możesz współpracować z tym parowaniem w różnych środowiskach deweloperskich:</span><span class="sxs-lookup"><span data-stu-id="b632b-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="b632b-106">Q # + C# przy użyciu programu Visual Studio (Windows)</span><span class="sxs-lookup"><span data-stu-id="b632b-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="b632b-107">Q # + C# używa Visual Studio Code (Windows, Linux i Mac)</span><span class="sxs-lookup"><span data-stu-id="b632b-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="b632b-108">Q # + C# przy użyciu narzędzia wiersza polecenia `dotnet`</span><span class="sxs-lookup"><span data-stu-id="b632b-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="b632b-109">Programowanie przy użyciu narzędzia Q C# # + w programie Visual Studio<a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="b632b-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="b632b-110">Program Visual Studio oferuje bogate środowisko do opracowywania programów pytań i odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="b632b-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="b632b-111">Rozszerzenie Q # programu Visual Studio zawiera szablony dla plików i projektów Q #, a także wyróżnianie składni, uzupełnianie kodu i obsługa technologii IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b632b-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="b632b-112">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b632b-112">Pre-requisites</span></span>

    - <span data-ttu-id="b632b-113">Program [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 z włączonym obciążeniem programu .NET Core obsługującym projektowanie dla wielu platform</span><span class="sxs-lookup"><span data-stu-id="b632b-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="b632b-114">Instalowanie rozszerzenia programu Visual Studio dla języka Q#</span><span class="sxs-lookup"><span data-stu-id="b632b-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="b632b-115">Pobierz i zainstaluj [rozszerzenie programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="b632b-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="b632b-116">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="b632b-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b632b-117">Tworzenie nowej aplikacji w języku Q#</span><span class="sxs-lookup"><span data-stu-id="b632b-117">Create a new Q# application</span></span>

        - <span data-ttu-id="b632b-118">Przejdź do pozycji **Plik** -> **Nowy** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="b632b-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="b632b-119">Wpisz `Q#` w polu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="b632b-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="b632b-120">Wybierz pozycję **Aplikacja Q#**</span><span class="sxs-lookup"><span data-stu-id="b632b-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="b632b-121">Wybierz pozycję **Dalej**</span><span class="sxs-lookup"><span data-stu-id="b632b-121">Select **Next**</span></span>
        - <span data-ttu-id="b632b-122">Wybierz nazwę i lokalizację dla aplikacji</span><span class="sxs-lookup"><span data-stu-id="b632b-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="b632b-123">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="b632b-123">Select **Create**</span></span>

    - <span data-ttu-id="b632b-124">Inspekcja projektu</span><span class="sxs-lookup"><span data-stu-id="b632b-124">Inspect the project</span></span>

        <span data-ttu-id="b632b-125">Powinny być widoczne dwa utworzone pliki: plik `Driver.cs`, który jest aplikacją hosta języka C#, i plik `Operation.qs`, czyli program języka Q# definiujący prostą operację w celu wydrukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="b632b-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="b632b-126">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="b632b-126">Run the application</span></span>

        - <span data-ttu-id="b632b-127">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**</span><span class="sxs-lookup"><span data-stu-id="b632b-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="b632b-128">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="b632b-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="b632b-129">Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="b632b-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="b632b-130">Programowanie przy użyciu funkcji Q C# # + Visual Studio Code<a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="b632b-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="b632b-131">Visual Studio Code (VS Code) oferuje bogate środowisko do opracowywania programów Q # w systemach Windows, Linux i Mac.</span><span class="sxs-lookup"><span data-stu-id="b632b-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="b632b-132">Rozszerzenie Q # VS Code obejmuje obsługę wyróżniania składni Q #, uzupełniania kodu i fragmentów kodu pytań i odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="b632b-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="b632b-133">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b632b-133">Pre-requisites</span></span>

   - [<span data-ttu-id="b632b-134">VS Code</span><span class="sxs-lookup"><span data-stu-id="b632b-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="b632b-135">Zestaw .NET Core SDK 3,1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="b632b-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b632b-136">Instalowanie rozszerzenia programu VS Code dla obliczeń kwantowych</span><span class="sxs-lookup"><span data-stu-id="b632b-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="b632b-137">Zainstaluj [rozszerzenie programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="b632b-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="b632b-138">Instalowanie szablonów projektów kwantowych:</span><span class="sxs-lookup"><span data-stu-id="b632b-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="b632b-139">Przejdź do pozycji **Widok** -> **Paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="b632b-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="b632b-140">Wybierz pozycję **Q #: Instalowanie szablonów projektu**</span><span class="sxs-lookup"><span data-stu-id="b632b-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="b632b-141">Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.</span><span class="sxs-lookup"><span data-stu-id="b632b-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="b632b-142">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="b632b-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b632b-143">Tworzenie nowego projektu:</span><span class="sxs-lookup"><span data-stu-id="b632b-143">Create a new project:</span></span>

        - <span data-ttu-id="b632b-144">Przejdź do pozycji **Widok** -> **Paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="b632b-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="b632b-145">Wybierz pozycję **Q #: Utwórz nowy projekt**</span><span class="sxs-lookup"><span data-stu-id="b632b-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="b632b-146">Wybierz **autonomiczną aplikację konsolową**</span><span class="sxs-lookup"><span data-stu-id="b632b-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="b632b-147">Przejdź do lokalizacji w systemie plików, w której chcesz utworzyć aplikację</span><span class="sxs-lookup"><span data-stu-id="b632b-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="b632b-148">Po utworzeniu projektu kliknij przycisk **Otwórz nowy projekt**</span><span class="sxs-lookup"><span data-stu-id="b632b-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="b632b-149">Jeśli nie masz jeszcze C# rozszerzenia vs Code, zostanie wyświetlone okno podręczne.</span><span class="sxs-lookup"><span data-stu-id="b632b-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="b632b-150">Zainstaluj rozszerzenie.</span><span class="sxs-lookup"><span data-stu-id="b632b-150">Install the extension.</span></span> 

    - <span data-ttu-id="b632b-151">Uruchom aplikację:</span><span class="sxs-lookup"><span data-stu-id="b632b-151">Run the application:</span></span>

        - <span data-ttu-id="b632b-152">Przejdź do **terminalu** -> **nowym terminalu**</span><span class="sxs-lookup"><span data-stu-id="b632b-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="b632b-153">Wprowadź wartość `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="b632b-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="b632b-154">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b632b-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="b632b-155">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b632b-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="b632b-156">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="b632b-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="b632b-157">Programowanie przy użyciu funkcji Q C# # + za pomocą narzędzia wiersza polecenia `dotnet`<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="b632b-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="b632b-158">Oczywiście programy Q# możesz kompilować i uruchamiać z poziomu wiersza polecenia, po prostu instalując zestaw SDK .NET Core i szablony projektów QDK.</span><span class="sxs-lookup"><span data-stu-id="b632b-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="b632b-159">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b632b-159">Pre-requisites</span></span>

    - [<span data-ttu-id="b632b-160">Zestaw .NET Core SDK 3,1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="b632b-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="b632b-161">Instalowanie szablonów projektów kwantowych dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="b632b-161">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="b632b-162">Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.</span><span class="sxs-lookup"><span data-stu-id="b632b-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="b632b-163">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="b632b-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b632b-164">Tworzenie nowej aplikacji</span><span class="sxs-lookup"><span data-stu-id="b632b-164">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="b632b-165">Przechodzenie do nowego katalogu aplikacji</span><span class="sxs-lookup"><span data-stu-id="b632b-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="b632b-166">Powinny zostać wyświetlone dwa utworzone pliki wraz z plikami projektu aplikacji: plik języka Q# (`Operation.qs`) i plik hosta języka C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="b632b-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="b632b-167">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="b632b-167">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="b632b-168">Powinny zostać wyświetlone następujące dane wyjściowe: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b632b-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="b632b-169">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="b632b-169">What's next?</span></span>

<span data-ttu-id="b632b-170">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="b632b-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
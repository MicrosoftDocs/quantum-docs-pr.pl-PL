---
title: Tworzenie aplikacji wiersza polecenia w języku Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 630dc7b8acf2dd8f258eb27dfbc367b812cd1c19
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867611"
---
# <a name="develop-with-no-locq-command-line-applications"></a><span data-ttu-id="e4446-102">Tworzenie aplikacji wiersza polecenia w języku Q#</span><span class="sxs-lookup"><span data-stu-id="e4446-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="e4446-103">Programy w języku Q# można wykonywać samodzielnie, bez sterownika w języku hosta, takim jak C#, F# czy Python.</span><span class="sxs-lookup"><span data-stu-id="e4446-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4446-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="e4446-104">Prerequisites</span></span>

- [<span data-ttu-id="e4446-105">Zestaw .NET Core SDK 3.1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="e4446-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="e4446-106">Instalacja</span><span class="sxs-lookup"><span data-stu-id="e4446-106">Installation</span></span>

<span data-ttu-id="e4446-107">Chociaż aplikacje wiersza polecenia w języku Q# można tworzyć w dowolnym środowisku IDE, zalecamy korzystanie z programu Visual Studio Code (VS Code) lub Visual Studio jako środowiska IDE do lokalnego programowania aplikacji w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="e4446-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="e4446-108">W przypadku programowania w chmurze za pośrednictwem przeglądarki internetowej zalecamy używanie programu Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="e4446-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="e4446-109">Programowanie w tych środowiskach obejmuje bogate funkcje rozszerzenia QDK, takie jak ostrzeżenia, wyróżnianie składni, szablony projektów i wiele innych.</span><span class="sxs-lookup"><span data-stu-id="e4446-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="e4446-110">Aby skonfigurować program VS Code:</span><span class="sxs-lookup"><span data-stu-id="e4446-110">To configure VS Code:</span></span>

1. <span data-ttu-id="e4446-111">Pobierz i zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac).</span><span class="sxs-lookup"><span data-stu-id="e4446-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="e4446-112">Zainstaluj [zestaw Microsoft QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="e4446-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="e4446-113">Aby skonfigurować program Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="e4446-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="e4446-114">Pobierz i zainstaluj program [Visual Studio](https://visualstudio.microsoft.com/downloads/) w wersji 16.3 lub nowszej z włączonym pakietem roboczym Tworzenie aplikacji dla wielu platform w środowisku .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e4446-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="e4446-115">Pobierz i zainstaluj [zestaw Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="e4446-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="e4446-116">Aby skonfigurować program Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="e4446-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="e4446-117">Utwórz [konto platformy Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="e4446-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="e4446-118">Utwórz środowisko programu Codespaces.</span><span class="sxs-lookup"><span data-stu-id="e4446-118">Create a Codespaces environment.</span></span> <span data-ttu-id="e4446-119">Postępuj zgodnie z [przewodnikiem Szybki start](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="e4446-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span></span> <span data-ttu-id="e4446-120">Podczas tworzenia środowiska Codespace zalecamy wprowadzenie wartości `microsoft/Quantum` w polu „Git Repository” (Repozytorium Git) w celu załadowania ustawień specyficznych dla zestawu QDK.</span><span class="sxs-lookup"><span data-stu-id="e4446-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="e4446-121">Teraz możesz uruchomić nowe środowisko i rozpocząć programowanie w przeglądarce za pomocą [środowiska IDE programu VS Codespaces w chmurze](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="e4446-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="e4446-122">Alternatywnie można korzystać z lokalnej instalacji programu VS Code i używać Codespaces jako [środowiska zdalnego](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="e4446-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="e4446-123">Aby zainstalować zestaw QDK dla innego środowiska, wprowadź w wierszu polecenia:</span><span class="sxs-lookup"><span data-stu-id="e4446-123">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="e4446-124">Programowanie przy użyciu języka Q#</span><span class="sxs-lookup"><span data-stu-id="e4446-124">Develop with Q#</span></span>

<span data-ttu-id="e4446-125">Postępuj zgodnie z instrukcjami na karcie odpowiadającej Twojemu środowisku.</span><span class="sxs-lookup"><span data-stu-id="e4446-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="e4446-126">VS Code</span><span class="sxs-lookup"><span data-stu-id="e4446-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="e4446-127">Aby utworzyć nowy projekt:</span><span class="sxs-lookup"><span data-stu-id="e4446-127">To create a new project:</span></span>

1. <span data-ttu-id="e4446-128">Kliknij pozycję **View** -> **Command Palette** (Widok -> Paleta poleceń), a następnie wybierz polecenie **Q#: Create New Project** (Q#: utwórz nowy projekt).</span><span class="sxs-lookup"><span data-stu-id="e4446-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="e4446-129">Kliknij pozycję **Standalone console application** (Autonomiczna aplikacja konsolowa).</span><span class="sxs-lookup"><span data-stu-id="e4446-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="e4446-130">Przejdź do lokalizacji, w której chcesz zapisać projekt, a następnie kliknij pozycję **Create project** (Utwórz projekt).</span><span class="sxs-lookup"><span data-stu-id="e4446-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="e4446-131">Po pomyślnym utworzeniu projektu kliknij pozycję **Open new project...** (Otwórz nowy projekt) w prawym dolnym rogu.</span><span class="sxs-lookup"><span data-stu-id="e4446-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="e4446-132">Zapoznaj się z projektem.</span><span class="sxs-lookup"><span data-stu-id="e4446-132">Inspect the project.</span></span> <span data-ttu-id="e4446-133">Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="e4446-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="e4446-134">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="e4446-134">To run the application:</span></span>
1. <span data-ttu-id="e4446-135">Kliknij pozycję **Terminal** -> **New Terminal** (Nowy terminal).</span><span class="sxs-lookup"><span data-stu-id="e4446-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="e4446-136">W wierszu polecenia terminalu wprowadź polecenie `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="e4446-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="e4446-137">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="e4446-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="e4446-138">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu VS Code dla języka Q#.</span><span class="sxs-lookup"><span data-stu-id="e4446-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="e4446-139">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="e4446-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="e4446-140">Program Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e4446-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="e4446-141">Zweryfikuj instalację programu Visual Studio, tworząc aplikację Q# w języku `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="e4446-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="e4446-142">Aby utworzyć nową aplikację w języku Q#:</span><span class="sxs-lookup"><span data-stu-id="e4446-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="e4446-143">Otwórz program Visual Studio, a następnie wybierz kolejno opcje **Plik** -> **Nowy** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="e4446-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="e4446-144">Wpisz `Q#` w polu wyszukiwania, wybierz pozycję **Aplikacja Q#** , a następnie kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="e4446-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="e4446-145">Wprowadź nazwę i lokalizację aplikacji, a następnie kliknij pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="e4446-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="e4446-146">Zapoznaj się z projektem.</span><span class="sxs-lookup"><span data-stu-id="e4446-146">Inspect the project.</span></span> <span data-ttu-id="e4446-147">Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="e4446-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="e4446-148">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="e4446-148">To run the application:</span></span>
1. <span data-ttu-id="e4446-149">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**.</span><span class="sxs-lookup"><span data-stu-id="e4446-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="e4446-150">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="e4446-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="e4446-151">Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="e4446-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="e4446-152">Inne edytory z wierszem polecenia</span><span class="sxs-lookup"><span data-stu-id="e4446-152">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="e4446-153">Zweryfikuj instalację, tworząc aplikację `Hello World` w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="e4446-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="e4446-154">Zainstaluj szablony projektów.</span><span class="sxs-lookup"><span data-stu-id="e4446-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="e4446-155">Tworzenie nowej aplikacji:</span><span class="sxs-lookup"><span data-stu-id="e4446-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="e4446-156">Przechodzenie do katalogu aplikacji:</span><span class="sxs-lookup"><span data-stu-id="e4446-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="e4446-157">Ten katalog powinien teraz zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="e4446-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="e4446-158">Ten szablon można zmodyfikować za pomocą edytora tekstów i zastąpić go własnymi aplikacjami kwantowymi.</span><span class="sxs-lookup"><span data-stu-id="e4446-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="e4446-159">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="e4446-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="e4446-160">Powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="e4446-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="e4446-161">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="e4446-161">Next steps</span></span>

<span data-ttu-id="e4446-162">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="e4446-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

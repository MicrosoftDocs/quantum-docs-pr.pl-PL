---
title: Tworzenie aplikacji w języku Q# w środowisku IDE
description: Dowiedz się, jak utworzyć aplikację Q# uruchamianą z wiersza polecenia.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: eeb567dedc1b8123b32faf7ed3a42bb51f16a7d2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228733"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="23dec-103">Tworzenie aplikacji w języku Q# w środowisku IDE</span><span class="sxs-lookup"><span data-stu-id="23dec-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="23dec-104">Programy w języku Q# można uruchamiać samodzielnie, bez sterownika w języku hosta, takim jak C#, F# czy Python.</span><span class="sxs-lookup"><span data-stu-id="23dec-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="23dec-105">Aplikacje w języku Q# możesz opracowywać w programie Visual Studio Code (VS Code), programie Visual Studio, usłudze Visual Studio Codespaces lub dowolnym edytorze / środowisku IDE, a następnie uruchamiać je z poziomu konsoli .NET.</span><span class="sxs-lookup"><span data-stu-id="23dec-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="23dec-106">Wymagania wstępne dla wszystkich środowisk</span><span class="sxs-lookup"><span data-stu-id="23dec-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="23dec-107">Zestaw .NET Core SDK 3.1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="23dec-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="23dec-108">Instalacja</span><span class="sxs-lookup"><span data-stu-id="23dec-108">Installation</span></span>

<span data-ttu-id="23dec-109">Chociaż aplikacje w języku Q# można tworzyć w dowolnym środowisku IDE, zalecamy korzystanie z programu Visual Studio Code (VS Code) lub Visual Studio jako środowiska IDE do lokalnego programowania aplikacji w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="23dec-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="23dec-110">W przypadku programowania w chmurze za pośrednictwem przeglądarki internetowej zalecamy używanie programu Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="23dec-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="23dec-111">Programowanie w tych środowiskach umożliwia wykorzystanie bogatych funkcji rozszerzenia QDK, takich jak ostrzeżenia, wyróżnianie składni, szablony projektów i wiele innych.</span><span class="sxs-lookup"><span data-stu-id="23dec-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="23dec-112">Aby skonfigurować na potrzeby programu VS Code:</span><span class="sxs-lookup"><span data-stu-id="23dec-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="23dec-113">Pobierz i zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac).</span><span class="sxs-lookup"><span data-stu-id="23dec-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="23dec-114">Zainstaluj [zestaw Microsoft QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="23dec-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="23dec-115">Aby skonfigurować na potrzeby programu Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="23dec-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="23dec-116">Pobierz i zainstaluj program [Visual Studio](https://visualstudio.microsoft.com/downloads/) w wersji 16.3 lub nowszej z włączonym pakietem roboczym Tworzenie aplikacji dla wielu platform w środowisku .NET Core.</span><span class="sxs-lookup"><span data-stu-id="23dec-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="23dec-117">Pobierz i zainstaluj [zestaw Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="23dec-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="23dec-118">Aby skonfigurować na potrzeby innego środowiska:</span><span class="sxs-lookup"><span data-stu-id="23dec-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="23dec-119">Wprowadź następujące polecenie w wierszu polecenia</span><span class="sxs-lookup"><span data-stu-id="23dec-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="23dec-120">Aby skonfigurować na potrzeby usługi Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="23dec-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="23dec-121">Utwórz [konto platformy Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="23dec-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="23dec-122">Utwórz środowisko programu Codespaces.</span><span class="sxs-lookup"><span data-stu-id="23dec-122">Create a Codespaces environment.</span></span> <span data-ttu-id="23dec-123">Postępuj zgodnie z [przewodnikiem Szybki start](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="23dec-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="23dec-124">Podczas tworzenia środowiska Codespace zalecamy wprowadzenie wartości `microsoft/Quantum` w polu „Git Repository” (Repozytorium Git) w celu załadowania ustawień specyficznych dla zestawu QDK.</span><span class="sxs-lookup"><span data-stu-id="23dec-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="23dec-125">Teraz możesz uruchomić nowe środowisko i rozpocząć programowanie w przeglądarce za pomocą [środowiska IDE programu VS Codespaces w chmurze](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="23dec-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="23dec-126">Alternatywnie można korzystać z lokalnej instalacji programu VS Code i używać Codespaces jako [środowiska zdalnego](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="23dec-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="23dec-127">Programowanie przy użyciu języka Q#</span><span class="sxs-lookup"><span data-stu-id="23dec-127">Develop with Q#</span></span>

<span data-ttu-id="23dec-128">Postępuj zgodnie z instrukcjami na karcie odpowiadającej Twojemu środowisku programistycznemu.</span><span class="sxs-lookup"><span data-stu-id="23dec-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="23dec-129">VS Code</span><span class="sxs-lookup"><span data-stu-id="23dec-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="23dec-130">Aby utworzyć nowy projekt:</span><span class="sxs-lookup"><span data-stu-id="23dec-130">To create a new project:</span></span>

1. <span data-ttu-id="23dec-131">Kliknij pozycję **View** -> **Command Palette** (Widok -> Paleta poleceń), a następnie wybierz polecenie **Q#: Create New Project** (Q#: utwórz nowy projekt).</span><span class="sxs-lookup"><span data-stu-id="23dec-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="23dec-132">Kliknij pozycję **Standalone console application** (Autonomiczna aplikacja konsolowa).</span><span class="sxs-lookup"><span data-stu-id="23dec-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="23dec-133">Przejdź do lokalizacji, w której ma zostać zapisany projekt.</span><span class="sxs-lookup"><span data-stu-id="23dec-133">Navigate to the location to save the project.</span></span> <span data-ttu-id="23dec-134">Wpisz nową nazwę projektu i kliknij pozycję **Create project** (Utwórz projekt).</span><span class="sxs-lookup"><span data-stu-id="23dec-134">Enter the project name and click **Create Project**.</span></span>
4. <span data-ttu-id="23dec-135">Po pomyślnym utworzeniu projektu kliknij pozycję **Open new project...** (Otwórz nowy projekt) w prawym dolnym rogu.</span><span class="sxs-lookup"><span data-stu-id="23dec-135">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="23dec-136">Zapoznaj się z projektem.</span><span class="sxs-lookup"><span data-stu-id="23dec-136">Inspect the project.</span></span> <span data-ttu-id="23dec-137">Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="23dec-137">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="23dec-138">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="23dec-138">To run the application:</span></span>

1. <span data-ttu-id="23dec-139">Kliknij pozycję **Terminal** -> **New Terminal** (Nowy terminal).</span><span class="sxs-lookup"><span data-stu-id="23dec-139">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="23dec-140">W wierszu polecenia terminalu wprowadź polecenie `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="23dec-140">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="23dec-141">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="23dec-141">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="23dec-142">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu VS Code dla języka Q#.</span><span class="sxs-lookup"><span data-stu-id="23dec-142">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="23dec-143">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="23dec-143">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="23dec-144">Program Visual Studio</span><span class="sxs-lookup"><span data-stu-id="23dec-144">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="23dec-145">Zweryfikuj instalację programu Visual Studio, tworząc aplikację Q# w języku `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="23dec-145">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="23dec-146">Aby utworzyć nową aplikację w języku Q#:</span><span class="sxs-lookup"><span data-stu-id="23dec-146">To create a new Q# application:</span></span>

1. <span data-ttu-id="23dec-147">Otwórz program Visual Studio, a następnie wybierz kolejno opcje **Plik** -> **Nowy** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="23dec-147">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="23dec-148">Wpisz `Q#` w polu wyszukiwania, wybierz pozycję **Aplikacja Q#** , a następnie kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="23dec-148">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="23dec-149">Wprowadź nazwę i lokalizację aplikacji, a następnie kliknij pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="23dec-149">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="23dec-150">Zapoznaj się z projektem.</span><span class="sxs-lookup"><span data-stu-id="23dec-150">Inspect the project.</span></span> <span data-ttu-id="23dec-151">Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="23dec-151">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="23dec-152">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="23dec-152">To run the application:</span></span>

1. <span data-ttu-id="23dec-153">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**.</span><span class="sxs-lookup"><span data-stu-id="23dec-153">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="23dec-154">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="23dec-154">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="23dec-155">Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="23dec-155">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="23dec-156">Inne edytory przy użyciu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="23dec-156">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="23dec-157">Zweryfikuj instalację, tworząc aplikację `Hello World` w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="23dec-157">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="23dec-158">Tworzenie nowej aplikacji:</span><span class="sxs-lookup"><span data-stu-id="23dec-158">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="23dec-159">Przechodzenie do katalogu aplikacji:</span><span class="sxs-lookup"><span data-stu-id="23dec-159">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="23dec-160">Ten katalog powinien teraz zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="23dec-160">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="23dec-161">Ten szablon można zmodyfikować za pomocą edytora tekstów i zastąpić go własnymi aplikacjami kwantowymi.</span><span class="sxs-lookup"><span data-stu-id="23dec-161">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="23dec-162">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="23dec-162">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="23dec-163">Powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="23dec-163">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="23dec-164">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="23dec-164">Next steps</span></span>

<span data-ttu-id="23dec-165">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="23dec-165">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

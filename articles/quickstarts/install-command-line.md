---
title: Tworzenie przy użyciu aplikacji w języku Q#
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
ms.openlocfilehash: 68f530d80e5c5f40dc2bcbb185879c3cb6f93f91
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834418"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="870e6-103">Tworzenie przy użyciu aplikacji w języku Q#</span><span class="sxs-lookup"><span data-stu-id="870e6-103">Develop with Q# applications</span></span>

<span data-ttu-id="870e6-104">Postępuj zgodnie z instrukcjami na karcie odpowiadającej Twojemu środowisku.</span><span class="sxs-lookup"><span data-stu-id="870e6-104">Follow the instructions at the tab corresponding to your environment.</span></span>

<span data-ttu-id="870e6-105">Programy w języku Q# można uruchamiać samodzielnie, bez sterownika w języku hosta, takim jak C#, F# czy Python.</span><span class="sxs-lookup"><span data-stu-id="870e6-105">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="870e6-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="870e6-106">Prerequisites</span></span>

- [<span data-ttu-id="870e6-107">Zestaw .NET Core SDK 3.1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="870e6-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="870e6-108">Instalacja</span><span class="sxs-lookup"><span data-stu-id="870e6-108">Installation</span></span>

<span data-ttu-id="870e6-109">Chociaż aplikacje w języku Q# można tworzyć w dowolnym środowisku IDE, zalecamy korzystanie z programu Visual Studio Code (VS Code) lub Visual Studio jako środowiska IDE do lokalnego programowania aplikacji w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="870e6-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="870e6-110">W przypadku programowania w chmurze za pośrednictwem przeglądarki internetowej zalecamy używanie programu Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="870e6-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="870e6-111">Programowanie w tych środowiskach obejmuje bogate funkcje rozszerzenia QDK, takie jak ostrzeżenia, wyróżnianie składni, szablony projektów i wiele innych.</span><span class="sxs-lookup"><span data-stu-id="870e6-111">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="870e6-112">Aby skonfigurować program VS Code:</span><span class="sxs-lookup"><span data-stu-id="870e6-112">To configure VS Code:</span></span>

1. <span data-ttu-id="870e6-113">Pobierz i zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac).</span><span class="sxs-lookup"><span data-stu-id="870e6-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="870e6-114">Zainstaluj [zestaw Microsoft QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="870e6-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="870e6-115">Aby skonfigurować program Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="870e6-115">To configure Visual Studio:</span></span>

1. <span data-ttu-id="870e6-116">Pobierz i zainstaluj program [Visual Studio](https://visualstudio.microsoft.com/downloads/) w wersji 16.3 lub nowszej z włączonym pakietem roboczym Tworzenie aplikacji dla wielu platform w środowisku .NET Core.</span><span class="sxs-lookup"><span data-stu-id="870e6-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="870e6-117">Pobierz i zainstaluj [zestaw Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="870e6-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="870e6-118">Aby skonfigurować program Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="870e6-118">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="870e6-119">Utwórz [konto platformy Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="870e6-119">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="870e6-120">Utwórz środowisko programu Codespaces.</span><span class="sxs-lookup"><span data-stu-id="870e6-120">Create a Codespaces environment.</span></span> <span data-ttu-id="870e6-121">Postępuj zgodnie z [przewodnikiem Szybki start](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="870e6-121">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="870e6-122">Podczas tworzenia środowiska Codespace zalecamy wprowadzenie wartości `microsoft/Quantum` w polu „Git Repository” (Repozytorium Git) w celu załadowania ustawień specyficznych dla zestawu QDK.</span><span class="sxs-lookup"><span data-stu-id="870e6-122">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="870e6-123">Teraz możesz uruchomić nowe środowisko i rozpocząć programowanie w przeglądarce za pomocą [środowiska IDE programu VS Codespaces w chmurze](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="870e6-123">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="870e6-124">Alternatywnie można korzystać z lokalnej instalacji programu VS Code i używać Codespaces jako [środowiska zdalnego](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="870e6-124">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="870e6-125">Aby zainstalować zestaw QDK dla innego środowiska, w wierszu polecenia wprowadź następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="870e6-125">To install the QDK for another environment, enter the following at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="870e6-126">Programowanie przy użyciu języka Q#</span><span class="sxs-lookup"><span data-stu-id="870e6-126">Develop with Q#</span></span>

<span data-ttu-id="870e6-127">Postępuj zgodnie z instrukcjami na karcie odpowiadającej Twojemu środowisku.</span><span class="sxs-lookup"><span data-stu-id="870e6-127">Follow the instructions on the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="870e6-128">VS Code</span><span class="sxs-lookup"><span data-stu-id="870e6-128">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="870e6-129">Aby utworzyć nowy projekt:</span><span class="sxs-lookup"><span data-stu-id="870e6-129">To create a new project:</span></span>

1. <span data-ttu-id="870e6-130">Kliknij pozycję **View** -> **Command Palette** (Widok -> Paleta poleceń), a następnie wybierz polecenie **Q#: Create New Project** (Q#: utwórz nowy projekt).</span><span class="sxs-lookup"><span data-stu-id="870e6-130">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="870e6-131">Kliknij pozycję **Standalone console application** (Autonomiczna aplikacja konsolowa).</span><span class="sxs-lookup"><span data-stu-id="870e6-131">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="870e6-132">Przejdź do lokalizacji, w której chcesz zapisać projekt, a następnie kliknij pozycję **Create project** (Utwórz projekt).</span><span class="sxs-lookup"><span data-stu-id="870e6-132">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="870e6-133">Po pomyślnym utworzeniu projektu kliknij pozycję **Open new project...** (Otwórz nowy projekt) w prawym dolnym rogu.</span><span class="sxs-lookup"><span data-stu-id="870e6-133">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="870e6-134">Zapoznaj się z projektem.</span><span class="sxs-lookup"><span data-stu-id="870e6-134">Inspect the project.</span></span> <span data-ttu-id="870e6-135">Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="870e6-135">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="870e6-136">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="870e6-136">To run the application:</span></span>

1. <span data-ttu-id="870e6-137">Kliknij pozycję **Terminal** -> **New Terminal** (Nowy terminal).</span><span class="sxs-lookup"><span data-stu-id="870e6-137">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="870e6-138">W wierszu polecenia terminalu wprowadź polecenie `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="870e6-138">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="870e6-139">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="870e6-139">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="870e6-140">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu VS Code dla języka Q#.</span><span class="sxs-lookup"><span data-stu-id="870e6-140">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="870e6-141">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="870e6-141">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="870e6-142">Program Visual Studio</span><span class="sxs-lookup"><span data-stu-id="870e6-142">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="870e6-143">Zweryfikuj instalację programu Visual Studio, tworząc aplikację Q# w języku `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="870e6-143">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="870e6-144">Aby utworzyć nową aplikację w języku Q#:</span><span class="sxs-lookup"><span data-stu-id="870e6-144">To create a new Q# application:</span></span>

1. <span data-ttu-id="870e6-145">Otwórz program Visual Studio, a następnie wybierz kolejno opcje **Plik** -> **Nowy** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="870e6-145">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="870e6-146">Wpisz `Q#` w polu wyszukiwania, wybierz pozycję **Aplikacja Q#** , a następnie kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="870e6-146">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="870e6-147">Wprowadź nazwę i lokalizację aplikacji, a następnie kliknij pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="870e6-147">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="870e6-148">Zapoznaj się z projektem.</span><span class="sxs-lookup"><span data-stu-id="870e6-148">Inspect the project.</span></span> <span data-ttu-id="870e6-149">Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="870e6-149">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="870e6-150">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="870e6-150">To run the application:</span></span>

1. <span data-ttu-id="870e6-151">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**.</span><span class="sxs-lookup"><span data-stu-id="870e6-151">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="870e6-152">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="870e6-152">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="870e6-153">Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="870e6-153">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="870e6-154">Inne edytory przy użyciu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="870e6-154">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="870e6-155">Zweryfikuj instalację, tworząc aplikację `Hello World` w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="870e6-155">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="870e6-156">Zainstaluj szablony projektów.</span><span class="sxs-lookup"><span data-stu-id="870e6-156">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="870e6-157">Tworzenie nowej aplikacji:</span><span class="sxs-lookup"><span data-stu-id="870e6-157">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="870e6-158">Przechodzenie do katalogu aplikacji:</span><span class="sxs-lookup"><span data-stu-id="870e6-158">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="870e6-159">Ten katalog powinien teraz zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="870e6-159">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="870e6-160">Ten szablon można zmodyfikować za pomocą edytora tekstów i zastąpić go własnymi aplikacjami kwantowymi.</span><span class="sxs-lookup"><span data-stu-id="870e6-160">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="870e6-161">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="870e6-161">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="870e6-162">Powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="870e6-162">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="870e6-163">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="870e6-163">Next steps</span></span>

<span data-ttu-id="870e6-164">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="870e6-164">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

---
title: Tworzenie aplikacji wiersza polecenia w języku Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884280"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="9b863-102">Tworzenie aplikacji wiersza polecenia w języku Q#</span><span class="sxs-lookup"><span data-stu-id="9b863-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="9b863-103">Programy w języku Q# można wykonywać samodzielnie, bez sterownika w języku hosta, takim jak C#, F#, czy Python.</span><span class="sxs-lookup"><span data-stu-id="9b863-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9b863-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="9b863-104">Prerequisites</span></span>

- [<span data-ttu-id="9b863-105">Zestaw .NET Core SDK 3.1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="9b863-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="9b863-106">Instalacja</span><span class="sxs-lookup"><span data-stu-id="9b863-106">Installation</span></span>

<span data-ttu-id="9b863-107">Chociaż aplikacje wiersza polecenia w języku Q# można tworzyć w dowolnym środowisku IDE, zalecamy korzystanie z programu Visual Studio Code (VS Code) lub Visual Studio jako środowiska IDE dla aplikacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="9b863-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="9b863-108">Programowanie w tych środowiskach obejmuje bogate funkcje rozszerzenia QDK, takie jak ostrzeżenia, wyróżnianie składni, szablony projektów i wiele innych.</span><span class="sxs-lookup"><span data-stu-id="9b863-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="9b863-109">Aby skonfigurować program VS Code:</span><span class="sxs-lookup"><span data-stu-id="9b863-109">To configure VS Code:</span></span>

1. <span data-ttu-id="9b863-110">Pobierz i zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac).</span><span class="sxs-lookup"><span data-stu-id="9b863-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="9b863-111">Zainstaluj [zestaw Microsoft QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="9b863-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="9b863-112">Aby skonfigurować program Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="9b863-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="9b863-113">Pobierz i zainstaluj program [Visual Studio](https://visualstudio.microsoft.com/downloads/) w wersji 16.3 lub nowszej z włączonym pakietem roboczym Tworzenie aplikacji dla wielu platform w środowisku .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9b863-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="9b863-114">Pobierz i zainstaluj [zestaw Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="9b863-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="9b863-115">Aby zainstalować zestaw QDK dla innego środowiska, wprowadź w wierszu polecenia:</span><span class="sxs-lookup"><span data-stu-id="9b863-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="9b863-116">Programowanie przy użyciu języka Q#</span><span class="sxs-lookup"><span data-stu-id="9b863-116">Develop with Q#</span></span>

<span data-ttu-id="9b863-117">Postępuj zgodnie z instrukcjami na karcie odpowiadającej Twojemu środowisku.</span><span class="sxs-lookup"><span data-stu-id="9b863-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="9b863-118">VS Code</span><span class="sxs-lookup"><span data-stu-id="9b863-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="9b863-119">Zainstaluj szablony projektów języka Q#:</span><span class="sxs-lookup"><span data-stu-id="9b863-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="9b863-120">Otwórz program VS Code.</span><span class="sxs-lookup"><span data-stu-id="9b863-120">Open VS Code.</span></span>
2. <span data-ttu-id="9b863-121">Przejdź do pozycji **View** -> **Command Palette** (Widok > Paleta poleceń).</span><span class="sxs-lookup"><span data-stu-id="9b863-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="9b863-122">Wybierz pozycję **Q#: Install project templates** (Q#: zainstaluj szablony projektów).</span><span class="sxs-lookup"><span data-stu-id="9b863-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="9b863-123">Po wyświetleniu komunikatu **Project templates installed successfully** (Pomyślnie zainstalowano szablony projektów) zestaw QDK jest gotowy do użycia z Twoimi aplikacjami i bibliotekami.</span><span class="sxs-lookup"><span data-stu-id="9b863-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="9b863-124">Aby utworzyć nowy projekt:</span><span class="sxs-lookup"><span data-stu-id="9b863-124">To create a new project:</span></span>

1. <span data-ttu-id="9b863-125">Kliknij pozycję **View** -> **Command Palette**, a następnie wybierz polecenie **Q#: Create New Project** (Q#: utwórz nowy projekt).</span><span class="sxs-lookup"><span data-stu-id="9b863-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="9b863-126">Kliknij pozycję **Standalone console application** (Autonomiczna aplikacja konsolowa).</span><span class="sxs-lookup"><span data-stu-id="9b863-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="9b863-127">Przejdź do lokalizacji, w której chcesz zapisać projekt, a następnie kliknij pozycję **Create project** (Utwórz projekt).</span><span class="sxs-lookup"><span data-stu-id="9b863-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="9b863-128">Po pomyślnym utworzeniu projektu kliknij pozycję **Open new project...** (Otwórz nowy projekt) w prawym dolnym rogu.</span><span class="sxs-lookup"><span data-stu-id="9b863-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="9b863-129">Zapoznaj się z projektem.</span><span class="sxs-lookup"><span data-stu-id="9b863-129">Inspect the project.</span></span> <span data-ttu-id="9b863-130">Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="9b863-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="9b863-131">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="9b863-131">To run the application:</span></span>
1. <span data-ttu-id="9b863-132">Kliknij pozycję **Terminal** -> **New Terminal** (Nowy terminal).</span><span class="sxs-lookup"><span data-stu-id="9b863-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="9b863-133">W wierszu polecenia terminalu wprowadź polecenie `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="9b863-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="9b863-134">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="9b863-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="9b863-135">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu VS Code dla języka Q#.</span><span class="sxs-lookup"><span data-stu-id="9b863-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="9b863-136">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="9b863-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="9b863-137">Program Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9b863-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="9b863-138">Zweryfikuj instalację programu Visual Studio, tworząc aplikację `Hello World` w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="9b863-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="9b863-139">Aby utworzyć nową aplikację w języku Q#:</span><span class="sxs-lookup"><span data-stu-id="9b863-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="9b863-140">Otwórz program Visual Studio, a następnie wybierz kolejno opcje **Plik** -> **Nowy** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="9b863-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="9b863-141">Wpisz `Q#` w polu wyszukiwania, wybierz pozycję **Aplikacja Q#** , a następnie kliknij pozycję **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="9b863-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="9b863-142">Wprowadź nazwę i lokalizację aplikacji, a następnie kliknij pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="9b863-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="9b863-143">Zapoznaj się z projektem.</span><span class="sxs-lookup"><span data-stu-id="9b863-143">Inspect the project.</span></span> <span data-ttu-id="9b863-144">Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="9b863-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="9b863-145">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="9b863-145">To run the application:</span></span>
1. <span data-ttu-id="9b863-146">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**.</span><span class="sxs-lookup"><span data-stu-id="9b863-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="9b863-147">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="9b863-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="9b863-148">Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="9b863-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="9b863-149">Inne edytory z wierszem polecenia</span><span class="sxs-lookup"><span data-stu-id="9b863-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="9b863-150">Zweryfikuj instalację, tworząc aplikację `Hello World` w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="9b863-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="9b863-151">Tworzenie nowej aplikacji:</span><span class="sxs-lookup"><span data-stu-id="9b863-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="9b863-152">Przechodzenie do katalogu aplikacji:</span><span class="sxs-lookup"><span data-stu-id="9b863-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="9b863-153">Ten katalog powinien teraz zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="9b863-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="9b863-154">Ten szablon można zmodyfikować za pomocą edytora tekstów i zastąpić go własnymi aplikacjami kwantowymi.</span><span class="sxs-lookup"><span data-stu-id="9b863-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="9b863-155">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="9b863-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="9b863-156">Powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="9b863-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="9b863-157">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="9b863-157">Next steps</span></span>

<span data-ttu-id="9b863-158">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="9b863-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

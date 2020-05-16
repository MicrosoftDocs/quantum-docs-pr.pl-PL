---
title: 'Opracowywanie aplikacji z wiersza polecenia Q #'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426434"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="2fd4a-102">Opracowywanie aplikacji z wiersza polecenia Q #</span><span class="sxs-lookup"><span data-stu-id="2fd4a-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="2fd4a-103">Programy Q # można wykonać samodzielnie, bez sterownika w języku hosta, takim jak C#, F # lub Python.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="2fd4a-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2fd4a-104">Pre-requisites</span></span>

- [<span data-ttu-id="2fd4a-105">Zestaw .NET Core SDK 3,1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="2fd4a-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="2fd4a-106">Instalacja</span><span class="sxs-lookup"><span data-stu-id="2fd4a-106">Installation</span></span>

<span data-ttu-id="2fd4a-107">Podczas tworzenia aplikacji wiersza polecenia Q # w dowolnym środowisku IDE zalecamy używanie Visual Studio Code (VS Code) lub środowiska IDE programu Visual Studio dla aplikacji Q #.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="2fd4a-108">Programowanie w tych narzędziach zapewnia dostęp do rozbudowanych funkcji.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="2fd4a-109">Aby skonfigurować VS Code:</span><span class="sxs-lookup"><span data-stu-id="2fd4a-109">To configure VS Code:</span></span>

1. <span data-ttu-id="2fd4a-110">Pobierz i zainstaluj [vs Code](https://code.visualstudio.com/download) (Windows, Linux i Mac).</span><span class="sxs-lookup"><span data-stu-id="2fd4a-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="2fd4a-111">Zainstaluj [program Microsoft QDK dla vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="2fd4a-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="2fd4a-112">Aby skonfigurować program Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="2fd4a-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="2fd4a-113">Pobierz i zainstaluj [program Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 lub nowszy z włączonym obciążeniem programistycznym dla wielu platform platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="2fd4a-114">Pobierz i zainstaluj [program Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="2fd4a-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="2fd4a-115">Programowanie przy użyciu narzędzia Q # VS Code</span><span class="sxs-lookup"><span data-stu-id="2fd4a-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="2fd4a-116">Zainstaluj szablony projektu Q #:</span><span class="sxs-lookup"><span data-stu-id="2fd4a-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="2fd4a-117">Otwórz VS Code.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-117">Open VS Code.</span></span>
2. <span data-ttu-id="2fd4a-118">Kliknij pozycję **Widok**  ->  **paleta poleceń**.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="2fd4a-119">Wybierz pozycję **Q #: Instalowanie szablonów projektu**.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="2fd4a-120">Po **pomyślnym wyświetleniu szablonu projektu** QDK jest gotowy do użycia z własnymi aplikacjami i bibliotekami.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="2fd4a-121">Aby utworzyć nowy projekt:</span><span class="sxs-lookup"><span data-stu-id="2fd4a-121">To create a new project:</span></span>

1. <span data-ttu-id="2fd4a-122">Kliknij pozycję **Wyświetl**  ->  **paletę poleceń** i wybierz pozycję **Q #: Utwórz nowy projekt**.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="2fd4a-123">Kliknij **autonomiczną aplikację konsolową**.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="2fd4a-124">Przejdź do lokalizacji, w której chcesz zapisać projekt, a następnie kliknij pozycję **Utwórz projekt**.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="2fd4a-125">Po pomyślnym utworzeniu projektu kliknij pozycję **Otwórz nowy projekt..** . w prawym dolnym rogu.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="2fd4a-126">Zbadaj projekt.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-126">Inspect the project.</span></span> <span data-ttu-id="2fd4a-127">Powinien zostać wyświetlony plik źródłowy o nazwie `Program.qs` , który jest programem Q #, który definiuje prostą operację do drukowania komunikatu w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="2fd4a-128">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="2fd4a-128">To run the application:</span></span>
1. <span data-ttu-id="2fd4a-129">Kliknij pozycję **Terminal**  ->  **Nowy terminal**.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="2fd4a-130">W wierszu polecenia terminalu wprowadź `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="2fd4a-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="2fd4a-131">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2fd4a-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="2fd4a-132">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie VS Code Q #.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="2fd4a-133">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="2fd4a-134">Programowanie za pomocą narzędzia Q # przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2fd4a-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="2fd4a-135">Zweryfikuj instalację programu Visual Studio, tworząc aplikację Q # `Hello World` .</span><span class="sxs-lookup"><span data-stu-id="2fd4a-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="2fd4a-136">Aby utworzyć nową aplikację Q #:</span><span class="sxs-lookup"><span data-stu-id="2fd4a-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="2fd4a-137">Otwórz program Visual Studio, a następnie kliknij pozycję **plik**  ->  **Nowy**  ->  **projekt**.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="2fd4a-138">Wpisz `Q#` w polu wyszukiwania, wybierz pozycję **Q # aplikacja** i kliknij **przycisk Dalej**.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="2fd4a-139">Wprowadź nazwę i lokalizację aplikacji, a następnie kliknij przycisk **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="2fd4a-140">Zbadaj projekt.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-140">Inspect the project.</span></span> <span data-ttu-id="2fd4a-141">Powinien zostać wyświetlony plik źródłowy o nazwie `Program.qs` , który jest programem Q #, który definiuje prostą operację do drukowania komunikatu w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="2fd4a-142">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="2fd4a-142">To run the application:</span></span>
1. <span data-ttu-id="2fd4a-143">Wybierz pozycję **Debuguj**  ->  **Uruchom bez debugowania**.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="2fd4a-144">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="2fd4a-145">Jeśli masz wiele projektów w ramach jednego rozwiązania programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="2fd4a-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="2fd4a-146">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="2fd4a-146">Next steps</span></span>

<span data-ttu-id="2fd4a-147">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="2fd4a-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

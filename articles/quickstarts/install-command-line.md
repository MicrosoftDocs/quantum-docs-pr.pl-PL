---
title: Tworzenie aplikacji wiersza polecenia w języku Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274190"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="3e086-102">Tworzenie aplikacji wiersza polecenia w języku Q#</span><span class="sxs-lookup"><span data-stu-id="3e086-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="3e086-103">Programy w języku Q# można wykonywać samodzielnie, bez sterownika w języku hosta, takim jak C#, F#, czy Python.</span><span class="sxs-lookup"><span data-stu-id="3e086-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3e086-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="3e086-104">Prerequisites</span></span>

- [<span data-ttu-id="3e086-105">Zestaw .NET Core SDK 3.1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="3e086-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="3e086-106">Instalacja</span><span class="sxs-lookup"><span data-stu-id="3e086-106">Installation</span></span>

<span data-ttu-id="3e086-107">Chociaż aplikacje wiersza polecenia w języku Q# można tworzyć w dowolnym środowisku IDE, zalecamy korzystanie z programu Visual Studio Code (VS Code) lub Visual Studio jako środowiska IDE dla aplikacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="3e086-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="3e086-108">Te narzędzia programistyczne zapewniają dostęp do rozbudowanych funkcji.</span><span class="sxs-lookup"><span data-stu-id="3e086-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="3e086-109">Aby skonfigurować program VS Code:</span><span class="sxs-lookup"><span data-stu-id="3e086-109">To configure VS Code:</span></span>

1. <span data-ttu-id="3e086-110">Pobierz i zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac).</span><span class="sxs-lookup"><span data-stu-id="3e086-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="3e086-111">Zainstaluj [zestaw Microsoft QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="3e086-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="3e086-112">Aby skonfigurować program Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="3e086-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="3e086-113">Pobierz i zainstaluj program [Visual Studio](https://visualstudio.microsoft.com/downloads/) w wersji 16.3 lub nowszej z włączonym pakietem roboczym Tworzenie aplikacji dla wielu platform w środowisku .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3e086-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="3e086-114">Pobierz i zainstaluj [zestaw Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="3e086-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="3e086-115">Programowanie w języku Q# przy użyciu programu VS Code</span><span class="sxs-lookup"><span data-stu-id="3e086-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="3e086-116">Zainstaluj szablony projektów języka Q#:</span><span class="sxs-lookup"><span data-stu-id="3e086-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="3e086-117">Otwórz program VS Code.</span><span class="sxs-lookup"><span data-stu-id="3e086-117">Open VS Code.</span></span>
2. <span data-ttu-id="3e086-118">Przejdź do pozycji **View** -> **Command Palette** (Widok > Paleta poleceń).</span><span class="sxs-lookup"><span data-stu-id="3e086-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="3e086-119">Wybierz pozycję **Q#: Install project templates** (Q#: zainstaluj szablony projektów).</span><span class="sxs-lookup"><span data-stu-id="3e086-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="3e086-120">Po wyświetleniu komunikatu **Project templates installed successfully** (Pomyślnie zainstalowano szablony projektów) zestaw QDK jest gotowy do użycia z Twoimi aplikacjami i bibliotekami.</span><span class="sxs-lookup"><span data-stu-id="3e086-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="3e086-121">Aby utworzyć nowy projekt:</span><span class="sxs-lookup"><span data-stu-id="3e086-121">To create a new project:</span></span>

1. <span data-ttu-id="3e086-122">Kliknij pozycję **View** -> **Command Palette**, a następnie wybierz polecenie **Q#: Create New Project** (Q#: utwórz nowy projekt).</span><span class="sxs-lookup"><span data-stu-id="3e086-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="3e086-123">Kliknij pozycję **Standalone console application** (Autonomiczna aplikacja konsolowa).</span><span class="sxs-lookup"><span data-stu-id="3e086-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="3e086-124">Przejdź do lokalizacji, w której chcesz zapisać projekt, a następnie kliknij pozycję **Create project** (Utwórz projekt).</span><span class="sxs-lookup"><span data-stu-id="3e086-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="3e086-125">Po pomyślnym utworzeniu projektu kliknij pozycję **Open new project...** (Otwórz nowy projekt) w prawym dolnym rogu.</span><span class="sxs-lookup"><span data-stu-id="3e086-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="3e086-126">Zapoznaj się z projektem.</span><span class="sxs-lookup"><span data-stu-id="3e086-126">Inspect the project.</span></span> <span data-ttu-id="3e086-127">Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="3e086-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="3e086-128">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="3e086-128">To run the application:</span></span>
1. <span data-ttu-id="3e086-129">Kliknij pozycję **Terminal** -> **New Terminal** (Nowy terminal).</span><span class="sxs-lookup"><span data-stu-id="3e086-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="3e086-130">W wierszu polecenia terminalu wprowadź polecenie `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="3e086-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="3e086-131">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="3e086-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="3e086-132">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu VS Code dla języka Q#.</span><span class="sxs-lookup"><span data-stu-id="3e086-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="3e086-133">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="3e086-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="3e086-134">Programowanie w języku Q# w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3e086-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="3e086-135">Zweryfikuj instalację programu Visual Studio, tworząc aplikację `Hello World` w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="3e086-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="3e086-136">Aby utworzyć nową aplikację w języku Q#:</span><span class="sxs-lookup"><span data-stu-id="3e086-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="3e086-137">Otwórz program Visual Studio, a następnie wybierz kolejno opcje **Plik** -> **Nowy** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="3e086-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="3e086-138">Wpisz `Q#` w polu wyszukiwania, wybierz pozycję **Aplikacja Q#** , a następnie kliknij pozycję **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="3e086-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="3e086-139">Wprowadź nazwę i lokalizację aplikacji, a następnie kliknij pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="3e086-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="3e086-140">Zapoznaj się z projektem.</span><span class="sxs-lookup"><span data-stu-id="3e086-140">Inspect the project.</span></span> <span data-ttu-id="3e086-141">Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.</span><span class="sxs-lookup"><span data-stu-id="3e086-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="3e086-142">Aby uruchomić aplikację:</span><span class="sxs-lookup"><span data-stu-id="3e086-142">To run the application:</span></span>
1. <span data-ttu-id="3e086-143">Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**.</span><span class="sxs-lookup"><span data-stu-id="3e086-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="3e086-144">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="3e086-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="3e086-145">Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="3e086-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="3e086-146">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="3e086-146">Next steps</span></span>

<span data-ttu-id="3e086-147">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="3e086-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

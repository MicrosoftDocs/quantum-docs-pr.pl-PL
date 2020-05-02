---
title: 'Wykonaj programy Q # bez sterownika i języka hosta'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706805"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="101a3-102">Aplikacje wiersza polecenia Q #</span><span class="sxs-lookup"><span data-stu-id="101a3-102">Q# Command Line Applications</span></span>

<span data-ttu-id="101a3-103">Programy Q # można wykonać samodzielnie, bez sterownika w języku hosta, takim jak C#, F # lub Python.</span><span class="sxs-lookup"><span data-stu-id="101a3-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="101a3-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="101a3-104">Pre-requisites</span></span>

- [<span data-ttu-id="101a3-105">Zestaw .NET Core SDK 3,1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="101a3-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="101a3-106">Instalacja</span><span class="sxs-lookup"><span data-stu-id="101a3-106">Installation</span></span>

<span data-ttu-id="101a3-107">Podczas tworzenia aplikacji wiersza polecenia Q # w dowolnym środowisku IDE zdecydowanie zalecamy używanie Visual Studio Code (VS Code) lub środowiska IDE programu Visual Studio dla aplikacji Q #.</span><span class="sxs-lookup"><span data-stu-id="101a3-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="101a3-108">Za pomocą VS Code lub programu Visual Studio oraz rozszerzenia QDK Visual Studio Code uzyskujesz dostęp do bogatszej funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="101a3-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="101a3-109">Zainstaluj [vs Code](https://code.visualstudio.com/download) (systemy Windows, Linux i Mac)</span><span class="sxs-lookup"><span data-stu-id="101a3-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="101a3-110">Zainstaluj [rozszerzenie QDK dla vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) lub</span><span class="sxs-lookup"><span data-stu-id="101a3-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="101a3-111">Program [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 z włączonym obciążeniem programu .NET Core obsługującym projektowanie dla wielu platform</span><span class="sxs-lookup"><span data-stu-id="101a3-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="101a3-112">Pobierz i zainstaluj [rozszerzenie programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="101a3-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="101a3-113">Programowanie przy użyciu narzędzia Q # VS Code</span><span class="sxs-lookup"><span data-stu-id="101a3-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="101a3-114">Instalowanie szablonów projektów kwantowych:</span><span class="sxs-lookup"><span data-stu-id="101a3-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="101a3-115">Przejdź do **widoku** -> —**paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="101a3-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="101a3-116">Wybierz pozycję **Q #: Instalowanie szablonów projektu**</span><span class="sxs-lookup"><span data-stu-id="101a3-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="101a3-117">Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.</span><span class="sxs-lookup"><span data-stu-id="101a3-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="101a3-118">Tworzenie nowego projektu:</span><span class="sxs-lookup"><span data-stu-id="101a3-118">Create a new project:</span></span>
  - <span data-ttu-id="101a3-119">Przejdź do **widoku** -> —**paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="101a3-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="101a3-120">Wybierz pozycję **Q #: Utwórz nowy projekt**</span><span class="sxs-lookup"><span data-stu-id="101a3-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="101a3-121">Wybierz **autonomiczną aplikację konsolową**</span><span class="sxs-lookup"><span data-stu-id="101a3-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="101a3-122">Przejdź do lokalizacji w systemie plików, w której chcesz utworzyć aplikację</span><span class="sxs-lookup"><span data-stu-id="101a3-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="101a3-123">Po utworzeniu projektu kliknij przycisk **Otwórz nowy projekt**</span><span class="sxs-lookup"><span data-stu-id="101a3-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="101a3-124">Inspekcja projektu</span><span class="sxs-lookup"><span data-stu-id="101a3-124">Inspect the project</span></span>
  - <span data-ttu-id="101a3-125">Powinien zostać wyświetlony plik o nazwie `Program.qs` utworzony, który jest programem Q #, który definiuje prostą operację do drukowania komunikatu w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="101a3-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="101a3-126">Uruchom aplikację:</span><span class="sxs-lookup"><span data-stu-id="101a3-126">Run the application:</span></span>
  - <span data-ttu-id="101a3-127">Przejdź do **terminalu** -> **Nowy terminal**</span><span class="sxs-lookup"><span data-stu-id="101a3-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="101a3-128">Wprowadź wartość `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="101a3-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="101a3-129">W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="101a3-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="101a3-130">Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="101a3-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="101a3-131">Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.</span><span class="sxs-lookup"><span data-stu-id="101a3-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="101a3-132">Programowanie za pomocą narzędzia Q # przy użyciu programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="101a3-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="101a3-133">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="101a3-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="101a3-134">Tworzenie nowej aplikacji w języku Q#</span><span class="sxs-lookup"><span data-stu-id="101a3-134">Create a new Q# application</span></span>
  - <span data-ttu-id="101a3-135">Przejdź do **pliku** -> **Nowy** -> **projekt**</span><span class="sxs-lookup"><span data-stu-id="101a3-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="101a3-136">Wpisz `Q#` w polu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="101a3-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="101a3-137">Wybierz pozycję **Aplikacja Q#**</span><span class="sxs-lookup"><span data-stu-id="101a3-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="101a3-138">Wybierz pozycję **dalej**</span><span class="sxs-lookup"><span data-stu-id="101a3-138">Select **Next**</span></span>
  - <span data-ttu-id="101a3-139">Wybierz nazwę i lokalizację dla aplikacji</span><span class="sxs-lookup"><span data-stu-id="101a3-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="101a3-140">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="101a3-140">Select **Create**</span></span>

- <span data-ttu-id="101a3-141">Inspekcja projektu</span><span class="sxs-lookup"><span data-stu-id="101a3-141">Inspect the project</span></span>
  - <span data-ttu-id="101a3-142">Powinieneś zobaczyć, że plik o `Program.qs` nazwie został utworzony, który jest programem Q #, który definiuje prostą operację do drukowania komunikatu w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="101a3-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="101a3-143">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="101a3-143">Run the application</span></span>
  - <span data-ttu-id="101a3-144">Wybierz pozycję **Debuguj** -> **Uruchom bez debugowania**</span><span class="sxs-lookup"><span data-stu-id="101a3-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="101a3-145">W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.</span><span class="sxs-lookup"><span data-stu-id="101a3-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="101a3-146">Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.</span><span class="sxs-lookup"><span data-stu-id="101a3-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="101a3-147">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="101a3-147">What's next?</span></span>

<span data-ttu-id="101a3-148">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="101a3-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>

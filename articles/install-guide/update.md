---
title: Dowiedz się, jak aktualizować Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ed2a90749bbe245dde97424fc3191682f995d85b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819743"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="1f2c8-102">Aktualizowanie Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="1f2c8-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="1f2c8-103">Dowiedz się, jak zaktualizować Microsoft Quantum Development Kit (QDK) do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="1f2c8-104">W tym artykule przyjęto założenie, że zainstalowano już QDK.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="1f2c8-105">Jeśli instalujesz po raz pierwszy, zapoznaj się z [Podręcznikiem instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="1f2c8-106">Zalecamy zachowywanie aktualności przy użyciu najnowszej wersji QDK.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-106">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="1f2c8-107">Postępuj zgodnie z tym przewodnikiem aktualizacji, aby przeprowadzić uaktualnienie do najnowszej wersji programu QDK.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-107">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="1f2c8-108">Proces składa się z dwóch części:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-108">The process consists of two parts:</span></span>
1. <span data-ttu-id="1f2c8-109">Aktualizowanie istniejących plików i projektów Q # w celu wyrównania kodu przy użyciu dowolnej zaktualizowanej składni</span><span class="sxs-lookup"><span data-stu-id="1f2c8-109">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="1f2c8-110">Aktualizowanie samej QDK dla wybranego środowiska programistycznego</span><span class="sxs-lookup"><span data-stu-id="1f2c8-110">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="1f2c8-111">Aktualizowanie projektów Q #</span><span class="sxs-lookup"><span data-stu-id="1f2c8-111">Updating Q# Projects</span></span> 

<span data-ttu-id="1f2c8-112">Bez względu na to, czy C# używasz programu lub języka Python do hostowania operacji q #, postępuj zgodnie z tymi instrukcjami, aby zaktualizować projekty q #.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-112">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="1f2c8-113">Najpierw sprawdź, czy masz najnowszą wersję [zestaw .NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-113">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="1f2c8-114">Uruchom następujące polecenie w wierszu polecenia:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-114">Run the following command in the command prompt:</span></span>
    ```bash
    dotnet --version
    ```
<span data-ttu-id="1f2c8-115">Sprawdź, czy dane wyjściowe są `3.1.100` lub nowsze.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-115">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="1f2c8-116">Jeśli nie, zainstaluj [najnowszą wersję](https://dotnet.microsoft.com/download) i sprawdź ponownie.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-116">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="1f2c8-117">Następnie postępuj zgodnie z poniższymi instrukcjami, w zależności od konfiguracji (Visual Studio, Visual Studio Code lub bezpośrednio w wierszu polecenia).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-117">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="1f2c8-118">Aktualizuj projekty Q # w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1f2c8-118">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="1f2c8-119">Aktualizacja do najnowszej wersji programu Visual Studio 2019, zobacz [tutaj](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) , aby uzyskać instrukcje</span><span class="sxs-lookup"><span data-stu-id="1f2c8-119">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="1f2c8-120">Otwórz rozwiązanie w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1f2c8-120">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="1f2c8-121">Z menu wybierz opcję **kompiluj** -> **Wyczyść rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="1f2c8-121">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="1f2c8-122">W każdym z plików. csproj zaktualizuj platformę docelową do `netcoreapp3.0` (lub `netstandard2.1`, jeśli jest to projekt biblioteki).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-122">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="1f2c8-123">Oznacza to, że edycja wierszy formularza:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-123">That is, edit lines of the form:</span></span>
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    <span data-ttu-id="1f2c8-124">Więcej szczegółowych informacji na temat określania platform docelowych można znaleźć [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-124">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="1f2c8-125">Zapisz i Zamknij wszystkie pliki w rozwiązaniu</span><span class="sxs-lookup"><span data-stu-id="1f2c8-125">Save and close all files in your solution</span></span>
6. <span data-ttu-id="1f2c8-126">Wybierz **narzędzia** ->  -> **wiersza polecenia** **wiersz polecenia dla deweloperów**</span><span class="sxs-lookup"><span data-stu-id="1f2c8-126">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="1f2c8-127">Dla każdego projektu w rozwiązaniu Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-127">For each project in the solution, run the following command:</span></span>
    ```bash
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```
    <span data-ttu-id="1f2c8-128">Jeśli projekty korzystają z innych pakietów Microsoft. Quantum (np. Microsoft. Quantum. Numerics), uruchom polecenie również dla nich.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-128">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="1f2c8-129">Zamknij wiersz polecenia i wybierz opcję **kompiluj** -> **Kompiluj rozwiązanie** ( *nie* wybieraj opcji Skompiluj ponownie rozwiązanie, ponieważ ponowne kompilowanie zakończy się niepowodzeniem)</span><span class="sxs-lookup"><span data-stu-id="1f2c8-129">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

<span data-ttu-id="1f2c8-130">Teraz możesz przejść do [aktualizacji rozszerzenia programu Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-130">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="1f2c8-131">Aktualizuj projekty Q # w Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1f2c8-131">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="1f2c8-132">W Visual Studio Code Otwórz folder zawierający projekt do zaktualizowania</span><span class="sxs-lookup"><span data-stu-id="1f2c8-132">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="1f2c8-133">Wybierz pozycję **terminal** -> **nowym terminalu**</span><span class="sxs-lookup"><span data-stu-id="1f2c8-133">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="1f2c8-134">Postępuj zgodnie z instrukcjami dotyczącymi aktualizowania przy użyciu wiersza polecenia (bezpośrednio poniżej)</span><span class="sxs-lookup"><span data-stu-id="1f2c8-134">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="1f2c8-135">Aktualizowanie projektów Q # przy użyciu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="1f2c8-135">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="1f2c8-136">Przejdź do folderu zawierającego plik projektu</span><span class="sxs-lookup"><span data-stu-id="1f2c8-136">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="1f2c8-137">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-137">Run the following command:</span></span>
    ```bash
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="1f2c8-138">W każdym z plików. csproj zaktualizuj platformę docelową do `netcoreapp3.0` (lub `netstandard2.1`, jeśli jest to projekt biblioteki).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-138">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="1f2c8-139">Oznacza to, że edycja wierszy formularza:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-139">That is, edit lines of the form:</span></span>
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    <span data-ttu-id="1f2c8-140">Więcej szczegółowych informacji na temat określania platform docelowych można znaleźć [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-140">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="1f2c8-141">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-141">Run the following command:</span></span>
    ```bash
    dotnet add package Microsoft.Quantum.Development.Kit
    ```
    <span data-ttu-id="1f2c8-142">Jeśli projekt używa innych pakietów Microsoft. Quantum (np. Microsoft. Quantum. Numerics), uruchom polecenie również dla nich.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-142">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="1f2c8-143">Zapisz i Zamknij wszystkie pliki.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-143">Save and close all files.</span></span>
6. <span data-ttu-id="1f2c8-144">Powtórz 1-4 dla każdej zależności projektu, a następnie przejdź z powrotem do folderu zawierającego główny projekt i uruchom:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-144">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
    ```bash
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="1f2c8-145">Gdy projekty Q # zostały zaktualizowane, postępuj zgodnie z poniższymi instrukcjami, aby zaktualizować QDK.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-145">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="1f2c8-146">Aktualizowanie QDK</span><span class="sxs-lookup"><span data-stu-id="1f2c8-146">Updating the QDK</span></span>

<span data-ttu-id="1f2c8-147">Proces aktualizowania QDK różni się w zależności od języka i środowiska deweloperskiego.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-147">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="1f2c8-148">Wybierz środowisko deweloperskie poniżej.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-148">Select your development environment below.</span></span>

* [<span data-ttu-id="1f2c8-149">Python: aktualizowanie rozszerzenia IQ #</span><span class="sxs-lookup"><span data-stu-id="1f2c8-149">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="1f2c8-150">Notesy Jupyter: aktualizowanie rozszerzenia IQ #</span><span class="sxs-lookup"><span data-stu-id="1f2c8-150">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="1f2c8-151">Visual Studio: aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="1f2c8-151">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="1f2c8-152">VS Code: aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="1f2c8-152">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="1f2c8-153">Wiersz polecenia i C#: aktualizowanie szablonów projektu</span><span class="sxs-lookup"><span data-stu-id="1f2c8-153">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="1f2c8-154">Aktualizacja IQ # dla języka Python</span><span class="sxs-lookup"><span data-stu-id="1f2c8-154">Update IQ# for Python</span></span>

1. <span data-ttu-id="1f2c8-155">Aktualizowanie jądra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="1f2c8-155">Update the `iqsharp` kernel</span></span> 

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="1f2c8-156">Weryfikowanie wersji `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="1f2c8-156">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="1f2c8-157">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-157">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    <span data-ttu-id="1f2c8-158">Nie martw się, jeśli Twoja wersja `iqsharp` jest wyższa, powinna być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-158">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="1f2c8-159">Aktualizowanie pakietu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="1f2c8-159">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="1f2c8-160">Weryfikowanie wersji `qsharp`</span><span class="sxs-lookup"><span data-stu-id="1f2c8-160">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="1f2c8-161">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-161">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
5. <span data-ttu-id="1f2c8-162">Uruchom następujące polecenie z lokalizacji plików `.qs`</span><span class="sxs-lookup"><span data-stu-id="1f2c8-162">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="1f2c8-163">Teraz można używać zaktualizowanej wersji QDK do uruchamiania istniejących programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-163">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="1f2c8-164">Aktualizacja IQ # dla notesów Jupyter</span><span class="sxs-lookup"><span data-stu-id="1f2c8-164">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="1f2c8-165">Aktualizowanie jądra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="1f2c8-165">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="1f2c8-166">Weryfikowanie wersji `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="1f2c8-166">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="1f2c8-167">Dane wyjściowe powinny wyglądać podobnie do następujących:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-167">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    <span data-ttu-id="1f2c8-168">Nie martw się, jeśli Twoja wersja `iqsharp` jest wyższa, powinna być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-168">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="1f2c8-169">Uruchom następujące polecenie w komórce w Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-169">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

4. <span data-ttu-id="1f2c8-170">Teraz możesz otworzyć istniejący Notes programu Jupyter i uruchomić go ze zaktualizowanym QDK.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-170">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="1f2c8-171">Zaktualizuj rozszerzenie Visual Studio QDK</span><span class="sxs-lookup"><span data-stu-id="1f2c8-171">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="1f2c8-172">Aktualizowanie rozszerzenia Q # programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1f2c8-172">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="1f2c8-173">Program Visual Studio poprosi o zaakceptowanie aktualizacji [rozszerzenia programu Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="1f2c8-173">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="1f2c8-174">Zaakceptuj aktualizację</span><span class="sxs-lookup"><span data-stu-id="1f2c8-174">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f2c8-175">Szablony projektu są aktualizowane przy użyciu rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-175">The project templates are updated with the extension.</span></span> <span data-ttu-id="1f2c8-176">Zaktualizowane szablony mają zastosowanie tylko do nowo utworzonych projektów.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-176">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="1f2c8-177">Kod dla istniejących projektów nie jest aktualizowany, gdy rozszerzenie zostanie zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-177">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="1f2c8-178">Aktualizacja rozszerzenia QDK VS Code</span><span class="sxs-lookup"><span data-stu-id="1f2c8-178">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="1f2c8-179">Aktualizowanie rozszerzenia Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="1f2c8-179">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="1f2c8-180">Uruchom ponownie VS Code</span><span class="sxs-lookup"><span data-stu-id="1f2c8-180">Restart VS Code</span></span>
    - <span data-ttu-id="1f2c8-181">Przejdź do karty **rozszerzenia**</span><span class="sxs-lookup"><span data-stu-id="1f2c8-181">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="1f2c8-182">Wybierz **Microsoft Quantum Development Kit rozszerzenia Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="1f2c8-182">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="1f2c8-183">Załaduj ponownie rozszerzenie</span><span class="sxs-lookup"><span data-stu-id="1f2c8-183">Reload the extension</span></span>

2. <span data-ttu-id="1f2c8-184">Aktualizowanie szablonów projektów Quantum:</span><span class="sxs-lookup"><span data-stu-id="1f2c8-184">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="1f2c8-185">Przejdź do pozycji **Widok** -> **Paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="1f2c8-185">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="1f2c8-186">Wybierz pozycję **Q #: Instalowanie szablonów projektu**</span><span class="sxs-lookup"><span data-stu-id="1f2c8-186">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="1f2c8-187">Po kilku sekundach powinien zostać wyświetlony podręczny komunikat potwierdzający pomyślne zainstalowanie szablonów projektu.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-187">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="1f2c8-188">C#przy użyciu narzędzia wiersza polecenia `dotnet`</span><span class="sxs-lookup"><span data-stu-id="1f2c8-188">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="1f2c8-189">Aktualizowanie szablonów projektów Quantum dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="1f2c8-189">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="1f2c8-190">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="1f2c8-190">What's next?</span></span>

<span data-ttu-id="1f2c8-191">Teraz, po zaktualizowaniu zestawu Quantum Development Kit w preferowanym środowisku, można nadal opracowywać i uruchamiać programy Quantum.</span><span class="sxs-lookup"><span data-stu-id="1f2c8-191">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="1f2c8-192">Jeśli nie zapisano jeszcze programu, możesz rozpocząć pracę z [pierwszym programem Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="1f2c8-192">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>

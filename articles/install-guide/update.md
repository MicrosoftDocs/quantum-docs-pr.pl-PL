---
title: Dowiedz się, jak aktualizować Microsoft Quantum Development Kit (QDK)
description: 'Opisuje, w jaki sposób aktualizować projekty Q # i Microsoft Quantum Development Kit do bieżącej wersji.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 264b5640216b2c0a468b625cdef4b9e0123d8b39
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904761"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="3733a-103">Aktualizowanie Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="3733a-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="3733a-104">Dowiedz się, jak zaktualizować Microsoft Quantum Development Kit (QDK) do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="3733a-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="3733a-105">W tym artykule przyjęto założenie, że zainstalowano już QDK.</span><span class="sxs-lookup"><span data-stu-id="3733a-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="3733a-106">Jeśli instalujesz po raz pierwszy, zapoznaj się z [Podręcznikiem instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="3733a-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="3733a-107">Zalecamy zachowywanie aktualności przy użyciu najnowszej wersji QDK.</span><span class="sxs-lookup"><span data-stu-id="3733a-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="3733a-108">Postępuj zgodnie z tym przewodnikiem aktualizacji, aby przeprowadzić uaktualnienie do najnowszej wersji programu QDK.</span><span class="sxs-lookup"><span data-stu-id="3733a-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="3733a-109">Proces składa się z dwóch części:</span><span class="sxs-lookup"><span data-stu-id="3733a-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="3733a-110">Aktualizowanie istniejących plików i projektów Q # w celu wyrównania kodu przy użyciu dowolnej zaktualizowanej składni</span><span class="sxs-lookup"><span data-stu-id="3733a-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="3733a-111">Aktualizowanie samej QDK dla wybranego środowiska programistycznego</span><span class="sxs-lookup"><span data-stu-id="3733a-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="3733a-112">Aktualizowanie projektów Q #</span><span class="sxs-lookup"><span data-stu-id="3733a-112">Updating Q# Projects</span></span> 

<span data-ttu-id="3733a-113">Bez względu na to, czy C# używasz programu lub języka Python do hostowania operacji q #, postępuj zgodnie z tymi instrukcjami, aby zaktualizować projekty q #.</span><span class="sxs-lookup"><span data-stu-id="3733a-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="3733a-114">Najpierw sprawdź, czy masz najnowszą wersję [zestaw .NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="3733a-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="3733a-115">Uruchom następujące polecenie w wierszu polecenia:</span><span class="sxs-lookup"><span data-stu-id="3733a-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="3733a-116">Sprawdź, czy dane wyjściowe są `3.1.100` lub nowsze.</span><span class="sxs-lookup"><span data-stu-id="3733a-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="3733a-117">Jeśli nie, zainstaluj [najnowszą wersję](https://dotnet.microsoft.com/download) i sprawdź ponownie.</span><span class="sxs-lookup"><span data-stu-id="3733a-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="3733a-118">Następnie postępuj zgodnie z poniższymi instrukcjami, w zależności od konfiguracji (Visual Studio, Visual Studio Code lub bezpośrednio w wierszu polecenia).</span><span class="sxs-lookup"><span data-stu-id="3733a-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="3733a-119">Aktualizuj projekty Q # w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3733a-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="3733a-120">Aktualizacja do najnowszej wersji programu Visual Studio 2019, zobacz [tutaj](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) , aby uzyskać instrukcje</span><span class="sxs-lookup"><span data-stu-id="3733a-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="3733a-121">Otwórz rozwiązanie w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3733a-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="3733a-122">Z menu wybierz opcję **kompiluj** -> **Wyczyść rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="3733a-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="3733a-123">W każdym z plików. csproj zaktualizuj platformę docelową do `netcoreapp3.0` (lub `netstandard2.1`, jeśli jest to projekt biblioteki).</span><span class="sxs-lookup"><span data-stu-id="3733a-123">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="3733a-124">Oznacza to, że edycja wierszy formularza:</span><span class="sxs-lookup"><span data-stu-id="3733a-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="3733a-125">Więcej szczegółowych informacji na temat określania platform docelowych można znaleźć [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="3733a-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="3733a-126">Zapisz i Zamknij wszystkie pliki w rozwiązaniu</span><span class="sxs-lookup"><span data-stu-id="3733a-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="3733a-127">Wybierz **narzędzia** ->  -> **wiersza polecenia** **wiersz polecenia dla deweloperów**</span><span class="sxs-lookup"><span data-stu-id="3733a-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="3733a-128">Dla każdego projektu w rozwiązaniu Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="3733a-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="3733a-129">Jeśli projekty korzystają z innych pakietów Microsoft. Quantum (np. Microsoft. Quantum. Numerics), uruchom polecenie również dla nich.</span><span class="sxs-lookup"><span data-stu-id="3733a-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="3733a-130">Zamknij wiersz polecenia i wybierz opcję **kompiluj** -> **Kompiluj rozwiązanie** ( *nie* wybieraj opcji Skompiluj ponownie rozwiązanie)</span><span class="sxs-lookup"><span data-stu-id="3733a-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="3733a-131">Teraz możesz przejść do [aktualizacji rozszerzenia programu Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="3733a-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="3733a-132">Aktualizuj projekty Q # w Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3733a-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="3733a-133">W Visual Studio Code Otwórz folder zawierający projekt do zaktualizowania</span><span class="sxs-lookup"><span data-stu-id="3733a-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="3733a-134">Wybierz pozycję **terminal** -> **nowym terminalu**</span><span class="sxs-lookup"><span data-stu-id="3733a-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="3733a-135">Postępuj zgodnie z instrukcjami dotyczącymi aktualizowania przy użyciu wiersza polecenia (bezpośrednio poniżej)</span><span class="sxs-lookup"><span data-stu-id="3733a-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="3733a-136">Aktualizowanie projektów Q # przy użyciu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="3733a-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="3733a-137">Przejdź do folderu zawierającego plik projektu</span><span class="sxs-lookup"><span data-stu-id="3733a-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="3733a-138">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="3733a-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="3733a-139">W każdym z plików. csproj zaktualizuj platformę docelową do `netcoreapp3.0` (lub `netstandard2.1`, jeśli jest to projekt biblioteki).</span><span class="sxs-lookup"><span data-stu-id="3733a-139">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="3733a-140">Oznacza to, że edycja wierszy formularza:</span><span class="sxs-lookup"><span data-stu-id="3733a-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="3733a-141">Więcej szczegółowych informacji na temat określania platform docelowych można znaleźć [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="3733a-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="3733a-142">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="3733a-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="3733a-143">Jeśli projekt używa innych pakietów Microsoft. Quantum (np. Microsoft. Quantum. Numerics), uruchom polecenie również dla nich.</span><span class="sxs-lookup"><span data-stu-id="3733a-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="3733a-144">Zapisz i Zamknij wszystkie pliki.</span><span class="sxs-lookup"><span data-stu-id="3733a-144">Save and close all files.</span></span>
6. <span data-ttu-id="3733a-145">Powtórz 1-4 dla każdej zależności projektu, a następnie przejdź z powrotem do folderu zawierającego główny projekt i uruchom:</span><span class="sxs-lookup"><span data-stu-id="3733a-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="3733a-146">Gdy projekty Q # zostały zaktualizowane, postępuj zgodnie z poniższymi instrukcjami, aby zaktualizować QDK.</span><span class="sxs-lookup"><span data-stu-id="3733a-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="3733a-147">Aktualizowanie QDK</span><span class="sxs-lookup"><span data-stu-id="3733a-147">Updating the QDK</span></span>

<span data-ttu-id="3733a-148">Proces aktualizowania QDK różni się w zależności od języka i środowiska deweloperskiego.</span><span class="sxs-lookup"><span data-stu-id="3733a-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="3733a-149">Wybierz środowisko deweloperskie poniżej.</span><span class="sxs-lookup"><span data-stu-id="3733a-149">Select your development environment below.</span></span>

* [<span data-ttu-id="3733a-150">Python: aktualizowanie rozszerzenia IQ #</span><span class="sxs-lookup"><span data-stu-id="3733a-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="3733a-151">Notesy Jupyter: aktualizowanie rozszerzenia IQ #</span><span class="sxs-lookup"><span data-stu-id="3733a-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="3733a-152">Visual Studio: aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="3733a-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="3733a-153">VS Code: aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="3733a-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="3733a-154">Wiersz polecenia i C#: aktualizowanie szablonów projektu</span><span class="sxs-lookup"><span data-stu-id="3733a-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="3733a-155">Aktualizacja IQ # dla języka Python</span><span class="sxs-lookup"><span data-stu-id="3733a-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="3733a-156">Aktualizowanie jądra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="3733a-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="3733a-157">Weryfikowanie wersji `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="3733a-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="3733a-158">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="3733a-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="3733a-159">Nie martw się, jeśli Twoja wersja `iqsharp` jest wyższa, powinna być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="3733a-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="3733a-160">Aktualizowanie pakietu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="3733a-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="3733a-161">Weryfikowanie wersji `qsharp`</span><span class="sxs-lookup"><span data-stu-id="3733a-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="3733a-162">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="3733a-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="3733a-163">Uruchom następujące polecenie z lokalizacji plików `.qs`</span><span class="sxs-lookup"><span data-stu-id="3733a-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="3733a-164">Teraz można używać zaktualizowanej wersji QDK do uruchamiania istniejących programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="3733a-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="3733a-165">Aktualizacja IQ # dla notesów Jupyter</span><span class="sxs-lookup"><span data-stu-id="3733a-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="3733a-166">Aktualizowanie jądra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="3733a-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="3733a-167">Weryfikowanie wersji `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="3733a-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="3733a-168">Dane wyjściowe powinny wyglądać podobnie do następujących:</span><span class="sxs-lookup"><span data-stu-id="3733a-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="3733a-169">Nie martw się, jeśli Twoja wersja `iqsharp` jest wyższa, powinna być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="3733a-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="3733a-170">Uruchom następujące polecenie w komórce w Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="3733a-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="3733a-171">Teraz możesz otworzyć istniejący Notes programu Jupyter i uruchomić go ze zaktualizowanym QDK.</span><span class="sxs-lookup"><span data-stu-id="3733a-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="3733a-172">Zaktualizuj rozszerzenie Visual Studio QDK</span><span class="sxs-lookup"><span data-stu-id="3733a-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="3733a-173">Aktualizowanie rozszerzenia Q # programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3733a-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="3733a-174">Program Visual Studio poprosi o zaakceptowanie aktualizacji [rozszerzenia programu Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="3733a-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="3733a-175">Zaakceptuj aktualizację</span><span class="sxs-lookup"><span data-stu-id="3733a-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="3733a-176">Szablony projektu są aktualizowane przy użyciu rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="3733a-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="3733a-177">Zaktualizowane szablony mają zastosowanie tylko do nowo utworzonych projektów.</span><span class="sxs-lookup"><span data-stu-id="3733a-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="3733a-178">Kod dla istniejących projektów nie jest aktualizowany, gdy rozszerzenie zostanie zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="3733a-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="3733a-179">Aktualizacja rozszerzenia QDK VS Code</span><span class="sxs-lookup"><span data-stu-id="3733a-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="3733a-180">Aktualizowanie rozszerzenia Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="3733a-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="3733a-181">Uruchom ponownie VS Code</span><span class="sxs-lookup"><span data-stu-id="3733a-181">Restart VS Code</span></span>
    - <span data-ttu-id="3733a-182">Przejdź do karty **rozszerzenia**</span><span class="sxs-lookup"><span data-stu-id="3733a-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="3733a-183">Wybierz **Microsoft Quantum Development Kit rozszerzenia Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="3733a-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="3733a-184">Załaduj ponownie rozszerzenie</span><span class="sxs-lookup"><span data-stu-id="3733a-184">Reload the extension</span></span>

2. <span data-ttu-id="3733a-185">Aktualizowanie szablonów projektów Quantum:</span><span class="sxs-lookup"><span data-stu-id="3733a-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="3733a-186">Przejdź do pozycji **Widok** -> **Paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="3733a-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="3733a-187">Wybierz pozycję **Q #: Instalowanie szablonów projektu**</span><span class="sxs-lookup"><span data-stu-id="3733a-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="3733a-188">Po kilku sekundach powinien zostać wyświetlony podręczny komunikat potwierdzający pomyślne zainstalowanie szablonów projektu.</span><span class="sxs-lookup"><span data-stu-id="3733a-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="3733a-189">C#przy użyciu narzędzia wiersza polecenia `dotnet`</span><span class="sxs-lookup"><span data-stu-id="3733a-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="3733a-190">Aktualizowanie szablonów projektów Quantum dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="3733a-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="3733a-191">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="3733a-191">What's next?</span></span>

<span data-ttu-id="3733a-192">Teraz, po zaktualizowaniu zestawu Quantum Development Kit w preferowanym środowisku, można nadal opracowywać i uruchamiać programy Quantum.</span><span class="sxs-lookup"><span data-stu-id="3733a-192">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="3733a-193">Jeśli nie zapisano jeszcze programu, możesz rozpocząć pracę z [pierwszym programem Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="3733a-193">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>

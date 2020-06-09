---
title: Aktualizowanie zestawu Quantum Development Kit (QDK)
description: 'Opisuje, w jaki sposób aktualizować projekty Q # i Microsoft Quantum Development Kit do bieżącej wersji.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 89db1a671767b0cc083a251918bbeeed2b39b883
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578185"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="d2e8f-103">Aktualizowanie Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="d2e8f-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="d2e8f-104">Dowiedz się, jak zaktualizować Microsoft Quantum Development Kit (QDK) do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="d2e8f-105">W tym artykule przyjęto założenie, że zainstalowano już QDK.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="d2e8f-106">Jeśli instalujesz po raz pierwszy, zapoznaj się z [Podręcznikiem instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="d2e8f-107">Zalecamy zachowywanie aktualności przy użyciu najnowszej wersji QDK.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="d2e8f-108">Postępuj zgodnie z tym przewodnikiem aktualizacji, aby przeprowadzić uaktualnienie do najnowszej wersji programu QDK.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="d2e8f-109">Proces składa się z dwóch części:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="d2e8f-110">Aktualizowanie istniejących plików i projektów Q # w celu wyrównania kodu przy użyciu dowolnej zaktualizowanej składni.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="d2e8f-111">Aktualizowanie samego QDK dla wybranego środowiska deweloperskiego.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="d2e8f-112">Aktualizowanie projektów Q #</span><span class="sxs-lookup"><span data-stu-id="d2e8f-112">Updating Q# Projects</span></span> 

<span data-ttu-id="d2e8f-113">Bez względu na to, czy używasz języka C# lub Python do hostowania operacji Q #, postępuj zgodnie z tymi instrukcjami, aby zaktualizować projekty Q #.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="d2e8f-114">Najpierw sprawdź, czy masz najnowszą wersję [zestaw .NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="d2e8f-115">Uruchom następujące polecenie w wierszu polecenia:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="d2e8f-116">Sprawdź, czy dane wyjściowe są `3.1.100` lub nowsze.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="d2e8f-117">Jeśli nie, zainstaluj [najnowszą wersję](https://dotnet.microsoft.com/download) i sprawdź ponownie.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="d2e8f-118">Następnie postępuj zgodnie z poniższymi instrukcjami, w zależności od konfiguracji (Visual Studio, Visual Studio Code lub bezpośrednio w wierszu polecenia).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="d2e8f-119">Aktualizuj projekty Q # w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d2e8f-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="d2e8f-120">Zaktualizuj do najnowszej wersji programu Visual Studio 2019, zobacz [tutaj](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) , aby uzyskać instrukcje.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="d2e8f-121">Otwórz rozwiązanie w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="d2e8f-122">Z menu wybierz opcję **Kompiluj**  ->  **czyste rozwiązanie**.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="d2e8f-123">W każdym z plików. csproj zaktualizuj platformę docelową do `netcoreapp3.1` (lub `netstandard2.1` Jeśli jest to projekt biblioteki).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="d2e8f-124">Oznacza to, że edycja wierszy formularza:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="d2e8f-125">Więcej szczegółowych informacji na temat określania platform docelowych można znaleźć [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="d2e8f-126">W każdym z plików. csproj Ustaw zestaw SDK na `Microsoft.Quantum.Sdk` , jak wskazano w wierszu poniżej.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="d2e8f-127">Należy zauważyć, że numer wersji powinien być najnowszy dostępny i można go określić, przeglądając [Informacje o wersji](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="d2e8f-128">Zapisz i Zamknij wszystkie pliki w rozwiązaniu.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="d2e8f-129">Wybierz pozycję **Narzędzia**  ->  **wiersz polecenia**  ->  **wiersz polecenia dla deweloperów**.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="d2e8f-130">Alternatywnie można użyć konsoli zarządzania pakietami w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="d2e8f-131">Dla każdego projektu w rozwiązaniu Uruchom następujące polecenie, aby **usunąć** ten pakiet:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="d2e8f-132">Jeśli projekty korzystają z innych pakietów Microsoft. Quantum lub Microsoft. Azure. Quantum (np. Microsoft. Quantum. Numerics), uruchom polecenie **Add** , aby zaktualizować używaną wersję.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="d2e8f-133">Zamknij wiersz polecenia i wybierz pozycję **Kompiluj**  ->  **kompilację rozwiązania** ( *nie* wybieraj opcji Skompiluj ponownie rozwiązanie).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="d2e8f-134">Teraz możesz przejść do [aktualizacji rozszerzenia programu Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="d2e8f-135">Aktualizuj projekty Q # w Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d2e8f-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="d2e8f-136">W Visual Studio Code Otwórz folder zawierający projekt do zaktualizowania.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="d2e8f-137">Wybierz pozycję **Terminal**  ->  **Nowy terminal**.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="d2e8f-138">Postępuj zgodnie z instrukcjami dotyczącymi aktualizowania przy użyciu wiersza polecenia (bezpośrednio poniżej).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="d2e8f-139">Aktualizowanie projektów Q # przy użyciu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="d2e8f-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="d2e8f-140">Przejdź do folderu zawierającego główny plik projektu.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="d2e8f-141">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="d2e8f-142">Ustal bieżącą wersję QDK.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="d2e8f-143">Aby go znaleźć, możesz przejrzeć informacje o [wersji](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="d2e8f-144">Wersja będzie wyglądać w formacie podobnym do `0.11.2006.207` .</span><span class="sxs-lookup"><span data-stu-id="d2e8f-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="d2e8f-145">W każdym z `.csproj` plików wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="d2e8f-146">Zaktualizuj platformę docelową do `netcoreapp3.1` (lub `netstandard2.1` Jeśli jest to projekt biblioteki).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="d2e8f-147">Oznacza to, że edycja wierszy formularza:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="d2e8f-148">Więcej szczegółowych informacji na temat określania platform docelowych można znaleźć [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="d2e8f-149">Zastąp odwołanie do zestawu SDK w definicji projektu.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="d2e8f-150">Upewnij się, że numer wersji odpowiada wartości określonej w **kroku 3**.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="d2e8f-151">Usuń odwołanie do pakietu `Microsoft.Quantum.Development.Kit` , jeśli jest obecny, które zostanie określone w następującym wpisie:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="d2e8f-152">Zaktualizuj wersję wszystkich pakietów Quantum firmy Microsoft do ostatnio wydanej wersji QDK (określonej w **kroku 3**).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="d2e8f-153">Te pakiety są nazwane następującymi wzorcami:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="d2e8f-154">Odwołania do pakietów mają następujący format:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="d2e8f-155">Zapisz zmodyfikowany plik.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-155">Save the updated file.</span></span>

    - <span data-ttu-id="d2e8f-156">Przywróć zależności projektu, wykonując następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="d2e8f-157">Przejdź z powrotem do folderu zawierającego główny projekt i uruchom:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="d2e8f-158">Gdy projekty Q # zostały zaktualizowane, postępuj zgodnie z poniższymi instrukcjami, aby zaktualizować QDK.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="d2e8f-159">Aktualizowanie QDK</span><span class="sxs-lookup"><span data-stu-id="d2e8f-159">Updating the QDK</span></span>

<span data-ttu-id="d2e8f-160">Proces aktualizowania QDK różni się w zależności od języka i środowiska deweloperskiego.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="d2e8f-161">Wybierz środowisko deweloperskie poniżej.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-161">Select your development environment below.</span></span>

* [<span data-ttu-id="d2e8f-162">Python: aktualizowanie rozszerzenia IQ #</span><span class="sxs-lookup"><span data-stu-id="d2e8f-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="d2e8f-163">Notesy Jupyter: aktualizowanie rozszerzenia IQ #</span><span class="sxs-lookup"><span data-stu-id="d2e8f-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="d2e8f-164">Visual Studio: aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="d2e8f-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="d2e8f-165">VS Code: aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="d2e8f-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="d2e8f-166">Wiersz polecenia i C#: aktualizowanie szablonów projektu</span><span class="sxs-lookup"><span data-stu-id="d2e8f-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="d2e8f-167">Aktualizacja IQ # dla języka Python</span><span class="sxs-lookup"><span data-stu-id="d2e8f-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="d2e8f-168">Aktualizowanie `iqsharp` jądra</span><span class="sxs-lookup"><span data-stu-id="d2e8f-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="d2e8f-169">Sprawdź `iqsharp` wersję</span><span class="sxs-lookup"><span data-stu-id="d2e8f-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="d2e8f-170">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-170">You should see the following output:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="d2e8f-171">Nie martw się, jeśli Twoja `iqsharp` wersja jest nowsza, powinna być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="d2e8f-172">Aktualizowanie `qsharp` pakietu</span><span class="sxs-lookup"><span data-stu-id="d2e8f-172">Update the `qsharp` package</span></span>

    ```
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="d2e8f-173">Sprawdź `qsharp` wersję</span><span class="sxs-lookup"><span data-stu-id="d2e8f-173">Verify the `qsharp` version</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="d2e8f-174">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-174">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="d2e8f-175">Uruchom następujące polecenie z lokalizacji `.qs` plików</span><span class="sxs-lookup"><span data-stu-id="d2e8f-175">Run the following command from the location of your `.qs` files</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="d2e8f-176">Teraz można używać zaktualizowanej wersji QDK do uruchamiania istniejących programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="d2e8f-177">Aktualizacja IQ # dla notesów Jupyter</span><span class="sxs-lookup"><span data-stu-id="d2e8f-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="d2e8f-178">Aktualizowanie `iqsharp` jądra</span><span class="sxs-lookup"><span data-stu-id="d2e8f-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="d2e8f-179">Sprawdź `iqsharp` wersję</span><span class="sxs-lookup"><span data-stu-id="d2e8f-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="d2e8f-180">Dane wyjściowe powinny wyglądać podobnie do następujących:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-180">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="d2e8f-181">Nie martw się, jeśli Twoja `iqsharp` wersja jest nowsza, powinna być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="d2e8f-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="d2e8f-182">Uruchom następujące polecenie w komórce w Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="d2e8f-183">Teraz możesz otworzyć istniejący Notes programu Jupyter i uruchomić go ze zaktualizowanym QDK.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="d2e8f-184">Zaktualizuj rozszerzenie Visual Studio QDK</span><span class="sxs-lookup"><span data-stu-id="d2e8f-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="d2e8f-185">Aktualizowanie rozszerzenia Q # programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d2e8f-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="d2e8f-186">Program Visual Studio poprosi o zaakceptowanie aktualizacji [rozszerzenia programu Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="d2e8f-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="d2e8f-187">Zaakceptuj aktualizację</span><span class="sxs-lookup"><span data-stu-id="d2e8f-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2e8f-188">Szablony projektu są aktualizowane przy użyciu rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="d2e8f-189">Zaktualizowane szablony mają zastosowanie tylko do nowo utworzonych projektów.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="d2e8f-190">Kod dla istniejących projektów nie jest aktualizowany, gdy rozszerzenie zostanie zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="d2e8f-191">Aktualizacja rozszerzenia QDK VS Code</span><span class="sxs-lookup"><span data-stu-id="d2e8f-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="d2e8f-192">Aktualizowanie rozszerzenia Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="d2e8f-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="d2e8f-193">Uruchom ponownie VS Code</span><span class="sxs-lookup"><span data-stu-id="d2e8f-193">Restart VS Code</span></span>
    - <span data-ttu-id="d2e8f-194">Przejdź do karty **rozszerzenia**</span><span class="sxs-lookup"><span data-stu-id="d2e8f-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="d2e8f-195">Wybierz **Microsoft Quantum Development Kit rozszerzenia Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="d2e8f-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="d2e8f-196">Załaduj ponownie rozszerzenie</span><span class="sxs-lookup"><span data-stu-id="d2e8f-196">Reload the extension</span></span>

2. <span data-ttu-id="d2e8f-197">Aktualizowanie szablonów projektów Quantum:</span><span class="sxs-lookup"><span data-stu-id="d2e8f-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="d2e8f-198">Przejdź do **widoku**—  ->  **paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="d2e8f-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="d2e8f-199">Wybierz pozycję **Q #: Instalowanie szablonów projektu**</span><span class="sxs-lookup"><span data-stu-id="d2e8f-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="d2e8f-200">Po kilku sekundach powinien zostać wyświetlony podręczny komunikat potwierdzający pomyślne zainstalowanie szablonów projektu.</span><span class="sxs-lookup"><span data-stu-id="d2e8f-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="d2e8f-201">C#, przy użyciu `dotnet` narzędzia wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="d2e8f-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="d2e8f-202">Aktualizowanie szablonów projektów Quantum dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="d2e8f-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

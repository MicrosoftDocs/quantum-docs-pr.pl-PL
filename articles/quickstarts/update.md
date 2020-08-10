---
title: Aktualizowanie zestawu Quantum Development Kit (QDK)
description: Tu opisano, jak zaktualizować projekty języka Q# i zestaw Microsoft Quantum Development Kit do bieżącej wersji.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: dd7360961aa728a6aa63b8d8c4e4840f5bf2afe8
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866761"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="b0091-103">Aktualizowanie zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="b0091-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="b0091-104">Dowiedz się, jak zaktualizować zestaw Microsoft Quantum Development Kit (QDK) do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="b0091-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="b0091-105">W tym artykule założono, że masz już zainstalowany zestaw QDK.</span><span class="sxs-lookup"><span data-stu-id="b0091-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="b0091-106">Jeśli instalujesz go po raz pierwszy, skorzystaj z [przewodnika instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="b0091-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="b0091-107">Zalecamy regularne aktualizowanie zestawu QDK do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="b0091-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="b0091-108">Wykonaj instrukcje z tego przewodnika aktualizacji, aby przejść na najnowszą wersję zestawu QDK.</span><span class="sxs-lookup"><span data-stu-id="b0091-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="b0091-109">Ten proces składa się z dwóch części:</span><span class="sxs-lookup"><span data-stu-id="b0091-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="b0091-110">Aktualizowanie istniejących plików i projektów języka Q# w celu dostosowania kodu do zaktualizowanej składni.</span><span class="sxs-lookup"><span data-stu-id="b0091-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="b0091-111">Aktualizowanie samego zestawu QDK dla wybranego środowiska deweloperskiego.</span><span class="sxs-lookup"><span data-stu-id="b0091-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-no-locq-projects"></a><span data-ttu-id="b0091-112">Aktualizowanie projektów języka Q#</span><span class="sxs-lookup"><span data-stu-id="b0091-112">Updating Q# Projects</span></span> 

<span data-ttu-id="b0091-113">Niezależnie od tego, czy hostujesz operacje języka Q# przy użyciu środowiska języka C#, czy Python, postępuj zgodnie z tymi instrukcjami, aby zaktualizować projekty języka Q#.</span><span class="sxs-lookup"><span data-stu-id="b0091-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="b0091-114">Najpierw sprawdź, czy masz najnowszą wersję [zestawu .NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="b0091-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="b0091-115">W wierszu polecenia uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="b0091-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="b0091-116">Sprawdź, czy dane wyjściowe zawierają informację o wersji `3.1.100` lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="b0091-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="b0091-117">Jeśli nie, zainstaluj [najnowszą wersję](https://dotnet.microsoft.com/download) i sprawdź ponownie.</span><span class="sxs-lookup"><span data-stu-id="b0091-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="b0091-118">Następnie postępuj zgodnie z poniższymi instrukcjami odpowiednio do używanej konfiguracji (w programie Visual Studio, Visual Studio Code lub bezpośrednio w wierszu polecenia).</span><span class="sxs-lookup"><span data-stu-id="b0091-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-no-locq-projects-in-visual-studio"></a><span data-ttu-id="b0091-119">Aktualizowanie projektów języka Q# w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0091-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="b0091-120">Zaktualizuj program Visual Studio 2019 do najnowszej wersji — instrukcje znajdziesz [tutaj](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="b0091-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="b0091-121">Otwórz rozwiązanie w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0091-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="b0091-122">Z menu wybierz pozycję**Kompilacja** -> **Wyczyść rozwiązanie**.</span><span class="sxs-lookup"><span data-stu-id="b0091-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="b0091-123">W każdym z plików .csproj zaktualizuj platformę docelową do wersji `netcoreapp3.1` (lub `netstandard2.1`, jeśli jest to projekt biblioteki).</span><span class="sxs-lookup"><span data-stu-id="b0091-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="b0091-124">W tym celu edytuj wiersze w następującym formacie:</span><span class="sxs-lookup"><span data-stu-id="b0091-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="b0091-125">Więcej szczegółowych informacji na temat określania platform docelowych znajdziesz [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="b0091-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="b0091-126">W każdym z plików .csproj określ zestaw SDK `Microsoft.Quantum.Sdk`, jak pokazano poniżej.</span><span class="sxs-lookup"><span data-stu-id="b0091-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="b0091-127">Zwróć uwagę, że numer wersji powinien odpowiadać najnowszej dostępnej wersji — aby ją określić, sprawdź [informacje o wersji](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="b0091-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. <span data-ttu-id="b0091-128">Zapisz i zamknij wszystkie pliki w rozwiązaniu.</span><span class="sxs-lookup"><span data-stu-id="b0091-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="b0091-129">Wybierz pozycję **Narzędzia** -> **Wiersz polecenia** -> **Wiersz polecenia dla deweloperów**.</span><span class="sxs-lookup"><span data-stu-id="b0091-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="b0091-130">Alternatywnie można użyć konsoli zarządzania pakietami w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0091-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="b0091-131">Dla każdego projektu w rozwiązaniu uruchom następujące polecenie, aby **usunąć** ten pakiet:</span><span class="sxs-lookup"><span data-stu-id="b0091-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="b0091-132">Jeśli w projektach są używane jakiekolwiek inne pakiety Microsoft.Quantum lub Microsoft.Azure.Quantum (na przykład Microsoft.Quantum.Numerics), uruchom polecenie **add**, aby zaktualizować używaną wersję.</span><span class="sxs-lookup"><span data-stu-id="b0091-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="b0091-133">Zamknij wiersz polecenia i wybierz pozycję **Kompilacja** -> **Kompiluj rozwiązanie** (*nie* wybieraj polecenia Kompiluj ponownie rozwiązanie).</span><span class="sxs-lookup"><span data-stu-id="b0091-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="b0091-134">Możesz teraz przejść do sekcji [Aktualizowanie rozszerzenia QDK dla programu Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="b0091-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-no-locq-projects-in-visual-studio-code"></a><span data-ttu-id="b0091-135">Aktualizowanie projektów języka Q# w programie Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b0091-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="b0091-136">W programie Visual Studio Code otwórz folder zawierający projekt, który chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="b0091-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="b0091-137">Wybierz pozycję **Terminal** -> **New Terminal** (Nowy terminal).</span><span class="sxs-lookup"><span data-stu-id="b0091-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="b0091-138">Postępuj zgodnie z instrukcjami aktualizowania przy użyciu wiersza polecenia (tuż poniżej).</span><span class="sxs-lookup"><span data-stu-id="b0091-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-no-locq-projects-using-the-command-line"></a><span data-ttu-id="b0091-139">Aktualizowanie projektów języka Q# przy użyciu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="b0091-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="b0091-140">Przejdź do folderu zawierającego główny plik projektu.</span><span class="sxs-lookup"><span data-stu-id="b0091-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="b0091-141">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="b0091-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="b0091-142">Określ bieżącą wersję zestawu QDK.</span><span class="sxs-lookup"><span data-stu-id="b0091-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="b0091-143">Aby ją znaleźć, możesz sprawdzić [informacje o wersji](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="b0091-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="b0091-144">Wersja będzie miała format podobny do następującego: `0.12.20072031`.</span><span class="sxs-lookup"><span data-stu-id="b0091-144">The version will be in a format similar to `0.12.20072031`.</span></span>

4. <span data-ttu-id="b0091-145">W każdym z plików `.csproj` wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="b0091-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="b0091-146">Zaktualizuj platformę docelową do wersji `netcoreapp3.1` (lub `netstandard2.1`, jeśli jest to projekt biblioteki).</span><span class="sxs-lookup"><span data-stu-id="b0091-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="b0091-147">W tym celu edytuj wiersze w następującym formacie:</span><span class="sxs-lookup"><span data-stu-id="b0091-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="b0091-148">Więcej szczegółowych informacji na temat określania platform docelowych znajdziesz [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="b0091-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="b0091-149">Zmień odwołanie do zestawu SDK w definicji projektu.</span><span class="sxs-lookup"><span data-stu-id="b0091-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="b0091-150">Upewnij się, że numer wersji odpowiada wartości określonej w **kroku 3**.</span><span class="sxs-lookup"><span data-stu-id="b0091-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - <span data-ttu-id="b0091-151">Usuń odwołanie do pakietu `Microsoft.Quantum.Development.Kit`, jeśli jest określone w następującym wpisie:</span><span class="sxs-lookup"><span data-stu-id="b0091-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="b0091-152">Zaktualizuj wersje wszystkich pakietów Microsoft Quantum do najnowszej wersji zestawu QDK (określonej w **kroku 3**).</span><span class="sxs-lookup"><span data-stu-id="b0091-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="b0091-153">Nazwy pakietów odpowiadają następującym wzorcom:</span><span class="sxs-lookup"><span data-stu-id="b0091-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="b0091-154">Odwołania do pakietów mają następujący format:</span><span class="sxs-lookup"><span data-stu-id="b0091-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - <span data-ttu-id="b0091-155">Zapisz zaktualizowany plik.</span><span class="sxs-lookup"><span data-stu-id="b0091-155">Save the updated file.</span></span>

    - <span data-ttu-id="b0091-156">Przywróć zależności projektu, wykonując następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="b0091-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="b0091-157">Wróć do folderu zawierającego główny plik projektu i uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="b0091-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="b0091-158">Po zaktualizowaniu projektów języka Q# możesz zaktualizować sam zestaw QDK zgodnie z poniższymi instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="b0091-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="b0091-159">Aktualizowanie zestawu QDK</span><span class="sxs-lookup"><span data-stu-id="b0091-159">Updating the QDK</span></span>

<span data-ttu-id="b0091-160">Proces aktualizowania zestawu QDK zależy od używanego języka programowania i środowiska.</span><span class="sxs-lookup"><span data-stu-id="b0091-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="b0091-161">Wybierz używane środowisko deweloperskie poniżej.</span><span class="sxs-lookup"><span data-stu-id="b0091-161">Select your development environment below.</span></span>

* [<span data-ttu-id="b0091-162">Python: aktualizowanie pakietu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="b0091-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="b0091-163">Notesy Jupyter Notebook: aktualizowanie jądra IQ#</span><span class="sxs-lookup"><span data-stu-id="b0091-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="b0091-164">Visual Studio: aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="b0091-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="b0091-165">VS Code: aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="b0091-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="b0091-166">Wiersz polecenia i język C#: aktualizowanie szablonów projektów</span><span class="sxs-lookup"><span data-stu-id="b0091-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="b0091-167">Aktualizowanie pakietu `qsharp` języka Python</span><span class="sxs-lookup"><span data-stu-id="b0091-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="b0091-168">Procedura aktualizacji zależy od tego, czy program został pierwotnie zainstalowany przy użyciu środowiska conda, czy przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP.</span><span class="sxs-lookup"><span data-stu-id="b0091-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="b0091-169">Aktualizowanie przy użyciu środowiska conda (zalecane)</span><span class="sxs-lookup"><span data-stu-id="b0091-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="b0091-170">Aktywuj środowisko conda, w którym zainstalowano pakiet `qsharp`, a następnie uruchom to polecenie, aby go zaktualizować:</span><span class="sxs-lookup"><span data-stu-id="b0091-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="b0091-171">Uruchom następujące polecenie z poziomu lokalizacji plików `.qs`:</span><span class="sxs-lookup"><span data-stu-id="b0091-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="b0091-172">Aktualizowanie przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP (zaawansowane)</span><span class="sxs-lookup"><span data-stu-id="b0091-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="b0091-173">Zaktualizuj jądro `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="b0091-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="b0091-174">Zweryfikuj wersję jądra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="b0091-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="b0091-175">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b0091-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="b0091-176">Nie przejmuj się, jeśli Twoja wersja jądra `iqsharp` jest nowsza.</span><span class="sxs-lookup"><span data-stu-id="b0091-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="b0091-177">Powinna ona być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="b0091-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="b0091-178">Zaktualizuj pakiet `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="b0091-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="b0091-179">Zweryfikuj wersję pakietu `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="b0091-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="b0091-180">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b0091-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="b0091-181">Uruchom następujące polecenie z poziomu lokalizacji plików `.qs`:</span><span class="sxs-lookup"><span data-stu-id="b0091-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="b0091-182">Teraz możesz korzystać ze zaktualizowanego pakietu `qsharp` języka Python do uruchamiania istniejących programów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="b0091-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="b0091-183">Aktualizowanie jądra Jupyter IQ#</span><span class="sxs-lookup"><span data-stu-id="b0091-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="b0091-184">Procedura aktualizacji zależy od tego, czy program został pierwotnie zainstalowany przy użyciu środowiska conda, czy przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP.</span><span class="sxs-lookup"><span data-stu-id="b0091-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="b0091-185">Aktualizowanie przy użyciu środowiska conda (zalecane)</span><span class="sxs-lookup"><span data-stu-id="b0091-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="b0091-186">Aktywuj środowisko conda, w którym zainstalowano pakiet `qsharp`, a następnie uruchom to polecenie, aby je zaktualizować:</span><span class="sxs-lookup"><span data-stu-id="b0091-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="b0091-187">Uruchom następujące polecenie w komórce w każdym z istniejących notesów Jupyter Notebook języka Q#:</span><span class="sxs-lookup"><span data-stu-id="b0091-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="b0091-188">Aktualizowanie przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP (zaawansowane)</span><span class="sxs-lookup"><span data-stu-id="b0091-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="b0091-189">Zaktualizuj pakiet `Microsoft.Quantum.IQSharp`:</span><span class="sxs-lookup"><span data-stu-id="b0091-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="b0091-190">Zweryfikuj wersję pakietu `iqsharp`:</span><span class="sxs-lookup"><span data-stu-id="b0091-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="b0091-191">Dane wyjściowe powinny być podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="b0091-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="b0091-192">Nie przejmuj się, jeśli Twoja wersja jądra `iqsharp` jest nowsza.</span><span class="sxs-lookup"><span data-stu-id="b0091-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="b0091-193">Powinna ona być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="b0091-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="b0091-194">Uruchom następujące polecenie w komórce w każdym z istniejących notesów Jupyter Notebook języka Q#:</span><span class="sxs-lookup"><span data-stu-id="b0091-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

***

<span data-ttu-id="b0091-195">Teraz możesz używać zaktualizowanego jądra IQ# do uruchamiania istniejących notesów Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="b0091-195">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="b0091-196">Aktualizowanie rozszerzenia QDK dla programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0091-196">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="b0091-197">Aktualizowanie rozszerzenia programu Visual Studio dla języka Q#</span><span class="sxs-lookup"><span data-stu-id="b0091-197">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="b0091-198">W programie Visual Studio zostanie wyświetlony monit o zaakceptowanie aktualizacji [rozszerzenia Quantum dla programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="b0091-198">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="b0091-199">Zaakceptuj aktualizację</span><span class="sxs-lookup"><span data-stu-id="b0091-199">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0091-200">Szablony projektów zostaną zaktualizowane wraz z rozszerzeniem.</span><span class="sxs-lookup"><span data-stu-id="b0091-200">The project templates are updated with the extension.</span></span> <span data-ttu-id="b0091-201">Zaktualizowane szablony będą stosowane tylko do nowo tworzonych projektów.</span><span class="sxs-lookup"><span data-stu-id="b0091-201">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="b0091-202">Kod istniejących projektów nie jest aktualizowany podczas aktualizacji rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="b0091-202">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="b0091-203">Aktualizowanie rozszerzenia QDK dla programu VS Code</span><span class="sxs-lookup"><span data-stu-id="b0091-203">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="b0091-204">Aktualizowanie rozszerzenia programu VS Code dla obliczeń kwantowych</span><span class="sxs-lookup"><span data-stu-id="b0091-204">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="b0091-205">Uruchom ponownie program VS Code</span><span class="sxs-lookup"><span data-stu-id="b0091-205">Restart VS Code</span></span>
    - <span data-ttu-id="b0091-206">Przejdź do karty **Extensions** (Rozszerzenia)</span><span class="sxs-lookup"><span data-stu-id="b0091-206">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="b0091-207">Wybierz rozszerzenie **Microsoft Quantum Development Kit for Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="b0091-207">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="b0091-208">Załaduj ponownie rozszerzenie</span><span class="sxs-lookup"><span data-stu-id="b0091-208">Reload the extension</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="b0091-209">Język C# i narzędzie wiersza polecenia `dotnet`</span><span class="sxs-lookup"><span data-stu-id="b0091-209">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="b0091-210">Zaktualizuj szablony projektów kwantowych dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="b0091-210">Update the Quantum project templates for .NET</span></span>

    <span data-ttu-id="b0091-211">Za pomocą wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="b0091-211">From the command line:</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   <span data-ttu-id="b0091-212">Alternatywnie, jeśli zamierzasz używać szablonów wiersza polecenia i masz już zainstalowane rozszerzenie QDK programu VS Code, możesz zaktualizować szablony projektu z poziomu samego rozszerzenia:</span><span class="sxs-lookup"><span data-stu-id="b0091-212">Alternatively, if you intend to use the command line templates, and already have the VS Code QDK extension installed, you can update the project templates from the extension itself:</span></span>

   - [<span data-ttu-id="b0091-213">Aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="b0091-213">Update the QDK extension</span></span>](#update-vs-code-qdk-extension)
   - <span data-ttu-id="b0091-214">W programie VS Code przejdź do pozycji **View** -> **Command Palette** (Widok, Paleta poleceń).</span><span class="sxs-lookup"><span data-stu-id="b0091-214">In VS Code, go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="b0091-215">Wybierz pozycję **Q#: Install command line project templates (Q#: zainstaluj szablony projektu wiersza polecenia)**</span><span class="sxs-lookup"><span data-stu-id="b0091-215">Select **Q#: Install command line project templates**</span></span>
   - <span data-ttu-id="b0091-216">Po kilku sekundach powinno zostać wyświetlone okno podręczne z potwierdzeniem: „project templates installed successfully” (pomyślnie zainstalowano szablony projektów).</span><span class="sxs-lookup"><span data-stu-id="b0091-216">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

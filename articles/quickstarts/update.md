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
ms.openlocfilehash: 84782d1628dd100c0939b2b12aa0a9aa8ab2b80e
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863638"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="9f5a0-103">Aktualizowanie zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="9f5a0-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="9f5a0-104">Dowiedz się, jak zaktualizować zestaw Microsoft Quantum Development Kit (QDK) do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="9f5a0-105">W tym artykule założono, że masz już zainstalowany zestaw QDK.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="9f5a0-106">Jeśli instalujesz go po raz pierwszy, skorzystaj z [przewodnika instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="9f5a0-107">Zalecamy regularne aktualizowanie zestawu QDK do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="9f5a0-108">Wykonaj instrukcje z tego przewodnika aktualizacji, aby przejść na najnowszą wersję zestawu QDK.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="9f5a0-109">Ten proces składa się z dwóch części:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="9f5a0-110">Aktualizowanie istniejących plików i projektów języka Q# w celu dostosowania kodu do zaktualizowanej składni.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="9f5a0-111">Aktualizowanie samego zestawu QDK dla wybranego środowiska deweloperskiego.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-no-locq-projects"></a><span data-ttu-id="9f5a0-112">Aktualizowanie projektów języka Q#</span><span class="sxs-lookup"><span data-stu-id="9f5a0-112">Updating Q# Projects</span></span> 

<span data-ttu-id="9f5a0-113">Niezależnie od tego, czy hostujesz operacje języka Q# przy użyciu środowiska języka C#, czy Python, postępuj zgodnie z tymi instrukcjami, aby zaktualizować projekty języka Q#.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="9f5a0-114">Najpierw sprawdź, czy masz najnowszą wersję [zestawu .NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="9f5a0-115">W wierszu polecenia uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="9f5a0-116">Sprawdź, czy dane wyjściowe zawierają informację o wersji `3.1.100` lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="9f5a0-117">Jeśli nie, zainstaluj [najnowszą wersję](https://dotnet.microsoft.com/download) i sprawdź ponownie.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="9f5a0-118">Następnie postępuj zgodnie z poniższymi instrukcjami odpowiednio do używanej konfiguracji (w programie Visual Studio, Visual Studio Code lub bezpośrednio w wierszu polecenia).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly from the command prompt).</span></span>

### <a name="update-no-locq-projects-in-visual-studio"></a><span data-ttu-id="9f5a0-119">Aktualizowanie projektów języka Q# w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9f5a0-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="9f5a0-120">Zaktualizuj program Visual Studio 2019 do najnowszej wersji — instrukcje znajdziesz [tutaj](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="9f5a0-121">Otwórz rozwiązanie w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="9f5a0-122">Z menu wybierz pozycję**Kompilacja** -> **Wyczyść rozwiązanie**.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="9f5a0-123">W każdym z plików .csproj zaktualizuj platformę docelową do wersji `netcoreapp3.1` (lub `netstandard2.1`, jeśli jest to projekt biblioteki).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="9f5a0-124">W tym celu edytuj wiersze w następującym formacie:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="9f5a0-125">Więcej szczegółowych informacji na temat określania platform docelowych znajdziesz [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="9f5a0-126">W każdym z plików .csproj określ zestaw SDK `Microsoft.Quantum.Sdk`, jak pokazano poniżej.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="9f5a0-127">Zwróć uwagę, że numer wersji powinien odpowiadać najnowszej dostępnej wersji — aby ją określić, sprawdź [informacje o wersji](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. <span data-ttu-id="9f5a0-128">Zapisz i zamknij wszystkie pliki w rozwiązaniu.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="9f5a0-129">Wybierz pozycję **Narzędzia** -> **Wiersz polecenia** -> **Wiersz polecenia dla deweloperów**.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="9f5a0-130">Alternatywnie można użyć konsoli zarządzania pakietami w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="9f5a0-131">Dla każdego projektu w rozwiązaniu uruchom następujące polecenie, aby **usunąć** ten pakiet:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="9f5a0-132">Jeśli w projektach są używane jakiekolwiek inne pakiety Microsoft.Quantum lub Microsoft.Azure.Quantum (na przykład Microsoft.Quantum.Numerics), uruchom polecenie **add**, aby zaktualizować używaną wersję.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="9f5a0-133">Zamknij wiersz polecenia i wybierz pozycję **Kompilacja** -> **Kompiluj rozwiązanie** (*nie* wybieraj polecenia Kompiluj ponownie rozwiązanie).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="9f5a0-134">Możesz teraz przejść do sekcji [Aktualizowanie rozszerzenia QDK dla programu Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-no-locq-projects-in-visual-studio-code"></a><span data-ttu-id="9f5a0-135">Aktualizowanie projektów języka Q# w programie Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9f5a0-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="9f5a0-136">W programie Visual Studio Code otwórz folder zawierający projekt, który chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="9f5a0-137">Wybierz pozycję **Terminal** -> **New Terminal** (Nowy terminal).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="9f5a0-138">Postępuj zgodnie z instrukcjami aktualizowania przy użyciu wiersza polecenia (tuż poniżej).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-138">Follow the instructions for updating using the command prompt (directly below).</span></span>

### <a name="update-no-locq-projects-using-the-command-prompt"></a><span data-ttu-id="9f5a0-139">Aktualizowanie projektów języka Q# przy użyciu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="9f5a0-139">Update Q# projects using the command prompt</span></span>

1. <span data-ttu-id="9f5a0-140">Przejdź do folderu zawierającego główny plik projektu.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="9f5a0-141">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="9f5a0-142">Określ bieżącą wersję zestawu QDK.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="9f5a0-143">Aby ją znaleźć, możesz sprawdzić [informacje o wersji](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="9f5a0-144">Wersja będzie miała format podobny do następującego: `0.12.20072031`.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-144">The version will be in a format similar to `0.12.20072031`.</span></span>

4. <span data-ttu-id="9f5a0-145">W każdym z plików `.csproj` wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="9f5a0-146">Zaktualizuj platformę docelową do wersji `netcoreapp3.1` (lub `netstandard2.1`, jeśli jest to projekt biblioteki).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="9f5a0-147">W tym celu edytuj wiersze w następującym formacie:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="9f5a0-148">Więcej szczegółowych informacji na temat określania platform docelowych znajdziesz [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="9f5a0-149">Zmień odwołanie do zestawu SDK w definicji projektu.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="9f5a0-150">Upewnij się, że numer wersji odpowiada wartości określonej w **kroku 3**.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - <span data-ttu-id="9f5a0-151">Usuń odwołanie do pakietu `Microsoft.Quantum.Development.Kit`, jeśli jest określone w następującym wpisie:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="9f5a0-152">Zaktualizuj wersje wszystkich pakietów Microsoft Quantum do najnowszej wersji zestawu QDK (określonej w **kroku 3**).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="9f5a0-153">Nazwy pakietów odpowiadają następującym wzorcom:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="9f5a0-154">Odwołania do pakietów mają następujący format:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - <span data-ttu-id="9f5a0-155">Zapisz zaktualizowany plik.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-155">Save the updated file.</span></span>

    - <span data-ttu-id="9f5a0-156">Przywróć zależności projektu, wykonując następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="9f5a0-157">Wróć do folderu zawierającego główny plik projektu i uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="9f5a0-158">Po zaktualizowaniu projektów języka Q# możesz zaktualizować sam zestaw QDK zgodnie z poniższymi instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="9f5a0-159">Aktualizowanie zestawu QDK</span><span class="sxs-lookup"><span data-stu-id="9f5a0-159">Updating the QDK</span></span>

<span data-ttu-id="9f5a0-160">Proces aktualizowania zestawu QDK zależy od używanego języka programowania i środowiska.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="9f5a0-161">Wybierz używane środowisko deweloperskie poniżej.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-161">Select your development environment below.</span></span>

* [<span data-ttu-id="9f5a0-162">Python: aktualizowanie pakietu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="9f5a0-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="9f5a0-163">Notesy Jupyter Notebook: aktualizowanie jądra IQ#</span><span class="sxs-lookup"><span data-stu-id="9f5a0-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="9f5a0-164">Visual Studio: aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="9f5a0-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="9f5a0-165">VS Code: aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="9f5a0-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="9f5a0-166">Wiersz polecenia i język C#: aktualizowanie szablonów projektów</span><span class="sxs-lookup"><span data-stu-id="9f5a0-166">Command line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="9f5a0-167">Aktualizowanie pakietu `qsharp` języka Python</span><span class="sxs-lookup"><span data-stu-id="9f5a0-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="9f5a0-168">Procedura aktualizacji zależy od tego, czy program został pierwotnie zainstalowany przy użyciu środowiska conda, czy przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="9f5a0-169">Aktualizowanie przy użyciu środowiska conda (zalecane)</span><span class="sxs-lookup"><span data-stu-id="9f5a0-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="9f5a0-170">Aktywuj środowisko conda, w którym zainstalowano pakiet `qsharp`, a następnie uruchom to polecenie, aby go zaktualizować:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="9f5a0-171">Uruchom następujące polecenie z poziomu lokalizacji plików `.qs`:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="9f5a0-172">Aktualizowanie przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP (zaawansowane)</span><span class="sxs-lookup"><span data-stu-id="9f5a0-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="9f5a0-173">Zaktualizuj jądro `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="9f5a0-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="9f5a0-174">Zweryfikuj wersję jądra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="9f5a0-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="9f5a0-175">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="9f5a0-176">Nie przejmuj się, jeśli Twoja wersja jądra `iqsharp` jest nowsza.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="9f5a0-177">Powinna ona być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="9f5a0-178">Zaktualizuj pakiet `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="9f5a0-179">Zweryfikuj wersję pakietu `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="9f5a0-180">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="9f5a0-181">Uruchom następujące polecenie z poziomu lokalizacji plików `.qs`:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="9f5a0-182">Teraz możesz korzystać ze zaktualizowanego pakietu `qsharp` języka Python do uruchamiania istniejących programów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="9f5a0-183">Aktualizowanie jądra Jupyter IQ#</span><span class="sxs-lookup"><span data-stu-id="9f5a0-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="9f5a0-184">Procedura aktualizacji zależy od tego, czy program został pierwotnie zainstalowany przy użyciu środowiska conda, czy przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="9f5a0-185">Aktualizowanie przy użyciu środowiska conda (zalecane)</span><span class="sxs-lookup"><span data-stu-id="9f5a0-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="9f5a0-186">Aktywuj środowisko conda, w którym zainstalowano pakiet `qsharp`, a następnie uruchom to polecenie, aby je zaktualizować:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="9f5a0-187">Uruchom następujące polecenie w komórce w każdym z istniejących notesów Jupyter Notebook języka Q#:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="9f5a0-188">Aktualizowanie przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP (zaawansowane)</span><span class="sxs-lookup"><span data-stu-id="9f5a0-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="9f5a0-189">Zaktualizuj pakiet `Microsoft.Quantum.IQSharp`:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="9f5a0-190">Zweryfikuj wersję pakietu `iqsharp`:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="9f5a0-191">Dane wyjściowe powinny być podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="9f5a0-192">Nie przejmuj się, jeśli Twoja wersja jądra `iqsharp` jest nowsza.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="9f5a0-193">Powinna ona być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="9f5a0-194">Uruchom następujące polecenie w komórce w każdym z istniejących notesów Jupyter Notebook języka Q#:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

***

<span data-ttu-id="9f5a0-195">Teraz możesz używać zaktualizowanego jądra IQ# do uruchamiania istniejących notesów Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-195">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="9f5a0-196">Aktualizowanie rozszerzenia QDK dla programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9f5a0-196">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="9f5a0-197">Aktualizowanie rozszerzenia programu Visual Studio dla języka Q#</span><span class="sxs-lookup"><span data-stu-id="9f5a0-197">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="9f5a0-198">W programie Visual Studio zostanie wyświetlony monit o zaakceptowanie aktualizacji [rozszerzenia Quantum dla programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="9f5a0-198">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="9f5a0-199">Zaakceptuj aktualizację</span><span class="sxs-lookup"><span data-stu-id="9f5a0-199">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="9f5a0-200">Szablony projektów zostaną zaktualizowane wraz z rozszerzeniem.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-200">The project templates are updated with the extension.</span></span> <span data-ttu-id="9f5a0-201">Zaktualizowane szablony będą stosowane tylko do nowo tworzonych projektów.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-201">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="9f5a0-202">Kod istniejących projektów nie jest aktualizowany podczas aktualizacji rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="9f5a0-202">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="9f5a0-203">Aktualizowanie rozszerzenia QDK dla programu VS Code</span><span class="sxs-lookup"><span data-stu-id="9f5a0-203">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="9f5a0-204">Aktualizowanie rozszerzenia programu VS Code dla obliczeń kwantowych</span><span class="sxs-lookup"><span data-stu-id="9f5a0-204">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="9f5a0-205">Uruchom ponownie program VS Code</span><span class="sxs-lookup"><span data-stu-id="9f5a0-205">Restart VS Code</span></span>
    - <span data-ttu-id="9f5a0-206">Przejdź do karty **Extensions** (Rozszerzenia)</span><span class="sxs-lookup"><span data-stu-id="9f5a0-206">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="9f5a0-207">Wybierz rozszerzenie **Microsoft Quantum Development Kit for Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="9f5a0-207">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="9f5a0-208">Załaduj ponownie rozszerzenie</span><span class="sxs-lookup"><span data-stu-id="9f5a0-208">Reload the extension</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="9f5a0-209">Język C# i narzędzie wiersza polecenia `dotnet`</span><span class="sxs-lookup"><span data-stu-id="9f5a0-209">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="9f5a0-210">Zaktualizuj szablony projektów kwantowych dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="9f5a0-210">Update the Quantum project templates for .NET</span></span>

    <span data-ttu-id="9f5a0-211">W wierszu polecenia:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-211">From the command prompt:</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   <span data-ttu-id="9f5a0-212">Alternatywnie, jeśli zamierzasz używać szablonów wiersza polecenia i masz już zainstalowane rozszerzenie QDK programu VS Code, możesz zaktualizować szablony projektu z poziomu samego rozszerzenia:</span><span class="sxs-lookup"><span data-stu-id="9f5a0-212">Alternatively, if you intend to use the command-line templates, and already have the VS Code QDK extension installed, you can update the project templates from the extension itself:</span></span>

   - [<span data-ttu-id="9f5a0-213">Aktualizowanie rozszerzenia QDK</span><span class="sxs-lookup"><span data-stu-id="9f5a0-213">Update the QDK extension</span></span>](#update-vs-code-qdk-extension)
   - <span data-ttu-id="9f5a0-214">W programie VS Code przejdź do pozycji **View** -> **Command Palette** (Widok, Paleta poleceń).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-214">In VS Code, go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="9f5a0-215">Wybierz pozycję **Q#: Install command line project templates (Q#: zainstaluj szablony projektu wiersza polecenia)**</span><span class="sxs-lookup"><span data-stu-id="9f5a0-215">Select **Q#: Install command line project templates**</span></span>
   - <span data-ttu-id="9f5a0-216">Po kilku sekundach powinno zostać wyświetlone okno podręczne z potwierdzeniem: „project templates installed successfully” (pomyślnie zainstalowano szablony projektów).</span><span class="sxs-lookup"><span data-stu-id="9f5a0-216">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

---
title: Dowiedz się, jak aktualizować Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463286"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="5b494-102">Aktualizowanie Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="5b494-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="5b494-103">Dowiedz się, jak zaktualizować Microsoft Quantum Development Kit (QDK) do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="5b494-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="5b494-104">W tym artykule przyjęto założenie, że zainstalowano już QDK.</span><span class="sxs-lookup"><span data-stu-id="5b494-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="5b494-105">Jeśli instalujesz po raz pierwszy, zapoznaj się z [Podręcznikiem instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="5b494-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="5b494-106">Aktualizowanie projektów Q #</span><span class="sxs-lookup"><span data-stu-id="5b494-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="5b494-107">Najpierw zainstaluj najnowszą wersję [zestaw .NET Core SDK 3,0](https://dotnet.microsoft.com/download) , a następnie uruchom następujące polecenie w wierszu polecenia:</span><span class="sxs-lookup"><span data-stu-id="5b494-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="5b494-108">Sprawdź, czy dane wyjściowe mają wartość 3.0.100 lub wyższą, a następnie postępuj zgodnie z poniższymi instrukcjami, w zależności od konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="5b494-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="5b494-109">W programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b494-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="5b494-110">Aktualizacja do najnowszej wersji programu Visual Studio 2019, zobacz [tutaj](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) , aby uzyskać instrukcje</span><span class="sxs-lookup"><span data-stu-id="5b494-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="5b494-111">Otwórz rozwiązanie w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b494-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="5b494-112">Z menu wybierz opcję Kompiluj > Wyczyść rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="5b494-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="5b494-113">[Zaktualizuj platformę docelową](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) w każdym z plików. csproj na netcoreapp 3.0 (lub Standard 2.1, jeśli jest to projekt biblioteki)</span><span class="sxs-lookup"><span data-stu-id="5b494-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="5b494-114">Zapisz i Zamknij wszystkie pliki w rozwiązaniu</span><span class="sxs-lookup"><span data-stu-id="5b494-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="5b494-115">Wybierz Narzędzia > > wiersza polecenia wiersz polecenia dla deweloperów</span><span class="sxs-lookup"><span data-stu-id="5b494-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="5b494-116">Dla każdego projektu w rozwiązaniu Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="5b494-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="5b494-117">Jeśli Twoje projekty korzystają z innych pakietów Microsoft. Quantum, uruchom polecenie również.</span><span class="sxs-lookup"><span data-stu-id="5b494-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="5b494-118">Zamknij wiersz polecenia i wybierz opcję Kompiluj > Kompiluj rozwiązanie ( *nie* wybieraj opcji Skompiluj ponownie rozwiązanie, ponieważ ponowne kompilowanie zakończy się niepowodzeniem)</span><span class="sxs-lookup"><span data-stu-id="5b494-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="5b494-119">W Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5b494-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="5b494-120">W Visual Studio Code Otwórz folder zawierający projekt do zaktualizowania</span><span class="sxs-lookup"><span data-stu-id="5b494-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="5b494-121">Wybierz pozycję Terminal > nowym terminalu</span><span class="sxs-lookup"><span data-stu-id="5b494-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="5b494-122">Postępuj zgodnie z instrukcjami dotyczącymi aktualizowania przy użyciu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="5b494-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="5b494-123">Korzystanie z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="5b494-123">Using the command line</span></span>

1. <span data-ttu-id="5b494-124">Przejdź do folderu zawierającego plik projektu</span><span class="sxs-lookup"><span data-stu-id="5b494-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="5b494-125">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="5b494-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="5b494-126">[Zaktualizuj platformę docelową](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) w każdym z plików. csproj na netcoreapp 3.0 (lub Standard 2.1, jeśli jest to projekt biblioteki)</span><span class="sxs-lookup"><span data-stu-id="5b494-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="5b494-127">Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="5b494-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="5b494-128">Jeśli projekt używa innych pakietów Microsoft. Quantum, uruchom polecenie również.</span><span class="sxs-lookup"><span data-stu-id="5b494-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="5b494-129">Zapisz i Zamknij wszystkie pliki</span><span class="sxs-lookup"><span data-stu-id="5b494-129">Save and close all files</span></span>
6. <span data-ttu-id="5b494-130">Powtórz 1-4 dla każdej zależności projektu, a następnie przejdź z powrotem do folderu zawierającego główny projekt i uruchom:</span><span class="sxs-lookup"><span data-stu-id="5b494-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="5b494-131">Aktualizacja IQ # dla języka Python</span><span class="sxs-lookup"><span data-stu-id="5b494-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="5b494-132">Aktualizowanie jądra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="5b494-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="5b494-133">Weryfikowanie wersji `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="5b494-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="5b494-134">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="5b494-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="5b494-135">Aktualizowanie pakietu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="5b494-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="5b494-136">Weryfikowanie wersji `qsharp`</span><span class="sxs-lookup"><span data-stu-id="5b494-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="5b494-137">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="5b494-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="5b494-138">Uruchom następujące polecenie z lokalizacji plików `.qs`</span><span class="sxs-lookup"><span data-stu-id="5b494-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="5b494-139">Teraz można używać zaktualizowanej wersji QDK do uruchamiania istniejących programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="5b494-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="5b494-140">Aktualizacja IQ # dla notesów Jupyter</span><span class="sxs-lookup"><span data-stu-id="5b494-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="5b494-141">Aktualizowanie jądra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="5b494-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="5b494-142">Weryfikowanie wersji `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="5b494-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="5b494-143">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="5b494-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="5b494-144">Uruchom następujące polecenie w komórce w Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="5b494-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="5b494-145">Teraz możesz otworzyć istniejący Notes programu Jupyter i uruchomić go ze zaktualizowanym QDK.</span><span class="sxs-lookup"><span data-stu-id="5b494-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="5b494-146">Zaktualizuj rozszerzenie Visual Studio QDK</span><span class="sxs-lookup"><span data-stu-id="5b494-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="5b494-147">Aktualizowanie rozszerzenia Q # programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b494-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="5b494-148">Program Visual Studio poprosi o zaakceptowanie aktualizacji [rozszerzenia programu Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="5b494-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="5b494-149">Zaakceptuj aktualizację</span><span class="sxs-lookup"><span data-stu-id="5b494-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b494-150">Szablony projektu są aktualizowane przy użyciu rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="5b494-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="5b494-151">Zaktualizowane szablony mają zastosowanie tylko do nowo utworzonych projektów.</span><span class="sxs-lookup"><span data-stu-id="5b494-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="5b494-152">Kod dla istniejących projektów nie jest aktualizowany, gdy rozszerzenie zostanie zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="5b494-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="5b494-153">Aktualizacja rozszerzenia QDK VS Code</span><span class="sxs-lookup"><span data-stu-id="5b494-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="5b494-154">Aktualizowanie rozszerzenia Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="5b494-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="5b494-155">Uruchom ponownie VS Code</span><span class="sxs-lookup"><span data-stu-id="5b494-155">Restart VS Code</span></span>
    - <span data-ttu-id="5b494-156">Przejdź do karty **rozszerzenia**</span><span class="sxs-lookup"><span data-stu-id="5b494-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="5b494-157">Wybierz **Microsoft Quantum Development Kit rozszerzenia Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="5b494-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="5b494-158">Załaduj ponownie rozszerzenie</span><span class="sxs-lookup"><span data-stu-id="5b494-158">Reload the extension</span></span>

1. <span data-ttu-id="5b494-159">Aktualizowanie szablonów projektów Quantum:</span><span class="sxs-lookup"><span data-stu-id="5b494-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="5b494-160">Przejdź do pozycji **Widok** -> **Paleta poleceń**</span><span class="sxs-lookup"><span data-stu-id="5b494-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="5b494-161">Wybierz pozycję **Q #: Instalowanie szablonów projektu**</span><span class="sxs-lookup"><span data-stu-id="5b494-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="5b494-162">C#przy użyciu narzędzia wiersza polecenia `dotnet`</span><span class="sxs-lookup"><span data-stu-id="5b494-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="5b494-163">Aktualizowanie szablonów projektów Quantum dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="5b494-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="5b494-164">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="5b494-164">What's next?</span></span>

<span data-ttu-id="5b494-165">Teraz, po zaktualizowaniu zestawu Quantum Development Kit w preferowanym środowisku, można nadal opracowywać i uruchamiać programy Quantum.</span><span class="sxs-lookup"><span data-stu-id="5b494-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="5b494-166">Jeśli nie zapisano jeszcze programu, możesz rozpocząć pracę z [pierwszym programem Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="5b494-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>

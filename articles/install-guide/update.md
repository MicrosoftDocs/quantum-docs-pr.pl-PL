---
title: Dowiedz się, jak aktualizować Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185855"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c98cc-102">Aktualizowanie Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="c98cc-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c98cc-103">Dowiedz się, jak zaktualizować Microsoft Quantum Development Kit (QDK) do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="c98cc-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="c98cc-104">W tym artykule przyjęto założenie, że zainstalowano już QDK.</span><span class="sxs-lookup"><span data-stu-id="c98cc-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="c98cc-105">Jeśli instalujesz po raz pierwszy, zapoznaj się z [Podręcznikiem instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="c98cc-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="c98cc-106">Kroki aktualizacji zależą od środowiska deweloperskiego.</span><span class="sxs-lookup"><span data-stu-id="c98cc-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="c98cc-107">Wybierz środowisko z następujących sekcji.</span><span class="sxs-lookup"><span data-stu-id="c98cc-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="c98cc-108">Python</span><span class="sxs-lookup"><span data-stu-id="c98cc-108">Python</span></span>

1. <span data-ttu-id="c98cc-109">Aktualizowanie jądra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="c98cc-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c98cc-110">Weryfikowanie wersji `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="c98cc-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c98cc-111">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="c98cc-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="c98cc-112">Aktualizowanie pakietu `qsharp`</span><span class="sxs-lookup"><span data-stu-id="c98cc-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="c98cc-113">Weryfikowanie wersji `qsharp`</span><span class="sxs-lookup"><span data-stu-id="c98cc-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="c98cc-114">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="c98cc-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="c98cc-115">Teraz można używać zaktualizowanej wersji QDK do uruchamiania istniejących programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="c98cc-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="c98cc-116">Notesy programu Jupyter</span><span class="sxs-lookup"><span data-stu-id="c98cc-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="c98cc-117">Aktualizowanie jądra `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="c98cc-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c98cc-118">Weryfikowanie wersji `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="c98cc-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c98cc-119">Powinny zostać wyświetlone następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="c98cc-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="c98cc-120">Teraz możesz otworzyć istniejący Notes programu Jupyter i uruchomić go ze zaktualizowanym QDK.</span><span class="sxs-lookup"><span data-stu-id="c98cc-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="c98cc-121">C#w systemie Windows, korzystanie z programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c98cc-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="c98cc-122">Aktualizowanie rozszerzenia Q # programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c98cc-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="c98cc-123">Program Visual Studio poprosi o zaakceptowanie aktualizacji [rozszerzenia programu Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="c98cc-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="c98cc-124">Zaakceptuj aktualizację</span><span class="sxs-lookup"><span data-stu-id="c98cc-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="c98cc-125">Szablony projektu są aktualizowane przy użyciu rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="c98cc-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="c98cc-126">Zaktualizowane szablony mają zastosowanie tylko do nowo utworzonych projektów.</span><span class="sxs-lookup"><span data-stu-id="c98cc-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="c98cc-127">Kod dla istniejących projektów nie jest aktualizowany, gdy rozszerzenie zostanie zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="c98cc-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="c98cc-128">Aktualizowanie pakietów QDK</span><span class="sxs-lookup"><span data-stu-id="c98cc-128">Update the QDK packages</span></span>

    - <span data-ttu-id="c98cc-129">Otwórz istniejącą aplikację</span><span class="sxs-lookup"><span data-stu-id="c98cc-129">Open an existing application</span></span>
    - <span data-ttu-id="c98cc-130">Wybierz **zależności** w Eksplorator rozwiązań</span><span class="sxs-lookup"><span data-stu-id="c98cc-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="c98cc-131">Wybierz pozycję **Zarządzaj pakietami NuGet**</span><span class="sxs-lookup"><span data-stu-id="c98cc-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="c98cc-132">Aktualizowanie pakietów **Microsoft. Quantum** do najnowszej wersji</span><span class="sxs-lookup"><span data-stu-id="c98cc-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="c98cc-133">Teraz możesz uruchomić aplikację przy użyciu najnowszej QDK.</span><span class="sxs-lookup"><span data-stu-id="c98cc-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="c98cc-134">C#, przy użyciu VS Code</span><span class="sxs-lookup"><span data-stu-id="c98cc-134">C#, using VS Code</span></span>

1. <span data-ttu-id="c98cc-135">Aktualizowanie rozszerzenia Quantum VS Code</span><span class="sxs-lookup"><span data-stu-id="c98cc-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="c98cc-136">Uruchom ponownie VS Code</span><span class="sxs-lookup"><span data-stu-id="c98cc-136">Restart VS Code</span></span>
    - <span data-ttu-id="c98cc-137">Przejdź do karty **rozszerzenia**</span><span class="sxs-lookup"><span data-stu-id="c98cc-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="c98cc-138">Wybierz **Microsoft Quantum Development Kit rozszerzenia Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="c98cc-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="c98cc-139">Załaduj ponownie rozszerzenie</span><span class="sxs-lookup"><span data-stu-id="c98cc-139">Reload the extension</span></span>

1. <span data-ttu-id="c98cc-140">Aktualizowanie szablonów projektów Quantum:</span><span class="sxs-lookup"><span data-stu-id="c98cc-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="c98cc-141">Przejdź do **widoku** **paleta poleceń** -> </span><span class="sxs-lookup"><span data-stu-id="c98cc-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="c98cc-142">Wybierz pozycję **Q #: Instalowanie szablonów projektu**</span><span class="sxs-lookup"><span data-stu-id="c98cc-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="c98cc-143">Otwórz istniejącą aplikację w VS Code</span><span class="sxs-lookup"><span data-stu-id="c98cc-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="c98cc-144">Edytuj plik. csproj, aby dodać nowe wersje pakietu</span><span class="sxs-lookup"><span data-stu-id="c98cc-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="c98cc-145">Jeśli używasz innych pakietów `Microsoft.Quantum`, zaktualizuj je.</span><span class="sxs-lookup"><span data-stu-id="c98cc-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="c98cc-146">Teraz możesz uruchomić aplikację ze zaktualizowanym QDK</span><span class="sxs-lookup"><span data-stu-id="c98cc-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="c98cc-147">C#przy użyciu narzędzia wiersza polecenia `dotnet`</span><span class="sxs-lookup"><span data-stu-id="c98cc-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="c98cc-148">Aktualizowanie szablonów projektów Quantum dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="c98cc-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="c98cc-149">Aktualizowanie i uruchamianie istniejącej aplikacji</span><span class="sxs-lookup"><span data-stu-id="c98cc-149">Update and run an existing application</span></span>

    - <span data-ttu-id="c98cc-150">Aktualizowanie wersji pakietu QDK w aplikacji</span><span class="sxs-lookup"><span data-stu-id="c98cc-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="c98cc-151">Jeśli aplikacja korzysta z innych pakietów `Microsoft.Quantum`, zaktualizuj je.</span><span class="sxs-lookup"><span data-stu-id="c98cc-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="c98cc-152">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="c98cc-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="c98cc-153">Aplikacja będzie działać z nowymi wersjami pakietu</span><span class="sxs-lookup"><span data-stu-id="c98cc-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="c98cc-154">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="c98cc-154">What's next?</span></span>

<span data-ttu-id="c98cc-155">Teraz, po zaktualizowaniu zestawu Quantum Development Kit w preferowanym środowisku, można nadal opracowywać i uruchamiać programy Quantum.</span><span class="sxs-lookup"><span data-stu-id="c98cc-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="c98cc-156">Jeśli nie zapisano jeszcze programu, możesz rozpocząć pracę z [pierwszym programem Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="c98cc-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>

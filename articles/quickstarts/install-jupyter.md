---
title: Programowanie w języku Q# przy użyciu notesów Jupyter Notebook
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274163"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="2dd1c-102">Programowanie w języku Q# przy użyciu notesów Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2dd1c-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="2dd1c-103">Zainstaluj zestaw QDK na potrzeby opracowywania operacji języka Q# w notesach Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="2dd1c-104">Notesy Jupyter Notebook zapewniają możliwość wykonywania kodu w miejscu, a także instrukcje, notatki i inną zawartość.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="2dd1c-105">Jest to idealne środowisko do pisania kodu języka Q# z osadzonymi wyjaśnieniami lub interaktywnych samouczków wykonywania obliczeń kwantowych.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="2dd1c-106">Oto jak zacząć tworzyć własne notesy języka Q#.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="2dd1c-107">IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie zestawu .NET Core SDK używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="2dd1c-108">W notesach Jupyter Notebook języka Q# można uruchamiać tylko kod języka Q# i nie można wywoływać operacji z zewnętrznych programów hosta (na przykład z plików języka Python lub C#).</span><span class="sxs-lookup"><span data-stu-id="2dd1c-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="2dd1c-109">To środowisko nie będzie odpowiednie, jeśli chcesz połączyć program kwantowy z zewnętrznym klasycznym programem hosta.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="2dd1c-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="2dd1c-110">Prerequisites</span></span>

    - <span data-ttu-id="2dd1c-111">Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="2dd1c-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="2dd1c-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2dd1c-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="2dd1c-113">Zestaw .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="2dd1c-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="2dd1c-114">Instalowanie pakietu `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="2dd1c-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="2dd1c-115">Jeśli w kroku `dotnet iqsharp install` wystąpił błąd, otwórz nowe okno terminalu i spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="2dd1c-116">Jeśli to nadal nie działa, spróbuj znaleźć zainstalowane narzędzie `dotnet-iqsharp` (w systemie Windows `dotnet-iqsharp.exe`) i uruchomić następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="2dd1c-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="2dd1c-117">gdzie `/path/to/dotnet-iqsharp` należy zastąpić ścieżką bezwzględną narzędzia `dotnet-iqsharp` w systemie plików.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="2dd1c-118">Zwykle znajduje się ono w podfolderze `.dotnet/tools` w folderze profilu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="2dd1c-119">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="2dd1c-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="2dd1c-120">Uruchom następujące polecenie, aby uruchomić serwer notesów:</span><span class="sxs-lookup"><span data-stu-id="2dd1c-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="2dd1c-121">Aby otworzyć notes Jupyter Notebook, skopiuj i wklej adres URL otrzymany w wierszu polecenia do okna przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="2dd1c-122">Utwórz notes Jupyter Notebook z jądrem Q# i dodaj następujący kod do pierwszej komórki notesu:</span><span class="sxs-lookup"><span data-stu-id="2dd1c-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="2dd1c-123">Uruchom tę komórkę notesu:</span><span class="sxs-lookup"><span data-stu-id="2dd1c-123">Run this cell of the notebook:</span></span>

        ![Komórka notesu Jupyter Notebook z kodem języka Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="2dd1c-125">W danych wyjściowych komórki powinien zostać wyświetlony element `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="2dd1c-126">W przypadku uruchamiania w notesach Jupyter Notebook kod języka Q# jest kompilowany, a notes zwraca w danych wyjściowych nazwy znalezionych operacji.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="2dd1c-127">W nowej komórce wykonaj utworzoną operację w symulatorze za pomocą polecenia `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="2dd1c-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Komórka notesu Jupyter Notebook z poleceniem magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="2dd1c-129">Na ekranie powinien zostać wyświetlony komunikat wraz z wynikiem wywołanej operacji (w tym przypadku jest to pusta krotka `()`, ponieważ operacja zwraca po prostu typ `Unit`).</span><span class="sxs-lookup"><span data-stu-id="2dd1c-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2dd1c-130">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="2dd1c-130">Next steps</span></span>

<span data-ttu-id="2dd1c-131">Po zainstalowaniu zestawu QDK na potrzeby notesów Jupyter Notebook języka Q# możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng), pisząc kod języka Q# bezpośrednio w środowisku Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="2dd1c-132">Aby znaleźć więcej przykładów zastosowań notesów Jupyter Notebook języka Q#, zobacz:</span><span class="sxs-lookup"><span data-stu-id="2dd1c-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="2dd1c-133">[Wprowadzenie do języka Q# i notesów Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="2dd1c-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="2dd1c-134">Tam znajdziesz notes Jupyter Notebook języka Q#, w którym pokazano, jak używać języka Q# w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="2dd1c-135">[Quantum Katas](xref:microsoft.quantum.overview.katas) to kolekcja typu open-source, zawierająca realizowane samodzielnie samouczki oraz zestawy ćwiczeń programistycznych w formie notesów Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="2dd1c-136">[Notesy samouczków Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) to dobry sposób, aby zacząć.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="2dd1c-137">Celem samouczków Quantum Katas jest połączenie nauki elementów obliczeń kwantowych i tworzenia zawartości w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="2dd1c-138">To doskonały przykład zawartości, którą można tworzyć za pomocą notesów Jupyter Notebook języka Q#.</span><span class="sxs-lookup"><span data-stu-id="2dd1c-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>

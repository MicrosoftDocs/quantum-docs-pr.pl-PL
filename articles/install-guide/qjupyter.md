---
title: Programowanie przy użyciu notesów Jupyter w języku Q#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 9117794d6cf6f05fa34e05c21fad8977d0e76505
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577824"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="70862-102">Programowanie przy użyciu notesów Jupyter w języku Q#</span><span class="sxs-lookup"><span data-stu-id="70862-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="70862-103">Zainstaluj QDK na potrzeby opracowywania operacji Q # w notesach Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="70862-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="70862-104">Notesy Jupyter umożliwiają wykonywanie kodu w miejscu wraz z instrukcjami, notatkami i inną zawartością.</span><span class="sxs-lookup"><span data-stu-id="70862-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="70862-105">To środowisko jest idealne do pisania kodu Q # z objaśnieniami osadzonymi lub interaktywnymi samouczkami przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="70862-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="70862-106">Oto jak zacząć tworzyć własne notesy języka Q#.</span><span class="sxs-lookup"><span data-stu-id="70862-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="70862-107">IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie zestawu .NET Core SDK używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="70862-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="70862-108">W notesach Q # Jupyter można uruchomić tylko kod Q #, a operacji nie można wywołać z zewnętrznych programów hosta (np. plików Python lub C#).</span><span class="sxs-lookup"><span data-stu-id="70862-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="70862-109">To środowisko nie jest odpowiednie, jeśli celem jest połączenie zewnętrznego klasycznego programu hosta z programem Quantum.</span><span class="sxs-lookup"><span data-stu-id="70862-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="70862-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="70862-110">Pre-requisites</span></span>

    - <span data-ttu-id="70862-111">[Python](https://www.python.org/downloads/) 3,6 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="70862-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="70862-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="70862-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="70862-113">Zestaw .NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="70862-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="70862-114">Instalowanie pakietu `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="70862-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="70862-115">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="70862-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="70862-116">Uruchom następujące polecenie, aby uruchomić serwer notesów:</span><span class="sxs-lookup"><span data-stu-id="70862-116">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="70862-117">Aby otworzyć Jupyter Notebook, skopiuj i wklej adres URL podany w wierszu polecenia do przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="70862-117">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="70862-118">Utwórz Jupyter Notebook przy użyciu jądra Q # i Dodaj następujący kod do pierwszej komórki notesu:</span><span class="sxs-lookup"><span data-stu-id="70862-118">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="70862-119">Uruchom tę komórkę notesu:</span><span class="sxs-lookup"><span data-stu-id="70862-119">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook komórki z kodem Q #](~/media/install-guide-jupyter.png)

        <span data-ttu-id="70862-121">W danych wyjściowych komórki powinien zostać wyświetlony element `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="70862-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="70862-122">Podczas uruchamiania w Jupyter Notebook kod Q # jest kompilowany, a Notes będzie wyprowadzał nazwę znalezionych operacji.</span><span class="sxs-lookup"><span data-stu-id="70862-122">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="70862-123">W nowej komórce wykonaj właśnie utworzoną operację (w symulatorze) za pomocą `%simulate` polecenia:</span><span class="sxs-lookup"><span data-stu-id="70862-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook komórki z użyciem symulowania Magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="70862-125">Powinien zostać wyświetlony komunikat wydrukowany na ekranie wraz z wynikiem wywołanej operacji (w tym miejscu zostanie wyświetlona pusta krotka, `()` ponieważ operacja po prostu zwraca `Unit` Typ).</span><span class="sxs-lookup"><span data-stu-id="70862-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="70862-126">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="70862-126">Next steps</span></span>

<span data-ttu-id="70862-127">Po zainstalowaniu QDK dla notesów Q # Jupyter można napisać i uruchomić [swój pierwszy program Quantum](xref:microsoft.quantum.quickstarts.qrng) , pisząc kod Q bezpośrednio w środowisku Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="70862-127">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="70862-128">Aby uzyskać więcej przykładów, co możesz zrobić z notesami Q # Jupyter, zapoznaj się z tematem:</span><span class="sxs-lookup"><span data-stu-id="70862-128">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="70862-129">[Wprowadzenie do programu Q # i Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="70862-129">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="70862-130">Znajdziesz Jupyter Notebook Q #, który pokazuje, jak używać Q # w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="70862-130">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="70862-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), Kolekcja typu "open source" z własnymi samouczkami i zestawami ćwiczeń programistycznych w postaci notesów Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="70862-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="70862-132">[Notesy w samouczku Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) są dobrym punktem początkowym.</span><span class="sxs-lookup"><span data-stu-id="70862-132">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="70862-133">Katas Quantum jest celem uczenia się elementów opartych na obliczeniach Quantum i programowania Q # w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="70862-133">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="70862-134">Są one doskonałym przykładem rodzaju zawartości, którą można utworzyć za pomocą notesów Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="70862-134">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>

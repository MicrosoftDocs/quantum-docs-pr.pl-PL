---
title: 'Tworzenie za pomocą notesów Q # Jupyter'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 3302a9bd0652b2dea86b844058bf8303ee7a4a7f
ms.sourcegitcommit: c85c1b439807ac576d3a11aadca307d57b059673
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2020
ms.locfileid: "83551043"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="13264-102">Tworzenie za pomocą notesów Q # Jupyter</span><span class="sxs-lookup"><span data-stu-id="13264-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="13264-103">Zainstaluj QDK na potrzeby opracowywania operacji Q # w notesach Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="13264-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="13264-104">Notesy Jupyter umożliwiają wykonywanie kodu w miejscu wraz z instrukcjami, notatkami i inną zawartością.</span><span class="sxs-lookup"><span data-stu-id="13264-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="13264-105">To środowisko jest idealne do pisania kodu Q # z objaśnieniami osadzonymi lub interaktywnymi samouczkami przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="13264-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="13264-106">Oto jak zacząć tworzyć własne notesy języka Q#.</span><span class="sxs-lookup"><span data-stu-id="13264-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="13264-107">IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie zestawu .NET Core SDK używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="13264-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="13264-108">W notesach Q # Jupyter można uruchomić tylko kod Q #, a operacji nie można wywołać z zewnętrznych programów hosta (np. plików Python lub C#).</span><span class="sxs-lookup"><span data-stu-id="13264-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="13264-109">To środowisko nie jest odpowiednie, jeśli celem jest połączenie zewnętrznego klasycznego programu hosta z programem Quantum.</span><span class="sxs-lookup"><span data-stu-id="13264-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="13264-110">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="13264-110">Pre-requisites</span></span>

    - <span data-ttu-id="13264-111">[Python](https://www.python.org/downloads/) 3,6 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="13264-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="13264-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="13264-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="13264-113">Zestaw .NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="13264-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="13264-114">Instalowanie pakietu `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="13264-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="13264-115">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="13264-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="13264-116">Uruchom następujące polecenie, aby uruchomić serwer notesów:</span><span class="sxs-lookup"><span data-stu-id="13264-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="13264-117">Aby otworzyć Notes Jupyter i wkleić adres URL podany w wierszu polecenia do przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="13264-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="13264-118">Utwórz notes Jupyter z jądrem Q# i dodaj następujący kod do pierwszej komórki notesu:</span><span class="sxs-lookup"><span data-stu-id="13264-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="13264-119">Uruchom tę komórkę notesu:</span><span class="sxs-lookup"><span data-stu-id="13264-119">Run this cell of the notebook:</span></span>

        ![Komórka notesu Jupyter z kodem języka Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="13264-121">W danych wyjściowych komórki powinien zostać wyświetlony element `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="13264-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="13264-122">W przypadku uruchamiania w notesach Jupyter kod języka Q# jest kompilowany, a notes zwraca w danych wyjściowych nazwę znalezionych operacji.</span><span class="sxs-lookup"><span data-stu-id="13264-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="13264-123">W nowej komórce wykonaj właśnie utworzoną operację (w symulatorze) za pomocą `%simulate` polecenia:</span><span class="sxs-lookup"><span data-stu-id="13264-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Komórka notesu Jupyter z poleceniem magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="13264-125">Powinien zostać wyświetlony komunikat wydrukowany na ekranie wraz z wynikiem wywołanej operacji (w tym miejscu zostanie wyświetlona pusta krotka, `()` ponieważ operacja po prostu zwraca `Unit` Typ).</span><span class="sxs-lookup"><span data-stu-id="13264-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="13264-126">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="13264-126">Next steps</span></span>

<span data-ttu-id="13264-127">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="13264-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

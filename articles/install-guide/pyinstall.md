---
title: 'Programowanie przy użyciu języka Q # i języka Python'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630284"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="51ac6-102">Programowanie przy użyciu języka Q # i języka Python</span><span class="sxs-lookup"><span data-stu-id="51ac6-102">Develop with Q# and Python</span></span>

<span data-ttu-id="51ac6-103">Zainstaluj program QDK w celu opracowania programów do obsługi hostów języka Python w celu wywołania operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="51ac6-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="51ac6-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="51ac6-104">Prerequisites</span></span>

    - <span data-ttu-id="51ac6-105">[Python](https://www.python.org/downloads/) 3,6 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="51ac6-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="51ac6-106">Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="51ac6-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="51ac6-107">Zestaw .NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="51ac6-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="51ac6-108">Zainstaluj `qsharp` pakiet, pakiet języka Python, który umożliwia współdziałanie między elementami Q # i Python.</span><span class="sxs-lookup"><span data-stu-id="51ac6-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="51ac6-109">Zainstaluj IQ #, jądro używane przez Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i wykonywania operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="51ac6-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="51ac6-110">Jeśli wystąpi błąd w trakcie tego `dotnet iqsharp install` kroku, Otwórz nowe okno terminalu i spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="51ac6-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="51ac6-111">Jeśli to nie zadziała, spróbuj zlokalizować zainstalowane `dotnet-iqsharp` Narzędzie (w systemie Windows, `dotnet-iqsharp.exe` ) i uruchomić polecenie:</span><span class="sxs-lookup"><span data-stu-id="51ac6-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="51ac6-112">gdzie `/path/to/dotnet-iqsharp` powinien zostać zastąpiony przez ścieżkę bezwzględną do `dotnet-iqsharp` Narzędzia w systemie plików.</span><span class="sxs-lookup"><span data-stu-id="51ac6-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="51ac6-113">Zwykle będzie to `.dotnet/tools` w folderze profilu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="51ac6-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="51ac6-114">Chociaż możesz użyć funkcji Q # z językiem Python w dowolnym środowisku IDE, zdecydowanie zalecamy używanie Visual Studio Code (VS Code) środowiska IDE dla aplikacji języka Python dla języka Q # +.</span><span class="sxs-lookup"><span data-stu-id="51ac6-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="51ac6-115">Korzystając z Visual Studio Code i rozszerzenia QDK Visual Studio Code, uzyskujesz dostęp do bogatszej funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="51ac6-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="51ac6-116">Zainstaluj [vs Code](https://code.visualstudio.com/download) (systemy Windows, Linux i Mac)</span><span class="sxs-lookup"><span data-stu-id="51ac6-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="51ac6-117">Zainstaluj [rozszerzenie QDK dla vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="51ac6-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="51ac6-118">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="51ac6-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="51ac6-119">Utwórz minimalną operację języka Q#, tworząc plik o nazwie `Operation.qs` i dodając do niego następujący kod:</span><span class="sxs-lookup"><span data-stu-id="51ac6-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="51ac6-120">Utwórz program w języku Python o nazwie `hello_world.py` do wywołania operacji `SayHello()` języka Q#:</span><span class="sxs-lookup"><span data-stu-id="51ac6-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="51ac6-121">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="51ac6-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="51ac6-122">Sprawdź dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="51ac6-122">Verify the output.</span></span> <span data-ttu-id="51ac6-123">Program powinien zwrócić następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="51ac6-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="51ac6-124">Za pomocą notesów Jupyter języka Python można także napisać klasyczny program Python i wywołać operacje Q # z komórek.</span><span class="sxs-lookup"><span data-stu-id="51ac6-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="51ac6-125">Kod języka Python jest tylko zwykłym programem w języku Python.</span><span class="sxs-lookup"><span data-stu-id="51ac6-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="51ac6-126">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="51ac6-126">Next steps</span></span>

<span data-ttu-id="51ac6-127">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="51ac6-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

---
title: Programowanie przy użyciu języków Q# i Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274151"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="833e8-102">Programowanie przy użyciu języków Q# i Python</span><span class="sxs-lookup"><span data-stu-id="833e8-102">Develop with Q# and Python</span></span>

<span data-ttu-id="833e8-103">Zainstaluj zestaw QDK, aby tworzyć programy hosta w języku Python, umożliwiające wywoływanie operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="833e8-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="833e8-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="833e8-104">Prerequisites</span></span>

    - <span data-ttu-id="833e8-105">Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="833e8-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="833e8-106">Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="833e8-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="833e8-107">Zestaw .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="833e8-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="833e8-108">Zainstaluj `qsharp`, pakiet języka Python, który umożliwia współdziałanie między językami Q# i Python.</span><span class="sxs-lookup"><span data-stu-id="833e8-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="833e8-109">Zainstaluj IQ#, jądro używane w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i wykonywania operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="833e8-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="833e8-110">Jeśli w kroku `dotnet iqsharp install` wystąpił błąd, otwórz nowe okno terminalu i spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="833e8-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="833e8-111">Jeśli to nadal nie działa, spróbuj znaleźć zainstalowane narzędzie `dotnet-iqsharp` (w systemie Windows `dotnet-iqsharp.exe`) i uruchomić następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="833e8-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="833e8-112">gdzie `/path/to/dotnet-iqsharp` należy zastąpić ścieżką bezwzględną narzędzia `dotnet-iqsharp` w systemie plików.</span><span class="sxs-lookup"><span data-stu-id="833e8-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="833e8-113">Zwykle znajduje się ono w podfolderze `.dotnet/tools` w folderze profilu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="833e8-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="833e8-114">Chociaż języka Q# wraz z językiem Python można używać w dowolnym środowisku IDE, zdecydowanie zalecamy korzystanie z programu Visual Studio Code (VS Code) jako środowiska IDE na potrzeby aplikacji tworzonych przy użyciu języków Q# i Python.</span><span class="sxs-lookup"><span data-stu-id="833e8-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="833e8-115">Program Visual Studio Code wraz z rozszerzeniem QDK dla programu Visual Studio Code zapewnia dostęp do bardziej rozbudowanych funkcji.</span><span class="sxs-lookup"><span data-stu-id="833e8-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="833e8-116">Zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac)</span><span class="sxs-lookup"><span data-stu-id="833e8-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="833e8-117">Zainstaluj [rozszerzenie QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="833e8-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="833e8-118">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="833e8-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="833e8-119">Utwórz minimalną operację języka Q#, tworząc plik o nazwie `Operation.qs` i dodając do niego następujący kod:</span><span class="sxs-lookup"><span data-stu-id="833e8-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="833e8-120">Utwórz program w języku Python o nazwie `hello_world.py` do wywołania operacji `SayHello()` języka Q#:</span><span class="sxs-lookup"><span data-stu-id="833e8-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="833e8-121">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="833e8-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="833e8-122">Sprawdź dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="833e8-122">Verify the output.</span></span> <span data-ttu-id="833e8-123">Program powinien zwrócić następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="833e8-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="833e8-124">Możesz też użyć notesów Jupyter języka Python, aby napisać klasyczny program języka Python i wywoływać operacje języka Q# z poziomu komórek.</span><span class="sxs-lookup"><span data-stu-id="833e8-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="833e8-125">Ten kod języka Python to zwykły program w języku Python.</span><span class="sxs-lookup"><span data-stu-id="833e8-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="833e8-126">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="833e8-126">Next steps</span></span>

<span data-ttu-id="833e8-127">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="833e8-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

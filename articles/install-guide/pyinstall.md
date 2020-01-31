---
title: 'Programowanie za pomocą narzędzia Q # + Python'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831005"
---
# <a name="develop-with-q--python"></a><span data-ttu-id="22c2b-102">Programowanie za pomocą narzędzia Q # + Python</span><span class="sxs-lookup"><span data-stu-id="22c2b-102">Develop with Q# + Python</span></span>

<span data-ttu-id="22c2b-103">Zainstaluj program QDK w celu opracowania programów do obsługi hostów języka Python w celu wywołania operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="22c2b-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="22c2b-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="22c2b-104">Pre-requisites</span></span>

    - <span data-ttu-id="22c2b-105">Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze</span><span class="sxs-lookup"><span data-stu-id="22c2b-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="22c2b-106">Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="22c2b-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="22c2b-107">Zestaw .NET Core SDK 3,1 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="22c2b-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="22c2b-108">Zainstaluj pakiet `qsharp`, pakiet języka Python, który umożliwia współdziałanie między elementami Q # i Python.</span><span class="sxs-lookup"><span data-stu-id="22c2b-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="22c2b-109">Zainstaluj `iqsharp`, jądro używane przez Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i wykonywania operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="22c2b-109">Install `iqsharp`, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="22c2b-110">Chociaż możesz użyć funkcji Q # z językiem Python w dowolnym środowisku IDE, zdecydowanie zalecamy używanie Visual Studio Code (VS Code) środowiska IDE dla aplikacji języka Python dla języka Q # +.</span><span class="sxs-lookup"><span data-stu-id="22c2b-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="22c2b-111">Korzystając z Visual Studio Code i rozszerzenia QDK Visual Studio Code, uzyskujesz dostęp do bogatszej funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="22c2b-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="22c2b-112">Zainstaluj [vs Code](https://code.visualstudio.com/download) (systemy Windows, Linux i Mac)</span><span class="sxs-lookup"><span data-stu-id="22c2b-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="22c2b-113">Zainstaluj [rozszerzenie QDK dla vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="22c2b-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="22c2b-114">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="22c2b-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="22c2b-115">Utwórz minimalną operację języka Q#, tworząc plik o nazwie `Operation.qs` i dodając do niego następujący kod:</span><span class="sxs-lookup"><span data-stu-id="22c2b-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="22c2b-116">Utwórz program w języku Python o nazwie `hello_world.py` do wywołania operacji `SayHello()` języka Q#:</span><span class="sxs-lookup"><span data-stu-id="22c2b-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="22c2b-117">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="22c2b-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="22c2b-118">Sprawdź dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="22c2b-118">Verify the output.</span></span> <span data-ttu-id="22c2b-119">Program powinien zwrócić następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="22c2b-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="22c2b-120">Za pomocą notesów Jupyter języka Python można także napisać klasyczny program Python i wywołać operacje Q # z komórek.</span><span class="sxs-lookup"><span data-stu-id="22c2b-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="22c2b-121">Kod języka Python jest tylko zwykłym programem w języku Python.</span><span class="sxs-lookup"><span data-stu-id="22c2b-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="22c2b-122">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="22c2b-122">What's next?</span></span>

<span data-ttu-id="22c2b-123">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="22c2b-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>

---
title: 'Programowanie przy użyciu języka Q # i języka Python'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 35499daae0cd0ae329e39b43b0d8dd5a00183871
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660729"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="b62a7-102">Programowanie przy użyciu języka Q # i języka Python</span><span class="sxs-lookup"><span data-stu-id="b62a7-102">Develop with Q# and Python</span></span>

<span data-ttu-id="b62a7-103">Zainstaluj program QDK w celu opracowania programów do obsługi hostów języka Python w celu wywołania operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="b62a7-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="b62a7-104">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b62a7-104">Pre-requisites</span></span>

    - <span data-ttu-id="b62a7-105">[Python](https://www.python.org/downloads/) 3,6 lub nowszy</span><span class="sxs-lookup"><span data-stu-id="b62a7-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="b62a7-106">Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="b62a7-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="b62a7-107">Zestaw .NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="b62a7-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="b62a7-108">Zainstaluj `qsharp` pakiet, pakiet języka Python, który umożliwia współdziałanie między elementami Q # i Python.</span><span class="sxs-lookup"><span data-stu-id="b62a7-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="b62a7-109">Zainstaluj IQ #, jądro używane przez Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i wykonywania operacji Q #.</span><span class="sxs-lookup"><span data-stu-id="b62a7-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="b62a7-110">Chociaż możesz użyć funkcji Q # z językiem Python w dowolnym środowisku IDE, zdecydowanie zalecamy używanie Visual Studio Code (VS Code) środowiska IDE dla aplikacji języka Python dla języka Q # +.</span><span class="sxs-lookup"><span data-stu-id="b62a7-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="b62a7-111">Korzystając z Visual Studio Code i rozszerzenia QDK Visual Studio Code, uzyskujesz dostęp do bogatszej funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="b62a7-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="b62a7-112">Zainstaluj [vs Code](https://code.visualstudio.com/download) (systemy Windows, Linux i Mac)</span><span class="sxs-lookup"><span data-stu-id="b62a7-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="b62a7-113">Zainstaluj [rozszerzenie QDK dla vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="b62a7-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="b62a7-114">Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`</span><span class="sxs-lookup"><span data-stu-id="b62a7-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="b62a7-115">Utwórz minimalną operację języka Q#, tworząc plik o nazwie `Operation.qs` i dodając do niego następujący kod:</span><span class="sxs-lookup"><span data-stu-id="b62a7-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="b62a7-116">Utwórz program w języku Python o nazwie `hello_world.py` do wywołania operacji `SayHello()` języka Q#:</span><span class="sxs-lookup"><span data-stu-id="b62a7-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="b62a7-117">Uruchom program:</span><span class="sxs-lookup"><span data-stu-id="b62a7-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="b62a7-118">Sprawdź dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="b62a7-118">Verify the output.</span></span> <span data-ttu-id="b62a7-119">Program powinien zwrócić następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="b62a7-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="b62a7-120">Za pomocą notesów Jupyter języka Python można także napisać klasyczny program Python i wywołać operacje Q # z komórek.</span><span class="sxs-lookup"><span data-stu-id="b62a7-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="b62a7-121">Kod języka Python jest tylko zwykłym programem w języku Python.</span><span class="sxs-lookup"><span data-stu-id="b62a7-121">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b62a7-122">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="b62a7-122">Next steps</span></span>

<span data-ttu-id="b62a7-123">Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="b62a7-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>

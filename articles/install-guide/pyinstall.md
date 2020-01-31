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
# <a name="develop-with-q--python"></a>Programowanie za pomocą narzędzia Q # + Python

Zainstaluj program QDK w celu opracowania programów do obsługi hostów języka Python w celu wywołania operacji Q #.

1. Wymagania wstępne

    - Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze
    - Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)
    - [Zestaw .NET Core SDK 3,1 lub nowszy](https://www.microsoft.com/net/download)


1. Zainstaluj pakiet `qsharp`, pakiet języka Python, który umożliwia współdziałanie między elementami Q # i Python.

    ```bash
    pip install qsharp
    ```

1. Zainstaluj `iqsharp`, jądro używane przez Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i wykonywania operacji Q #.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. Chociaż możesz użyć funkcji Q # z językiem Python w dowolnym środowisku IDE, zdecydowanie zalecamy używanie Visual Studio Code (VS Code) środowiska IDE dla aplikacji języka Python dla języka Q # +. Korzystając z Visual Studio Code i rozszerzenia QDK Visual Studio Code, uzyskujesz dostęp do bogatszej funkcjonalności.

    - Zainstaluj [vs Code](https://code.visualstudio.com/download) (systemy Windows, Linux i Mac)
    - Zainstaluj [rozszerzenie QDK dla vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Utwórz minimalną operację języka Q#, tworząc plik o nazwie `Operation.qs` i dodając do niego następujący kod:

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - Utwórz program w języku Python o nazwie `hello_world.py` do wywołania operacji `SayHello()` języka Q#:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Uruchom program:

        ```bash
        python hello_world.py
        ```

    - Sprawdź dane wyjściowe. Program powinien zwrócić następujące wiersze:

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * Za pomocą notesów Jupyter języka Python można także napisać klasyczny program Python i wywołać operacje Q # z komórek. Kod języka Python jest tylko zwykłym programem w języku Python.

## <a name="whats-next"></a>Co dalej?

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.write-program).

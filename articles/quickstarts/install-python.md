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
# <a name="develop-with-q-and-python"></a>Programowanie przy użyciu języków Q# i Python

Zainstaluj zestaw QDK, aby tworzyć programy hosta w języku Python, umożliwiające wywoływanie operacji języka Q#.

1. Wymagania wstępne

    - Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze
    - Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)
    - [Zestaw .NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Zainstaluj `qsharp`, pakiet języka Python, który umożliwia współdziałanie między językami Q# i Python.

    ```
    pip install qsharp
    ```

1. Zainstaluj IQ#, jądro używane w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i wykonywania operacji języka Q#.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Jeśli w kroku `dotnet iqsharp install` wystąpił błąd, otwórz nowe okno terminalu i spróbuj ponownie.
    > Jeśli to nadal nie działa, spróbuj znaleźć zainstalowane narzędzie `dotnet-iqsharp` (w systemie Windows `dotnet-iqsharp.exe`) i uruchomić następujące polecenie:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > gdzie `/path/to/dotnet-iqsharp` należy zastąpić ścieżką bezwzględną narzędzia `dotnet-iqsharp` w systemie plików.
    > Zwykle znajduje się ono w podfolderze `.dotnet/tools` w folderze profilu użytkownika.
  
1. Chociaż języka Q# wraz z językiem Python można używać w dowolnym środowisku IDE, zdecydowanie zalecamy korzystanie z programu Visual Studio Code (VS Code) jako środowiska IDE na potrzeby aplikacji tworzonych przy użyciu języków Q# i Python. Program Visual Studio Code wraz z rozszerzeniem QDK dla programu Visual Studio Code zapewnia dostęp do bardziej rozbudowanych funkcji.

    - Zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac)
    - Zainstaluj [rozszerzenie QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

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

        ```
        python hello_world.py
        ```

    - Sprawdź dane wyjściowe. Program powinien zwrócić następujące wiersze:

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * Możesz też użyć notesów Jupyter języka Python, aby napisać klasyczny program języka Python i wywoływać operacje języka Q# z poziomu komórek. Ten kod języka Python to zwykły program w języku Python.

## <a name="next-steps"></a>Następne kroki

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).

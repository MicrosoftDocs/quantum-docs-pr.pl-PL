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
# <a name="develop-with-q-and-python"></a>Programowanie przy użyciu języka Q # i języka Python

Zainstaluj program QDK w celu opracowania programów do obsługi hostów języka Python w celu wywołania operacji Q #.

1. Wymagania wstępne

    - [Python](https://www.python.org/downloads/) 3,6 lub nowszy
    - Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)
    - [Zestaw .NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Zainstaluj `qsharp` pakiet, pakiet języka Python, który umożliwia współdziałanie między elementami Q # i Python.

    ```
    pip install qsharp
    ```

1. Zainstaluj IQ #, jądro używane przez Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i wykonywania operacji Q #.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Jeśli wystąpi błąd w trakcie tego `dotnet iqsharp install` kroku, Otwórz nowe okno terminalu i spróbuj ponownie.
    > Jeśli to nie zadziała, spróbuj zlokalizować zainstalowane `dotnet-iqsharp` Narzędzie (w systemie Windows, `dotnet-iqsharp.exe` ) i uruchomić polecenie:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > gdzie `/path/to/dotnet-iqsharp` powinien zostać zastąpiony przez ścieżkę bezwzględną do `dotnet-iqsharp` Narzędzia w systemie plików.
    > Zwykle będzie to `.dotnet/tools` w folderze profilu użytkownika.
  
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

        ```
        python hello_world.py
        ```

    - Sprawdź dane wyjściowe. Program powinien zwrócić następujące wiersze:

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * Za pomocą notesów Jupyter języka Python można także napisać klasyczny program Python i wywołać operacje Q # z komórek. Kod języka Python jest tylko zwykłym programem w języku Python.

## <a name="next-steps"></a>Następne kroki

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).

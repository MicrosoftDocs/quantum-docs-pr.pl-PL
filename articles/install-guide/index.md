---
title: Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035305"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalowanie zestawu Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym. Zestaw QDK składa się z:

- języka programowania Q#
- zestawu bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#
- aplikacja hosta (napisana w języku Python lub języku .NET), która uruchamia operacje kwantowe napisane w języku Q#
- narzędzia ułatwiające programowanie

W zależności od wybranego środowiska programistycznego istnieją różne kroki instalacji. Wybierz odpowiednie środowisko w poniższych sekcjach.

## <a name="develop-with-python"></a>Programowanie przy użyciu platformy Python

1. Wymagania wstępne

    - Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze
    - Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)
    - [Zestaw .NET Core SDK 2.1 lub nowszy](https://www.microsoft.com/net/download)

1. Instalowanie pakietu `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Instalowanie pakietu `qsharp`

    ```bash
    pip install qsharp
    ```

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Utwórz minimalną operację języka Q#, tworząc plik o nazwie `Operation.qs` i dodając do niego następujący kod:

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
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
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>Programowanie za pomocą notesów Jupyter

1. Wymagania wstępne

    - Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Zestaw .NET Core SDK 2.1 lub nowszy](https://www.microsoft.com/net/download)

1. Instalowanie pakietu `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Uruchom następujące polecenie, aby uruchomić serwer notesów:

        ```bash
        jupyter notebook
        ```

    - Przejdź do adresu URL podanego w wierszu polecenia. Na przykład: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - Utwórz notes Jupyter z jądrem Q# i dodaj następujący kod do pierwszej komórki notesu:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Uruchom tę komórkę notesu:

        ![Komórka notesu Jupyter](~/media/install-guide-jupyter.png)

        W danych wyjściowych komórki powinien zostać wyświetlony element `SayHello`. W przypadku uruchamiania w notesach Jupyter kod języka Q# jest kompilowany, a notes zwraca w danych wyjściowych nazwę znalezionych operacji.

## <a name="develop-with-c-on-windows-using-visual-studio"></a>Programowanie w języku C# w systemie Windows przy użyciu programu Visual Studio

1. Wymagania wstępne

    - Program [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 z włączonym obciążeniem programu .NET Core obsługującym projektowanie dla wielu platform

1. Instalowanie rozszerzenia programu Visual Studio dla języka Q#

    - Pobierz [rozszerzenie programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Dodaj rozszerzenie do programu Visual Studio

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Tworzenie nowej aplikacji w języku Q#

        - Przejdź do pozycji **Plik** -> **Nowy** -> **Projekt**
        - Wpisz `Q#` w polu wyszukiwania
        - Wybierz pozycję **Aplikacja Q#**
        - Wybierz pozycję **Dalej**
        - Wybierz nazwę i lokalizację dla aplikacji
        - Wybierz pozycję **Utwórz**

    - Inspekcja projektu

        Powinny być widoczne dwa utworzone pliki: plik `Driver.cs`, który jest aplikacją hosta języka C#, i plik `Operation.qs`, czyli program języka Q# definiujący prostą operację w celu wydrukowania komunikatu w konsoli.

    - Uruchamianie aplikacji

        - Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**
        - W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.

> [!NOTE]
> * Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.  

## <a name="develop-with-c-using-vs-code"></a>Programowanie w języku C# przy użyciu programu VS Code

1. Wymagania wstępne

   - [VS Code](https://code.visualstudio.com/download)
   - [Zestaw .NET Core SDK 2.1 lub nowszy](https://www.microsoft.com/net/download)

1. Instalowanie rozszerzenia programu VS Code dla obliczeń kwantowych

    - Zainstaluj [rozszerzenie programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Instalowanie szablonów projektów kwantowych:

   - Przejdź do pozycji **Widok** -> **Paleta poleceń**
   - Wybierz pozycję **Q#: Instalowanie szablonów projektów**

    Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Tworzenie nowego projektu:

        - Przejdź do pozycji **Widok** -> **Paleta poleceń**
        - Wybierz pozycję **Q#: Utwórz nowy projekt**
        - Przejdź do lokalizacji w systemie plików, w której chcesz utworzyć aplikację
        - Po utworzeniu projektu kliknij przycisk **Otwórz nowy projekt**

    - Uruchom aplikację:

        - Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**
        - W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`

> [!NOTE]
> * > * Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu Visual Studio Code. Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>Programowanie w języku C# przy użyciu narzędzia wiersza polecenia `dotnet`

1. Wymagania wstępne

    - [Zestaw .NET Core SDK 2.1 lub nowszy](https://www.microsoft.com/net/download)

1. Instalowanie szablonów projektów kwantowych dla platformy .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Tworzenie nowej aplikacji

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - Przechodzenie do nowego katalogu aplikacji

       ```bash
       cd runSayHello
       ```

    Powinny zostać wyświetlone dwa utworzone pliki wraz z plikami projektu aplikacji: plik języka Q# (`Operation.qs`) i plik hosta języka C# (`Driver.cs`).

    - Uruchamianie aplikacji

        ```bash
        dotnet run
        ```

        Powinny zostać wyświetlone następujące dane wyjściowe: `Hello quantum world!`

## <a name="whats-next"></a>Co dalej?

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.write-program).
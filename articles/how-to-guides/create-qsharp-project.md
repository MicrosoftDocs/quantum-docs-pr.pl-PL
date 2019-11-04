---
title: 'Dowiedz się, jak utworzyć projekt Q # przy użyciu zestawu Quantum Development Kit (QDK)'
description: 'Zainicjuj projekt dla rozwoju Quantum przy użyciu QDK i Q # w wybranym środowisku programistycznym'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444178"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Tworzenie projektu Q # w środowisku deweloperskim

Dowiedz się, jak utworzyć projekt Q # z QDK.

Projekt Q # zawiera pliki Q # zawierające kod Quantum oraz program hosta służący do uruchamiania programu Quantum. Program hosta można napisać w językach .NET, takich jak C#, lub w języku Python. Możesz również uruchomić kod Q w notesie Jupyter przy użyciu jądra IQ #.

Wybierz środowisko deweloperskie i język w poniższych sekcjach:

* [Python](#create-a-python-project)
* [Notesy Jupyter](#create-a-jupyter-notebook-project)
* [C#za pomocą programu Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C#z VS Code](#create-a-c-project-using-vs-code)
* [C#przy użyciu wiersza polecenia](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Tworzenie projektu w języku Python

1. Wymagania wstępne

     * [Zestaw Quantum Development Kit dla języka Python](xref:microsoft.quantum.install#develop-with-python)

1. Utwórz folder dla projektu i przejdź do tego folderu

1. Utwórz plik Q # o nazwie `Operation.qs`i Dodaj do niego kod Q. Na przykład:

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. Utwórz plik hosta języka Python o nazwie `host.py`, aby wywołać operację Q #. Na przykład:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Uruchom program:

    ```bash
    python host.py
    ```

1. Sprawdź dane wyjściowe. Program powinien zwrócić następujące wiersze:

    ```bash
    Hello from quantum world!
    0
    ```

Teraz można kontynuować opracowywanie programu Quantum.

## <a name="create-a-jupyter-notebook-project"></a>Tworzenie projektu Jupyter Notebook

1. Wymagania wstępne

    * [Zestaw Quantum Development Kit dla notesów Jupyter](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)

1. Uruchom następujące polecenie, aby uruchomić serwer notesów:

    ```bash
    jupyter notebook
    ```

1. Przejdź do adresu URL podanego w wierszu polecenia. Na przykład: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. W przeglądarce pojawi się Strona Jupyter. Na karcie **pliki** wybierz pozycję **Nowy** > **Q #** , aby utworzyć Notes Jupyter z jądrem Q #. Dodaj następujący kod do pierwszej komórki notesu:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Zaznacz **komórkę** > **Run Cells** , aby uruchomić Notes. `SayHello` pojawi się wkrótce w danych wyjściowych komórki:

    ![Komórka notesu Jupyter z kodem Q #](~/media/install-guide-jupyter.png)

    W przypadku uruchamiania w notesach Jupyter kod Q # jest kompilowany, a Notes będzie wyprowadzał nazwę znalezionych operacji.

1. W nowej komórce Symuluj wykonywanie na komputerze Quantum dla właśnie utworzonej operacji przy użyciu Magic `%simulate`:

    ![Komórka notesu Jupyter z użyciem symulowania Magic](~/media/install-guide-jupyter-simulate.png)

    Powinien zostać wyświetlony komunikat wydrukowany na ekranie wraz z wynikiem wywołanej operacji (w tym przypadku pustą).

Teraz możesz dodać inne operacje pytań i odpowiedzi, aby kontynuować tworzenie procesów Quantum.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Tworzenie C# projektu w systemie Windows przy użyciu programu Visual Studio

1. Wymagania wstępne

    * [Zestaw Quantum Development Kit dla programu Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)

1. Tworzenie nowej aplikacji w języku Q#

    * Przejdź do pozycji **Plik** -> **Nowy** -> **Projekt**
    * Wpisz `Q#` w polu wyszukiwania
    * Wybierz pozycję **Aplikacja Q#**
    * Wybierz pozycję **Dalej**
    * Wybierz nazwę i lokalizację dla aplikacji
    * Wybierz pozycję **Utwórz**

1. Inspekcja projektu

    Powinny być widoczne dwa utworzone pliki: plik `Driver.cs`, który jest aplikacją hosta języka C#, i plik `Operation.qs`, czyli program języka Q# definiujący prostą operację w celu wydrukowania komunikatu w konsoli.

1. Uruchamianie aplikacji

    * Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**
    * W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.

Teraz możesz kontynuować opracowywanie Quantum przy użyciu programu Visual Studio

> [!NOTE]
> * Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.  

## <a name="create-a-c-project-using-vs-code"></a>Tworzenie C# projektu przy użyciu vs Code

1. Wymagania wstępne

    * [Zestaw Quantum Development Kit dla vs Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)

1. Tworzenie nowego projektu:

    * Przejdź do pozycji **Widok** -> **Paleta poleceń**
    * Wybierz pozycję **Q #: Utwórz nowy projekt**
    * Przejdź do lokalizacji w systemie plików, w której chcesz utworzyć aplikację
    * Po utworzeniu projektu kliknij przycisk **Otwórz nowy projekt**

1. Uruchom aplikację:

    * Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**
    * W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`

Teraz możesz kontynuować tworzenie aplikacji Quantum przy użyciu Visual Studio Code.

> [!NOTE]
> * Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu Visual Studio Code. Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Tworzenie C# projektu przy użyciu narzędzia wiersza polecenia `dotnet`

1. Wymagania wstępne

    * [Zestaw Quantum Development Kit dla wiersza polecenia](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)

1. Tworzenie nowej aplikacji

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. Przechodzenie do nowego katalogu aplikacji

    ```bash
    cd <project name>
    ```

    Powinny zostać wyświetlone dwa utworzone pliki wraz z plikami projektu aplikacji: plik języka Q# (`Operation.qs`) i plik hosta języka C# (`Driver.cs`).

1. Uruchamianie aplikacji

    ```bash
    dotnet run
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe: `Hello quantum world!`

Teraz Kontynuuj programowanie w usłudze Quantum przy użyciu narzędzi wiersza polecenia.

## <a name="whats-next"></a>Co dalej?

Teraz, po utworzeniu projektu w preferowanym środowisku, można kontynuować programowanie w usłudze Quantum.

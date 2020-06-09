---
title: 'Dowiedz się, jak utworzyć projekt Q # przy użyciu zestawu Quantum Development Kit (QDK)'
description: 'Zainicjuj projekt dla rozwoju Quantum przy użyciu QDK i Q # w wybranym środowisku programistycznym'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8af8e3288aab731520ede984d5f89644de292385
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578215"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Tworzenie projektu Q # w środowisku deweloperskim

Dowiedz się, jak utworzyć projekt Q # z QDK.

Projekt Q # zawiera pliki Q # zawierające kod Quantum oraz program hosta służący do uruchamiania programu Quantum. Program hosta można napisać w językach .NET, takich jak C#, lub w języku Python. Możesz również uruchomić kod Q # w Jupyter Notebook przy użyciu jądra IQ #.

Wybierz środowisko deweloperskie i język w poniższych sekcjach:

* [Python](#create-a-python-project)
* [Notesy programu Jupyter dla języka Q#](#create-a-q-jupyter-notebook-project)
* [C# z programem Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C# z VS Code](#create-a-c-project-using-vs-code)
* [C# z wierszem polecenia](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Tworzenie projektu w języku Python

1. Wymagania wstępne

     * Instalowanie [zestawu Quantum Development Kit dla języka Python](xref:microsoft.quantum.install.python)

1. Utwórz folder dla projektu i przejdź do tego folderu

1. Utwórz plik Q # o nazwie `Operation.qs` i Dodaj do niego kod q. Przykład:

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

1. Utwórz plik hosta języka Python o nazwie `host.py` , aby wywołać operację Q #. Przykład:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Uruchom program:

    ```
    python host.py
    ```

1. Sprawdź dane wyjściowe. Program powinien zwrócić następujące wiersze:

    ```
    Hello from quantum world!
    0
    ```

Teraz można kontynuować opracowywanie programu Quantum.

## <a name="create-a-q-jupyter-notebook-project"></a>Utwórz projekt Q # Jupyter Notebook

1. Wymagania wstępne

    * Instalowanie [zestawu Quantum Development Kit dla notesów Jupyter](xref:microsoft.quantum.install.jupyter)

1. Uruchom następujące polecenie, aby uruchomić serwer notesów:

    ```
    jupyter notebook
    ```

1. Przejdź do adresu URL podanego w wierszu polecenia. Na przykład: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]

1. W przeglądarce pojawi się Strona Jupyter. Na karcie **pliki** wybierz pozycję **Nowy**  >  **Q #** , aby utworzyć Jupyter Notebook przy użyciu jądra Q #. Dodaj następujący kod do pierwszej komórki notesu:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Wybierz **komórki**  >  **Run Cells** , aby uruchomić Notes. `SayHello`pojawi się wkrótce w danych wyjściowych komórki:

    ![Jupyter Notebook komórki z kodem Q #](~/media/install-guide-jupyter.png)

    W przypadku uruchamiania w notesach Jupyter kod Q # jest kompilowany, a Notes będzie wyprowadzał nazwę znalezionych operacji.

1. W nowej komórce zasymuluj wykonywanie na komputerze kwantowym właśnie utworzonej operacji przy użyciu polecenia magic `%simulate`:

    ![Jupyter Notebook komórki z użyciem symulowania Magic](~/media/install-guide-jupyter-simulate.png)

    Na ekranie powinien zostać wyświetlony komunikat oraz wynik wywołanej operacji (w tym przypadku pusty).

Teraz możesz dodać inne operacje pytań i odpowiedzi, aby kontynuować tworzenie procesów Quantum.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Tworzenie projektu C# w systemie Windows przy użyciu programu Visual Studio

1. Wymagania wstępne

    * Zainstaluj [rozszerzenie Quantum Development Kit dla programu Visual Studio](xref:microsoft.quantum.install.cs)

1. Tworzenie nowej aplikacji w języku Q#

    * Przejdź do **pliku**  ->  **Nowy**  ->  **projekt**
    * Wpisz `Q#` w polu wyszukiwania
    * Wybierz pozycję **Aplikacja Q#**
    * Wybierz pozycję **dalej**
    * Wybierz nazwę i lokalizację dla aplikacji
    * Wybierz pozycję **Utwórz**

1. Inspekcja projektu

    Powinny być widoczne dwa utworzone pliki: plik `Driver.cs`, który jest aplikacją hosta języka C#, i plik `Operation.qs`, czyli program języka Q# definiujący prostą operację w celu wydrukowania komunikatu w konsoli.

1. Uruchamianie aplikacji

    * Wybierz pozycję **Debuguj**  ->  **Uruchom bez debugowania**
    * W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.

Teraz możesz kontynuować opracowywanie Quantum przy użyciu programu Visual Studio

> [!NOTE]
> * Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.  

## <a name="create-a-c-project-using-vs-code"></a>Tworzenie projektu C# przy użyciu VS Code

1. Wymagania wstępne

    * Zainstaluj [rozszerzenie Quantum Development Kit dla vs Code](xref:microsoft.quantum.install.cs)

1. Tworzenie nowego projektu:

    * Przejdź do **widoku**—  ->  **paleta poleceń**
    * Wybierz pozycję **Q #: Utwórz nowy projekt**
    * Wybierz **autonomiczną aplikację konsolową**
    * Przejdź do lokalizacji w systemie plików, w której chcesz utworzyć aplikację
    * Po utworzeniu projektu kliknij przycisk **Otwórz nowy projekt**

1. Uruchom aplikację:

    * Przejdź do **terminalu**  ->  **Nowy terminal**
    * Wprowadź wartość `dotnet run`
    * W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`

Teraz możesz kontynuować tworzenie aplikacji Quantum przy użyciu Visual Studio Code.

> [!NOTE]
> * Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu Visual Studio Code. Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Tworzenie projektu C# przy użyciu `dotnet` narzędzia wiersza polecenia

1. Wymagania wstępne

    * Instalowanie [zestawu Quantum Development Kit dla wiersza polecenia](xref:microsoft.quantum.install.standalone)

1. Tworzenie nowej aplikacji

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. Przechodzenie do nowego katalogu aplikacji

    ```
    cd <project name>
    ```

    Powinny zostać wyświetlone dwa utworzone pliki wraz z plikami projektu aplikacji: plik języka Q# (`Operation.qs`) i plik hosta języka C# (`Driver.cs`).

1. Uruchamianie aplikacji

    ```dotnetcli
    dotnet run
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe: `Hello quantum world!`

Teraz Kontynuuj programowanie w usłudze Quantum przy użyciu narzędzi wiersza polecenia.

## <a name="next-steps"></a>Następne kroki

Teraz, po utworzeniu projektu w preferowanym środowisku, można kontynuować programowanie w usłudze Quantum.

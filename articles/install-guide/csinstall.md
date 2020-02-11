---
title: 'Programowanie przy użyciu narzędzia Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 7803846279f230f5fc0ee8424bd39be735a650ca
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036291"
---
# <a name="develop-with-q--c"></a>Programowanie przy użyciu narzędzia Q # +C#

Zainstaluj program QDK, aby C# opracowywać programy hosta do wywoływania operacji Q #.

Program Q # jest zbudowany w celu pomyślnego C#odtwarzania z językami .NET — w tym celu. Możesz współpracować z tym parowaniem w różnych środowiskach deweloperskich:

- [Q # + C# przy użyciu programu Visual Studio (Windows)](#VS)
- [Q # + C# używa Visual Studio Code (Windows, Linux i Mac)](#VSC)
- [Q # + C# przy użyciu narzędzia wiersza polecenia `dotnet`](#command)

## Programowanie przy użyciu narzędzia Q C# # + w programie Visual Studio <a name="VS"></a>

Program Visual Studio oferuje bogate środowisko do opracowywania programów pytań i odpowiedzi. Rozszerzenie Q # programu Visual Studio zawiera szablony dla plików i projektów Q #, a także wyróżnianie składni, uzupełnianie kodu i obsługa technologii IntelliSense.


1. Wymagania wstępne

    - Program [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 z włączonym obciążeniem programu .NET Core obsługującym projektowanie dla wielu platform

1. Instalowanie rozszerzenia programu Visual Studio dla języka Q#

    - Pobierz i zainstaluj [rozszerzenie programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)

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

## Programowanie przy użyciu funkcji Q C# # + Visual Studio Code <a name="VSC"></a>

Visual Studio Code (VS Code) oferuje bogate środowisko do opracowywania programów Q # w systemach Windows, Linux i Mac.  Rozszerzenie Q # VS Code obejmuje obsługę wyróżniania składni Q #, uzupełniania kodu i fragmentów kodu pytań i odpowiedzi.

1. Wymagania wstępne

   - [VS Code](https://code.visualstudio.com/download)
   - [Zestaw .NET Core SDK 3,1 lub nowszy](https://www.microsoft.com/net/download)

1. Instalowanie rozszerzenia programu VS Code dla obliczeń kwantowych

    - Zainstaluj [rozszerzenie programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Instalowanie szablonów projektów kwantowych:

   - Przejdź do pozycji **Widok** -> **Paleta poleceń**
   - Wybierz pozycję **Q #: Instalowanie szablonów projektu**

    Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Tworzenie nowego projektu:

        - Przejdź do pozycji **Widok** -> **Paleta poleceń**
        - Wybierz pozycję **Q #: Utwórz nowy projekt**
        - Wybierz **autonomiczną aplikację konsolową**
        - Przejdź do lokalizacji w systemie plików, w której chcesz utworzyć aplikację
        - Po utworzeniu projektu kliknij przycisk **Otwórz nowy projekt**

    - Jeśli nie masz jeszcze C# rozszerzenia vs Code, zostanie wyświetlone okno podręczne. Zainstaluj rozszerzenie. 

    - Uruchom aplikację:

        - Przejdź do **terminalu** -> **nowym terminalu**
        - Wprowadź `dotnet run`
        - W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`


> [!NOTE]
> * Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu Visual Studio Code. Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.

## Programowanie przy użyciu funkcji Q C# # + za pomocą narzędzia wiersza polecenia `dotnet` <a name="command"></a>

Oczywiście programy Q# możesz kompilować i uruchamiać z poziomu wiersza polecenia, po prostu instalując zestaw SDK .NET Core i szablony projektów QDK. 

1. Wymagania wstępne

    - [Zestaw .NET Core SDK 3,1 lub nowszy](https://www.microsoft.com/net/download)

1. Instalowanie szablonów projektów kwantowych dla platformy .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Tworzenie nowej aplikacji

       ```dotnetcli
       dotnet new console -lang "Q#" -o runSayHello
       ```

    - Przechodzenie do nowego katalogu aplikacji

       ```bash
       cd runSayHello
       ```

    Powinny zostać wyświetlone dwa utworzone pliki wraz z plikami projektu aplikacji: plik języka Q# (`Operation.qs`) i plik hosta języka C# (`Driver.cs`).

    - Uruchamianie aplikacji

        ```dotnetcli
        dotnet run
        ```

        Powinny zostać wyświetlone następujące dane wyjściowe: `Hello quantum world!`

    
## <a name="whats-next"></a>Co dalej?

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.write-program).

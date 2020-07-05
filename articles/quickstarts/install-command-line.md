---
title: Tworzenie aplikacji wiersza polecenia w języku Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884280"
---
# <a name="develop-with-q-command-line-applications"></a>Tworzenie aplikacji wiersza polecenia w języku Q#

Programy w języku Q# można wykonywać samodzielnie, bez sterownika w języku hosta, takim jak C#, F#, czy Python.

## <a name="prerequisites"></a>Wymagania wstępne

- [Zestaw .NET Core SDK 3.1 lub nowszy](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalacja

Chociaż aplikacje wiersza polecenia w języku Q# można tworzyć w dowolnym środowisku IDE, zalecamy korzystanie z programu Visual Studio Code (VS Code) lub Visual Studio jako środowiska IDE dla aplikacji języka Q#. Programowanie w tych środowiskach obejmuje bogate funkcje rozszerzenia QDK, takie jak ostrzeżenia, wyróżnianie składni, szablony projektów i wiele innych.

Aby skonfigurować program VS Code:

1. Pobierz i zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac).
2. Zainstaluj [zestaw Microsoft QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Aby skonfigurować program Visual Studio:

1. Pobierz i zainstaluj program [Visual Studio](https://visualstudio.microsoft.com/downloads/) w wersji 16.3 lub nowszej z włączonym pakietem roboczym Tworzenie aplikacji dla wielu platform w środowisku .NET Core.
2. Pobierz i zainstaluj [zestaw Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

Aby zainstalować zestaw QDK dla innego środowiska, wprowadź w wierszu polecenia:

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a>Programowanie przy użyciu języka Q#

Postępuj zgodnie z instrukcjami na karcie odpowiadającej Twojemu środowisku.

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

Zainstaluj szablony projektów języka Q#:

1. Otwórz program VS Code.
2. Przejdź do pozycji **View** -> **Command Palette** (Widok > Paleta poleceń).
3. Wybierz pozycję **Q#: Install project templates** (Q#: zainstaluj szablony projektów).

Po wyświetleniu komunikatu **Project templates installed successfully** (Pomyślnie zainstalowano szablony projektów) zestaw QDK jest gotowy do użycia z Twoimi aplikacjami i bibliotekami.

Aby utworzyć nowy projekt:

1. Kliknij pozycję **View** -> **Command Palette**, a następnie wybierz polecenie **Q#: Create New Project** (Q#: utwórz nowy projekt).
2. Kliknij pozycję **Standalone console application** (Autonomiczna aplikacja konsolowa).
3. Przejdź do lokalizacji, w której chcesz zapisać projekt, a następnie kliknij pozycję **Create project** (Utwórz projekt).
4. Po pomyślnym utworzeniu projektu kliknij pozycję **Open new project...** (Otwórz nowy projekt) w prawym dolnym rogu.
        
Zapoznaj się z projektem. Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.

Aby uruchomić aplikację:
1. Kliknij pozycję **Terminal** -> **New Terminal** (Nowy terminal).
2. W wierszu polecenia terminalu wprowadź polecenie `dotnet run`.
3. W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`


> [!NOTE]
> Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu VS Code dla języka Q#. Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.

### <a name="visual-studio"></a>[Program Visual Studio](#tab/tabid-vs)

Zweryfikuj instalację programu Visual Studio, tworząc aplikację `Hello World` w języku Q#.

Aby utworzyć nową aplikację w języku Q#:
1. Otwórz program Visual Studio, a następnie wybierz kolejno opcje **Plik** -> **Nowy** -> **Projekt**.
2. Wpisz `Q#` w polu wyszukiwania, wybierz pozycję **Aplikacja Q#** , a następnie kliknij pozycję **Dalej**.
3. Wprowadź nazwę i lokalizację aplikacji, a następnie kliknij pozycję **Utwórz**.


Zapoznaj się z projektem. Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.

Aby uruchomić aplikację:
1. Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**.
2. W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.

> [!NOTE]
> Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.  

### <a name="other-editors-with-the-command-line"></a>[Inne edytory z wierszem polecenia](#tab/tabid-cmdline)

Zweryfikuj instalację, tworząc aplikację `Hello World` w języku Q#.

1. Tworzenie nowej aplikacji:
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. Przechodzenie do katalogu aplikacji:
    ```dotnetcli
    cd runSayHello
    ```

    Ten katalog powinien teraz zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli. Ten szablon można zmodyfikować za pomocą edytora tekstów i zastąpić go własnymi aplikacjami kwantowymi. 

3. Uruchom program:
    ```dotnetcli
    dotnet run
    ```

4. Powinien zostać wyświetlony następujący tekst: `Hello quantum world!`

***

## <a name="next-steps"></a>Następne kroki

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).

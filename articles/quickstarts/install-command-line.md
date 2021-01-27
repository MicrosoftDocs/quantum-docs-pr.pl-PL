---
title: Tworzenie aplikacji w języku Q# w środowisku IDE
description: Dowiedz się, jak utworzyć aplikację Q# uruchamianą z wiersza polecenia.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e4f1e97477ecb0547b1586b1c7603c8a9954584
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844316"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a>Tworzenie aplikacji w języku Q# w środowisku IDE

Programy w języku Q# można uruchamiać samodzielnie, bez sterownika w języku hosta, takim jak C#, F# czy Python. Aplikacje w języku Q# możesz opracowywać w programie Visual Studio Code (VS Code), programie Visual Studio, usłudze Visual Studio Codespaces lub dowolnym edytorze / środowisku IDE, a następnie uruchamiać je z poziomu konsoli .NET. 

## <a name="prerequisites-for-all-environments"></a>Wymagania wstępne dla wszystkich środowisk

- [Zestaw .NET Core SDK 3.1 lub nowszy](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalacja

Chociaż aplikacje w języku Q# można tworzyć w dowolnym środowisku IDE, zalecamy korzystanie z programu Visual Studio Code (VS Code) lub Visual Studio jako środowiska IDE do lokalnego programowania aplikacji w języku Q#. W przypadku programowania w chmurze za pośrednictwem przeglądarki internetowej zalecamy używanie programu Visual Studio Codespaces. Programowanie w tych środowiskach umożliwia wykorzystanie bogatych funkcji rozszerzenia QDK, takich jak ostrzeżenia, wyróżnianie składni, szablony projektów i wiele innych. 

### <a name="to-configure-for-vs-code"></a>Aby skonfigurować na potrzeby programu VS Code:

1. Pobierz i zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac).
2. Zainstaluj [zestaw Microsoft QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

### <a name="to-configure-for-visual-studio"></a>Aby skonfigurować na potrzeby programu Visual Studio:

1. Pobierz i zainstaluj program [Visual Studio](https://visualstudio.microsoft.com/downloads/) w wersji 16.3 lub nowszej z włączonym pakietem roboczym Tworzenie aplikacji dla wielu platform w środowisku .NET Core.
2. Pobierz i zainstaluj [zestaw Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

### <a name="to-configure-for-another-environment"></a>Aby skonfigurować na potrzeby innego środowiska: 

1. Wprowadź następujące polecenie w wierszu polecenia

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a>Aby skonfigurować na potrzeby usługi Visual Studio Codespaces:

1. Utwórz [konto platformy Azure](https://azure.microsoft.com/free/).
2. Utwórz środowisko programu Codespaces. Postępuj zgodnie z [przewodnikiem Szybki start](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser). Podczas tworzenia środowiska Codespace zalecamy wprowadzenie wartości `microsoft/Quantum` w polu „Git Repository” (Repozytorium Git) w celu załadowania ustawień specyficznych dla zestawu QDK.
3. Teraz możesz uruchomić nowe środowisko i rozpocząć programowanie w przeglądarce za pomocą [środowiska IDE programu VS Codespaces w chmurze](https://online.visualstudio.com/environments). Alternatywnie można korzystać z lokalnej instalacji programu VS Code i używać Codespaces jako [środowiska zdalnego](https://docs.microsoft.com/visualstudio/online/how-to/vscode).

## <a name="develop-with-no-locq"></a>Programowanie przy użyciu języka Q#

Postępuj zgodnie z instrukcjami na karcie odpowiadającej Twojemu środowisku programistycznemu.

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

Aby utworzyć nowy projekt:

1. Kliknij pozycję **View** -> **Command Palette** (Widok -> Paleta poleceń), a następnie wybierz polecenie **Q#: Create New Project** (Q#: utwórz nowy projekt).
2. Kliknij pozycję **Standalone console application** (Autonomiczna aplikacja konsolowa).
3. Przejdź do lokalizacji, w której ma zostać zapisany projekt. Wpisz nową nazwę projektu i kliknij pozycję **Create project** (Utwórz projekt).
4. Po pomyślnym utworzeniu projektu kliknij pozycję **Open new project...** (Otwórz nowy projekt) w prawym dolnym rogu.

Zapoznaj się z projektem. Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.

Aby uruchomić aplikację:

1. Kliknij pozycję **Terminal** -> **New Terminal** (Nowy terminal).
2. W wierszu polecenia terminalu wprowadź polecenie `dotnet run`.
3. W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`

> [!NOTE]
> Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu VS Code dla języka Q#. Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.

### <a name="visual-studio"></a>[Program Visual Studio](#tab/tabid-vs)

Zweryfikuj instalację programu Visual Studio, tworząc aplikację Q# w języku `Hello World`.

Aby utworzyć nową aplikację w języku Q#:

1. Otwórz program Visual Studio, a następnie wybierz kolejno opcje **Plik** -> **Nowy** -> **Projekt**.
2. Wpisz `Q#` w polu wyszukiwania, wybierz pozycję **Aplikacja Q#** , a następnie kliknij przycisk **Dalej**.
3. Wprowadź nazwę i lokalizację aplikacji, a następnie kliknij pozycję **Utwórz**.


Zapoznaj się z projektem. Powinien zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli.

Aby uruchomić aplikację:

1. Wybierz kolejno pozycje **Debuguj** -> **Uruchom bez debugowania**.
2. W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.

> [!NOTE]
> Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.  

### <a name="other-editors-with-the-command-prompt"></a>[Inne edytory przy użyciu wiersza polecenia](#tab/tabid-cmdline)

Zweryfikuj instalację, tworząc aplikację `Hello World` w języku Q#.

1. Tworzenie nowej aplikacji:

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. Przechodzenie do katalogu aplikacji:

    ```dotnetcli
    cd runSayHello
    ```

    Ten katalog powinien teraz zawierać plik źródłowy o nazwie `Program.qs`, czyli program języka Q#, w którym zdefiniowano prostą operację drukowania komunikatu w konsoli. Ten szablon można zmodyfikować za pomocą edytora tekstów i zastąpić go własnymi aplikacjami kwantowymi. 

1. Uruchom program:

    ```dotnetcli
    dotnet run
    ```

1. Powinien zostać wyświetlony następujący tekst: `Hello quantum world!`

***

## <a name="next-steps"></a>Następne kroki

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).

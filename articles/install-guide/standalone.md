---
title: 'Opracowywanie aplikacji z wiersza polecenia Q #'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426434"
---
# <a name="develop-with-q-command-line-applications"></a>Opracowywanie aplikacji z wiersza polecenia Q #

Programy Q # można wykonać samodzielnie, bez sterownika w języku hosta, takim jak C#, F # lub Python.

## <a name="pre-requisites"></a>Wymagania wstępne

- [Zestaw .NET Core SDK 3,1 lub nowszy](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalacja

Podczas tworzenia aplikacji wiersza polecenia Q # w dowolnym środowisku IDE zalecamy używanie Visual Studio Code (VS Code) lub środowiska IDE programu Visual Studio dla aplikacji Q #. Programowanie w tych narzędziach zapewnia dostęp do rozbudowanych funkcji.

Aby skonfigurować VS Code:

1. Pobierz i zainstaluj [vs Code](https://code.visualstudio.com/download) (Windows, Linux i Mac).
2. Zainstaluj [program Microsoft QDK dla vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Aby skonfigurować program Visual Studio:

1. Pobierz i zainstaluj [program Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 lub nowszy z włączonym obciążeniem programistycznym dla wielu platform platformy .NET Core.
2. Pobierz i zainstaluj [program Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Programowanie przy użyciu narzędzia Q # VS Code

Zainstaluj szablony projektu Q #:

1. Otwórz VS Code.
2. Kliknij pozycję **Widok**  ->  **paleta poleceń**.
3. Wybierz pozycję **Q #: Instalowanie szablonów projektu**.

Po **pomyślnym wyświetleniu szablonu projektu** QDK jest gotowy do użycia z własnymi aplikacjami i bibliotekami.

Aby utworzyć nowy projekt:

1. Kliknij pozycję **Wyświetl**  ->  **paletę poleceń** i wybierz pozycję **Q #: Utwórz nowy projekt**.
2. Kliknij **autonomiczną aplikację konsolową**.
3. Przejdź do lokalizacji, w której chcesz zapisać projekt, a następnie kliknij pozycję **Utwórz projekt**.
4. Po pomyślnym utworzeniu projektu kliknij pozycję **Otwórz nowy projekt..** . w prawym dolnym rogu.
        
Zbadaj projekt. Powinien zostać wyświetlony plik źródłowy o nazwie `Program.qs` , który jest programem Q #, który definiuje prostą operację do drukowania komunikatu w konsoli programu.

Aby uruchomić aplikację:
1. Kliknij pozycję **Terminal**  ->  **Nowy terminal**.
2. W wierszu polecenia terminalu wprowadź `dotnet run` .
3. W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`


> [!NOTE]
> Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie VS Code Q #. Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.

## <a name="develop-with-q-using-visual-studio"></a>Programowanie za pomocą narzędzia Q # przy użyciu programu Visual Studio

Zweryfikuj instalację programu Visual Studio, tworząc aplikację Q # `Hello World` .

Aby utworzyć nową aplikację Q #:
1. Otwórz program Visual Studio, a następnie kliknij pozycję **plik**  ->  **Nowy**  ->  **projekt**.
2. Wpisz `Q#` w polu wyszukiwania, wybierz pozycję **Q # aplikacja** i kliknij **przycisk Dalej**.
3. Wprowadź nazwę i lokalizację aplikacji, a następnie kliknij przycisk **Utwórz**.


Zbadaj projekt. Powinien zostać wyświetlony plik źródłowy o nazwie `Program.qs` , który jest programem Q #, który definiuje prostą operację do drukowania komunikatu w konsoli programu.

Aby uruchomić aplikację:
1. Wybierz pozycję **Debuguj**  ->  **Uruchom bez debugowania**.
2. W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.

> [!NOTE]
> Jeśli masz wiele projektów w ramach jednego rozwiązania programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.  


## <a name="next-steps"></a>Następne kroki

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).

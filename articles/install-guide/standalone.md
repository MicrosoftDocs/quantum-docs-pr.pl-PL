---
title: 'Wykonaj programy Q # bez sterownika i języka hosta'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706805"
---
# <a name="q-command-line-applications"></a>Aplikacje wiersza polecenia Q #

Programy Q # można wykonać samodzielnie, bez sterownika w języku hosta, takim jak C#, F # lub Python.

## <a name="pre-requisites"></a>Wymagania wstępne

- [Zestaw .NET Core SDK 3,1 lub nowszy](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalacja

Podczas tworzenia aplikacji wiersza polecenia Q # w dowolnym środowisku IDE zdecydowanie zalecamy używanie Visual Studio Code (VS Code) lub środowiska IDE programu Visual Studio dla aplikacji Q #. Za pomocą VS Code lub programu Visual Studio oraz rozszerzenia QDK Visual Studio Code uzyskujesz dostęp do bogatszej funkcjonalności.

- Zainstaluj [vs Code](https://code.visualstudio.com/download) (systemy Windows, Linux i Mac)
- Zainstaluj [rozszerzenie QDK dla vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) lub
- Program [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 z włączonym obciążeniem programu .NET Core obsługującym projektowanie dla wielu platform
- Pobierz i zainstaluj [rozszerzenie programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)


## <a name="develop-with-q-using-vs-code"></a>Programowanie przy użyciu narzędzia Q # VS Code

Instalowanie szablonów projektów kwantowych:

- Przejdź do **widoku** -> —**paleta poleceń**
- Wybierz pozycję **Q #: Instalowanie szablonów projektu**

Zestaw Quantum Development Kit jest teraz zainstalowany i gotowy do użycia w Twoich własnych aplikacjach i bibliotekach.
- Tworzenie nowego projektu:
  - Przejdź do **widoku** -> —**paleta poleceń**
  - Wybierz pozycję **Q #: Utwórz nowy projekt**
  - Wybierz **autonomiczną aplikację konsolową**
  - Przejdź do lokalizacji w systemie plików, w której chcesz utworzyć aplikację
  - Po utworzeniu projektu kliknij przycisk **Otwórz nowy projekt**
        
- Inspekcja projektu
  - Powinien zostać wyświetlony plik o nazwie `Program.qs` utworzony, który jest programem Q #, który definiuje prostą operację do drukowania komunikatu w konsoli programu.

- Uruchom aplikację:
  - Przejdź do **terminalu** -> **Nowy terminal**
  - Wprowadź wartość `dotnet run`
  - W oknie danych wyjściowych powinien zostać wyświetlony następujący tekst: `Hello quantum world!`


> [!NOTE]
> * Obszary robocze z wieloma folderami głównymi nie są obecnie obsługiwane przez rozszerzenie programu Visual Studio Code. Jeśli masz wiele projektów w jednym obszarze roboczym programu VS Code, wszystkie projekty muszą znajdować się w tym samym folderze głównym.

## <a name="develop-with-q-using-visual-studio"></a>Programowanie za pomocą narzędzia Q # przy użyciu programu Visual Studio

Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

- Tworzenie nowej aplikacji w języku Q#
  - Przejdź do **pliku** -> **Nowy** -> **projekt**
  - Wpisz `Q#` w polu wyszukiwania
  - Wybierz pozycję **Aplikacja Q#**
  - Wybierz pozycję **dalej**
  - Wybierz nazwę i lokalizację dla aplikacji
  - Wybierz pozycję **Utwórz**

- Inspekcja projektu
  - Powinieneś zobaczyć, że plik o `Program.qs` nazwie został utworzony, który jest programem Q #, który definiuje prostą operację do drukowania komunikatu w konsoli programu.

- Uruchamianie aplikacji
  - Wybierz pozycję **Debuguj** -> **Uruchom bez debugowania**
  - W oknie konsoli powinien zostać wypisany tekst `Hello quantum world!`.

> [!NOTE]
> * Jeśli masz wiele projektów w jednym rozwiązaniu programu Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.  


## <a name="whats-next"></a>Co dalej?

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.write-program).

---
title: Dowiedz się, jak aktualizować Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463286"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizowanie Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zaktualizować Microsoft Quantum Development Kit (QDK) do najnowszej wersji.

W tym artykule przyjęto założenie, że zainstalowano już QDK. Jeśli instalujesz po raz pierwszy, zapoznaj się z [Podręcznikiem instalacji](xref:microsoft.quantum.install).


## <a name="updating-q-projects"></a>Aktualizowanie projektów Q # 

1. Najpierw zainstaluj najnowszą wersję [zestaw .NET Core SDK 3,0](https://dotnet.microsoft.com/download) , a następnie uruchom następujące polecenie w wierszu polecenia:
```bash
dotnet --version
```
 Sprawdź, czy dane wyjściowe mają wartość 3.0.100 lub wyższą, a następnie postępuj zgodnie z poniższymi instrukcjami, w zależności od konfiguracji.

### <a name="in-visual-studio"></a>W programie Visual Studio
 
 1. Aktualizacja do najnowszej wersji programu Visual Studio 2019, zobacz [tutaj](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) , aby uzyskać instrukcje
 2. Otwórz rozwiązanie w programie Visual Studio
 3. Z menu wybierz opcję Kompiluj > Wyczyść rozwiązanie 
 4. [Zaktualizuj platformę docelową](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) w każdym z plików. csproj na netcoreapp 3.0 (lub Standard 2.1, jeśli jest to projekt biblioteki)
 5. Zapisz i Zamknij wszystkie pliki w rozwiązaniu
 6. Wybierz Narzędzia > > wiersza polecenia wiersz polecenia dla deweloperów
 7. Dla każdego projektu w rozwiązaniu Uruchom następujące polecenie:
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
Jeśli Twoje projekty korzystają z innych pakietów Microsoft. Quantum, uruchom polecenie również. 
 8. Zamknij wiersz polecenia i wybierz opcję Kompiluj > Kompiluj rozwiązanie ( *nie* wybieraj opcji Skompiluj ponownie rozwiązanie, ponieważ ponowne kompilowanie zakończy się niepowodzeniem)

### <a name="in-visual-studio-code"></a>W Visual Studio Code

1. W Visual Studio Code Otwórz folder zawierający projekt do zaktualizowania
1. Wybierz pozycję Terminal > nowym terminalu
1. Postępuj zgodnie z instrukcjami dotyczącymi aktualizowania przy użyciu wiersza polecenia

### <a name="using-the-command-line"></a>Korzystanie z wiersza polecenia

1. Przejdź do folderu zawierającego plik projektu
2. Uruchom następujące polecenie:
```bash
dotnet clean [project_name].csproj
```

3. [Zaktualizuj platformę docelową](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) w każdym z plików. csproj na netcoreapp 3.0 (lub Standard 2.1, jeśli jest to projekt biblioteki)
4. Uruchom następujące polecenie:
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
Jeśli projekt używa innych pakietów Microsoft. Quantum, uruchom polecenie również.

5. Zapisz i Zamknij wszystkie pliki
6. Powtórz 1-4 dla każdej zależności projektu, a następnie przejdź z powrotem do folderu zawierającego główny projekt i uruchom:
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>Aktualizacja IQ # dla języka Python

1. Aktualizowanie jądra `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Weryfikowanie wersji `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe:

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. Aktualizowanie pakietu `qsharp`

    ```bash
    pip install qsharp --upgrade
    ```

1. Weryfikowanie wersji `qsharp`

    ```bash
    pip show qsharp
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe:

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. Uruchom następujące polecenie z lokalizacji plików `.qs`
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. Teraz można używać zaktualizowanej wersji QDK do uruchamiania istniejących programów Quantum.

## <a name="update-iq-for-jupyter-notebooks"></a>Aktualizacja IQ # dla notesów Jupyter

1. Aktualizowanie jądra `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Weryfikowanie wersji `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe:

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. Uruchom następujące polecenie w komórce w Jupyter Notebook:
    ```
    %workspace reload
    ```

1. Teraz możesz otworzyć istniejący Notes programu Jupyter i uruchomić go ze zaktualizowanym QDK.

## <a name="update-visual-studio-qdk-extension"></a>Zaktualizuj rozszerzenie Visual Studio QDK

1. Aktualizowanie rozszerzenia Q # programu Visual Studio

    - Program Visual Studio poprosi o zaakceptowanie aktualizacji [rozszerzenia programu Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Zaakceptuj aktualizację

    > [!NOTE]
    > Szablony projektu są aktualizowane przy użyciu rozszerzenia. Zaktualizowane szablony mają zastosowanie tylko do nowo utworzonych projektów. Kod dla istniejących projektów nie jest aktualizowany, gdy rozszerzenie zostanie zaktualizowane.

## <a name="update-vs-code-qdk-extension"></a>Aktualizacja rozszerzenia QDK VS Code

1. Aktualizowanie rozszerzenia Quantum VS Code

    - Uruchom ponownie VS Code
    - Przejdź do karty **rozszerzenia**
    - Wybierz **Microsoft Quantum Development Kit rozszerzenia Visual Studio Code**
    - Załaduj ponownie rozszerzenie

1. Aktualizowanie szablonów projektów Quantum:

   - Przejdź do pozycji **Widok** -> **Paleta poleceń**
   - Wybierz pozycję **Q #: Instalowanie szablonów projektu**

## <a name="c-using-the-dotnet-command-line-tool"></a>C#przy użyciu narzędzia wiersza polecenia `dotnet`

1. Aktualizowanie szablonów projektów Quantum dla platformy .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>Co dalej?

Teraz, po zaktualizowaniu zestawu Quantum Development Kit w preferowanym środowisku, można nadal opracowywać i uruchamiać programy Quantum. Jeśli nie zapisano jeszcze programu, możesz rozpocząć pracę z [pierwszym programem Quantum](xref:microsoft.quantum.write-program).

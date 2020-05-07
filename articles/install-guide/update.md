---
title: Dowiedz się, jak aktualizować Microsoft Quantum Development Kit (QDK)
description: 'Opisuje, w jaki sposób aktualizować projekty Q # i Microsoft Quantum Development Kit do bieżącej wersji.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: bf6d6d3d80af485b555429f25b125bfea685bebf
ms.sourcegitcommit: c57c271ab73f75f165401651fad2b5bc143e9c8f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/06/2020
ms.locfileid: "82862211"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizowanie Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zaktualizować Microsoft Quantum Development Kit (QDK) do najnowszej wersji.

W tym artykule przyjęto założenie, że zainstalowano już QDK. Jeśli instalujesz po raz pierwszy, zapoznaj się z [Podręcznikiem instalacji](xref:microsoft.quantum.install).

Zalecamy zachowywanie aktualności przy użyciu najnowszej wersji QDK. Postępuj zgodnie z tym przewodnikiem aktualizacji, aby przeprowadzić uaktualnienie do najnowszej wersji programu QDK. Proces składa się z dwóch części:
1. Aktualizowanie istniejących plików i projektów Q # w celu wyrównania kodu przy użyciu dowolnej zaktualizowanej składni
2. Aktualizowanie samej QDK dla wybranego środowiska programistycznego 

## <a name="updating-q-projects"></a>Aktualizowanie projektów Q # 

Bez względu na to, czy używasz języka C# lub Python do hostowania operacji Q #, postępuj zgodnie z tymi instrukcjami, aby zaktualizować projekty Q #.

1. Najpierw sprawdź, czy masz najnowszą wersję [zestaw .NET Core SDK 3,1](https://dotnet.microsoft.com/download). Uruchom następujące polecenie w wierszu polecenia:

    ```dotnetcli
    dotnet --version
    ```

    Sprawdź, czy dane `3.1.100` wyjściowe są lub nowsze. Jeśli nie, zainstaluj [najnowszą wersję](https://dotnet.microsoft.com/download) i sprawdź ponownie. Następnie postępuj zgodnie z poniższymi instrukcjami, w zależności od konfiguracji (Visual Studio, Visual Studio Code lub bezpośrednio w wierszu polecenia).

### <a name="update-q-projects-in-visual-studio"></a>Aktualizuj projekty Q # w programie Visual Studio
 
1. Aktualizacja do najnowszej wersji programu Visual Studio 2019, zobacz [tutaj](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) , aby uzyskać instrukcje
2. Otwórz rozwiązanie w programie Visual Studio
3. Z menu wybierz opcję **Kompiluj** -> **czyste rozwiązanie**
4. W każdym z plików. csproj zaktualizuj platformę docelową do `netcoreapp3.1` (lub `netstandard2.1` jeśli jest to projekt biblioteki).
    Oznacza to, że edycja wierszy formularza:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Więcej szczegółowych informacji na temat określania platform docelowych można znaleźć [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
5. Zapisz i Zamknij wszystkie pliki w rozwiązaniu
6. Wybieranie **narzędzi** -> **wiersza** -> polecenia**wiersz polecenia dla deweloperów**
7. Dla każdego projektu w rozwiązaniu Uruchom następujące polecenie:

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Jeśli projekty korzystają z innych pakietów Microsoft. Quantum (np. Microsoft. Quantum. Numerics), uruchom polecenie również dla nich.
8. Zamknij wiersz polecenia i wybierz pozycję **Kompiluj** -> **kompilację rozwiązania** ( *nie* wybieraj opcji Skompiluj ponownie rozwiązanie)

Teraz możesz przejść do [aktualizacji rozszerzenia programu Visual Studio QDK](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Aktualizuj projekty Q # w Visual Studio Code

1. W Visual Studio Code Otwórz folder zawierający projekt do zaktualizowania
2.  -> Wybierz **Terminal****Nowy terminal** terminalu
3. Postępuj zgodnie z instrukcjami dotyczącymi aktualizowania przy użyciu wiersza polecenia (bezpośrednio poniżej)

### <a name="update-q-projects-using-the-command-line"></a>Aktualizowanie projektów Q # przy użyciu wiersza polecenia

1. Przejdź do folderu zawierającego plik projektu
2. Uruchom następujące polecenie:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. W każdym z plików. csproj zaktualizuj platformę docelową do `netcoreapp3.1` (lub `netstandard2.1` jeśli jest to projekt biblioteki).
    Oznacza to, że edycja wierszy formularza:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Więcej szczegółowych informacji na temat określania platform docelowych można znaleźć [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
4. Uruchom następujące polecenie:

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    Jeśli projekt używa innych pakietów Microsoft. Quantum (np. Microsoft. Quantum. Numerics), uruchom polecenie również dla nich.
5. Zapisz i Zamknij wszystkie pliki.
6. Powtórz 1-4 dla każdej zależności projektu, a następnie przejdź z powrotem do folderu zawierającego główny projekt i uruchom:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Gdy projekty Q # zostały zaktualizowane, postępuj zgodnie z poniższymi instrukcjami, aby zaktualizować QDK.

## <a name="updating-the-qdk"></a>Aktualizowanie QDK

Proces aktualizowania QDK różni się w zależności od języka i środowiska deweloperskiego.
Wybierz środowisko deweloperskie poniżej.

* [Python: aktualizowanie rozszerzenia IQ #](#update-iq-for-python)
* [Notesy Jupyter: aktualizowanie rozszerzenia IQ #](#update-iq-for-jupyter-notebooks)
* [Visual Studio: aktualizowanie rozszerzenia QDK](#update-visual-studio-qdk-extension)
* [VS Code: aktualizowanie rozszerzenia QDK](#update-vs-code-qdk-extension)
* [Wiersz polecenia i C#: aktualizowanie szablonów projektu](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Aktualizacja IQ # dla języka Python

1. Aktualizowanie `iqsharp` jądra 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Sprawdź `iqsharp` wersję

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Nie martw się, `iqsharp` Jeśli Twoja wersja jest nowsza, powinna być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).

3. Aktualizowanie `qsharp` pakietu

    ```bash
    pip install qsharp --upgrade
    ```

4. Sprawdź `qsharp` wersję

    ```bash
    pip show qsharp
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe:

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Uruchom następujące polecenie z lokalizacji `.qs` plików

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. Teraz można używać zaktualizowanej wersji QDK do uruchamiania istniejących programów Quantum.

### <a name="update-iq-for-jupyter-notebooks"></a>Aktualizacja IQ # dla notesów Jupyter

1. Aktualizowanie `iqsharp` jądra

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Sprawdź `iqsharp` wersję

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Dane wyjściowe powinny wyglądać podobnie do następujących:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Nie martw się, `iqsharp` Jeśli Twoja wersja jest nowsza, powinna być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).

3. Uruchom następujące polecenie w komórce w Jupyter Notebook:

    ```
    %workspace reload
    ```

4. Teraz możesz otworzyć istniejący Notes programu Jupyter i uruchomić go ze zaktualizowanym QDK.

### <a name="update-visual-studio-qdk-extension"></a>Zaktualizuj rozszerzenie Visual Studio QDK

1. Aktualizowanie rozszerzenia Q # programu Visual Studio

    - Program Visual Studio poprosi o zaakceptowanie aktualizacji [rozszerzenia programu Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Zaakceptuj aktualizację

    > [!NOTE]
    > Szablony projektu są aktualizowane przy użyciu rozszerzenia. Zaktualizowane szablony mają zastosowanie tylko do nowo utworzonych projektów. Kod dla istniejących projektów nie jest aktualizowany, gdy rozszerzenie zostanie zaktualizowane.

### <a name="update-vs-code-qdk-extension"></a>Aktualizacja rozszerzenia QDK VS Code

1. Aktualizowanie rozszerzenia Quantum VS Code

    - Uruchom ponownie VS Code
    - Przejdź do karty **rozszerzenia**
    - Wybierz **Microsoft Quantum Development Kit rozszerzenia Visual Studio Code**
    - Załaduj ponownie rozszerzenie

2. Aktualizowanie szablonów projektów Quantum:

   - Przejdź do **widoku** -> —**paleta poleceń**
   - Wybierz pozycję **Q #: Instalowanie szablonów projektu**
   - Po kilku sekundach powinien zostać wyświetlony podręczny komunikat potwierdzający pomyślne zainstalowanie szablonów projektu.

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, przy użyciu `dotnet` narzędzia wiersza polecenia

1. Aktualizowanie szablonów projektów Quantum dla platformy .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>Co dalej?

Teraz, po zaktualizowaniu zestawu Quantum Development Kit w preferowanym środowisku, można nadal opracowywać i uruchamiać programy Quantum. Jeśli nie zapisano jeszcze programu, możesz rozpocząć pracę z [pierwszym programem Quantum](xref:microsoft.quantum.write-program).

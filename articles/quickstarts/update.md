---
title: Aktualizowanie zestawu Quantum Development Kit (QDK)
description: Tu opisano, jak zaktualizować projekty języka Q# i zestaw Microsoft Quantum Development Kit do bieżącej wersji.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 8d39716c4d4c96ad87862b4b185895aab66cd210
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274140"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizowanie zestawu Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zaktualizować zestaw Microsoft Quantum Development Kit (QDK) do najnowszej wersji.

W tym artykule założono, że masz już zainstalowany zestaw QDK. Jeśli instalujesz go po raz pierwszy, skorzystaj z [przewodnika instalacji](xref:microsoft.quantum.install).

Zalecamy regularne aktualizowanie zestawu QDK do najnowszej wersji. Wykonaj instrukcje z tego przewodnika aktualizacji, aby przejść na najnowszą wersję zestawu QDK. Ten proces składa się z dwóch części:
1. Aktualizowanie istniejących plików i projektów języka Q# w celu dostosowania kodu do zaktualizowanej składni.
2. Aktualizowanie samego zestawu QDK dla wybranego środowiska deweloperskiego.

## <a name="updating-q-projects"></a>Aktualizowanie projektów języka Q# 

Niezależnie od tego, czy hostujesz operacje języka Q# przy użyciu środowiska języka C#, czy Python, postępuj zgodnie z tymi instrukcjami, aby zaktualizować projekty języka Q#.

1. Najpierw sprawdź, czy masz najnowszą wersję [zestawu .NET Core SDK 3.1](https://dotnet.microsoft.com/download). W wierszu polecenia uruchom następujące polecenie:

    ```dotnetcli
    dotnet --version
    ```

    Sprawdź, czy dane wyjściowe zawierają informację o wersji `3.1.100` lub nowszej. Jeśli nie, zainstaluj [najnowszą wersję](https://dotnet.microsoft.com/download) i sprawdź ponownie. Następnie postępuj zgodnie z poniższymi instrukcjami odpowiednio do używanej konfiguracji (w programie Visual Studio, Visual Studio Code lub bezpośrednio w wierszu polecenia).

### <a name="update-q-projects-in-visual-studio"></a>Aktualizowanie projektów języka Q# w programie Visual Studio
 
1. Zaktualizuj program Visual Studio 2019 do najnowszej wersji — instrukcje znajdziesz [tutaj](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).
2. Otwórz rozwiązanie w programie Visual Studio.
3. Z menu wybierz pozycję**Kompilacja** -> **Wyczyść rozwiązanie**.
4. W każdym z plików .csproj zaktualizuj platformę docelową do wersji `netcoreapp3.1` (lub `netstandard2.1`, jeśli jest to projekt biblioteki).
    W tym celu edytuj wiersze w następującym formacie:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Więcej szczegółowych informacji na temat określania platform docelowych znajdziesz [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

5. W każdym z plików .csproj określ zestaw SDK `Microsoft.Quantum.Sdk`, jak pokazano poniżej. Zwróć uwagę, że numer wersji powinien odpowiadać najnowszej dostępnej wersji — aby ją określić, sprawdź [informacje o wersji](https://docs.microsoft.com/quantum/relnotes/).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Zapisz i zamknij wszystkie pliki w rozwiązaniu.

7. Wybierz pozycję **Narzędzia** -> **Wiersz polecenia** -> **Wiersz polecenia dla deweloperów**. Alternatywnie można użyć konsoli zarządzania pakietami w programie Visual Studio.

8. Dla każdego projektu w rozwiązaniu uruchom następujące polecenie, aby **usunąć** ten pakiet:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Jeśli w projektach są używane jakiekolwiek inne pakiety Microsoft.Quantum lub Microsoft.Azure.Quantum (na przykład Microsoft.Quantum.Numerics), uruchom polecenie **add**, aby zaktualizować używaną wersję.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Zamknij wiersz polecenia i wybierz pozycję **Kompilacja** -> **Kompiluj rozwiązanie** (*nie* wybieraj polecenia Kompiluj ponownie rozwiązanie).

Możesz teraz przejść do sekcji [Aktualizowanie rozszerzenia QDK dla programu Visual Studio](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Aktualizowanie projektów języka Q# w programie Visual Studio Code

1. W programie Visual Studio Code otwórz folder zawierający projekt, który chcesz zaktualizować.
2. Wybierz pozycję **Terminal** -> **New Terminal** (Nowy terminal).
3. Postępuj zgodnie z instrukcjami aktualizowania przy użyciu wiersza polecenia (tuż poniżej).

### <a name="update-q-projects-using-the-command-line"></a>Aktualizowanie projektów języka Q# przy użyciu wiersza polecenia

1. Przejdź do folderu zawierającego główny plik projektu.

2. Uruchom następujące polecenie:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Określ bieżącą wersję zestawu QDK. Aby ją znaleźć, możesz sprawdzić [informacje o wersji](https://docs.microsoft.com/quantum/relnotes/). Wersja będzie miała format podobny do następującego: `0.11.2006.207`.

4. W każdym z plików `.csproj` wykonaj następujące czynności:

    - Zaktualizuj platformę docelową do wersji `netcoreapp3.1` (lub `netstandard2.1`, jeśli jest to projekt biblioteki). W tym celu edytuj wiersze w następującym formacie:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Więcej szczegółowych informacji na temat określania platform docelowych znajdziesz [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Zmień odwołanie do zestawu SDK w definicji projektu. Upewnij się, że numer wersji odpowiada wartości określonej w **kroku 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Usuń odwołanie do pakietu `Microsoft.Quantum.Development.Kit`, jeśli jest określone w następującym wpisie:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Zaktualizuj wersje wszystkich pakietów Microsoft Quantum do najnowszej wersji zestawu QDK (określonej w **kroku 3**). Nazwy pakietów odpowiadają następującym wzorcom:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Odwołania do pakietów mają następujący format:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Zapisz zaktualizowany plik.

    - Przywróć zależności projektu, wykonując następujące polecenie:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Wróć do folderu zawierającego główny plik projektu i uruchom następujące polecenie:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Po zaktualizowaniu projektów języka Q# możesz zaktualizować sam zestaw QDK zgodnie z następującymi instrukcjami:

## <a name="updating-the-qdk"></a>Aktualizowanie zestawu QDK

Proces aktualizowania zestawu QDK zależy od używanego języka programowania i środowiska.
Wybierz używane środowisko deweloperskie poniżej.

* [Python: aktualizowanie rozszerzenia IQ#](#update-iq-for-python)
* [Notesy Jupyter Notebook: aktualizowanie rozszerzenia IQ#](#update-iq-for-jupyter-notebooks)
* [Visual Studio: aktualizowanie rozszerzenia QDK](#update-visual-studio-qdk-extension)
* [VS Code: aktualizowanie rozszerzenia QDK](#update-vs-code-qdk-extension)
* [Wiersz polecenia i język C#: aktualizowanie szablonów projektów](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Aktualizowanie rozszerzenia IQ# dla języka Python

1. Zaktualizuj jądro `iqsharp` 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Zweryfikuj wersję jądra `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Jeśli Twoja wersja jądra `iqsharp` jest wyższa, to nie problem — powinna odpowiadać [najnowszej wersji](xref:microsoft.quantum.relnotes).

3. Zaktualizuj pakiet `qsharp`

    ```
    pip install qsharp --upgrade
    ```

4. Zweryfikuj wersję pakietu `qsharp`

    ```
    pip show qsharp
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe:

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Uruchom następujące polecenie z poziomu lokalizacji plików `.qs`

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. Teraz możesz korzystać ze zaktualizowanej wersji pakietu QDK do uruchamiania istniejących programów kwantowych.

### <a name="update-iq-for-jupyter-notebooks"></a>Aktualizowanie rozszerzenia IQ# dla notesów Jupyter Notebook

1. Zaktualizuj jądro `iqsharp`

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Zweryfikuj wersję jądra `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Dane wyjściowe powinny być podobne do następujących:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Jeśli Twoja wersja jądra `iqsharp` jest wyższa, to nie problem — powinna odpowiadać [najnowszej wersji](xref:microsoft.quantum.relnotes).

3. Uruchom następujące polecenie w komórce notesu Jupyter Notebook:

    ```
    %workspace reload
    ```

4. Możesz teraz otworzyć istniejący notes Jupyter i uruchomić go przy użyciu zaktualizowanego zestawu QDK.

### <a name="update-visual-studio-qdk-extension"></a>Aktualizowanie rozszerzenia QDK dla programu Visual Studio

1. Aktualizowanie rozszerzenia programu Visual Studio dla języka Q#

    - W programie Visual Studio zostanie wyświetlony monit o zaakceptowanie aktualizacji [rozszerzenia Quantum dla programu Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Zaakceptuj aktualizację

    > [!NOTE]
    > Szablony projektów zostaną zaktualizowane wraz z rozszerzeniem. Zaktualizowane szablony będą stosowane tylko do nowo tworzonych projektów. Kod istniejących projektów nie jest aktualizowany podczas aktualizacji rozszerzenia.

### <a name="update-vs-code-qdk-extension"></a>Aktualizowanie rozszerzenia QDK dla programu VS Code

1. Aktualizowanie rozszerzenia programu VS Code dla obliczeń kwantowych

    - Uruchom ponownie program VS Code
    - Przejdź do karty **Extensions** (Rozszerzenia)
    - Wybierz rozszerzenie **Microsoft Quantum Development Kit for Visual Studio Code**
    - Załaduj ponownie rozszerzenie

2. Zaktualizuj szablony projektów kwantowych:

   - Przejdź do pozycji **Widok** -> **Paleta poleceń**
   - Wybierz pozycję **Q#: Instalowanie szablonów projektów**
   - Po kilku sekundach powinno zostać wyświetlone okno podręczne z potwierdzeniem: „project templates installed successfully” (pomyślnie zainstalowano szablony projektów).

### <a name="c-using-the-dotnet-command-line-tool"></a>Język C# i narzędzie wiersza polecenia `dotnet`

1. Zaktualizuj szablony projektów kwantowych dla platformy .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

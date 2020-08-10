---
title: Aktualizowanie zestawu Quantum Development Kit (QDK)
description: Tu opisano, jak zaktualizować projekty języka Q# i zestaw Microsoft Quantum Development Kit do bieżącej wersji.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: dd7360961aa728a6aa63b8d8c4e4840f5bf2afe8
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866761"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizowanie zestawu Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zaktualizować zestaw Microsoft Quantum Development Kit (QDK) do najnowszej wersji.

W tym artykule założono, że masz już zainstalowany zestaw QDK. Jeśli instalujesz go po raz pierwszy, skorzystaj z [przewodnika instalacji](xref:microsoft.quantum.install).

Zalecamy regularne aktualizowanie zestawu QDK do najnowszej wersji. Wykonaj instrukcje z tego przewodnika aktualizacji, aby przejść na najnowszą wersję zestawu QDK. Ten proces składa się z dwóch części:
1. Aktualizowanie istniejących plików i projektów języka Q# w celu dostosowania kodu do zaktualizowanej składni.
2. Aktualizowanie samego zestawu QDK dla wybranego środowiska deweloperskiego.

## <a name="updating-no-locq-projects"></a>Aktualizowanie projektów języka Q# 

Niezależnie od tego, czy hostujesz operacje języka Q# przy użyciu środowiska języka C#, czy Python, postępuj zgodnie z tymi instrukcjami, aby zaktualizować projekty języka Q#.

1. Najpierw sprawdź, czy masz najnowszą wersję [zestawu .NET Core SDK 3.1](https://dotnet.microsoft.com/download). W wierszu polecenia uruchom następujące polecenie:

    ```dotnetcli
    dotnet --version
    ```

    Sprawdź, czy dane wyjściowe zawierają informację o wersji `3.1.100` lub nowszej. Jeśli nie, zainstaluj [najnowszą wersję](https://dotnet.microsoft.com/download) i sprawdź ponownie. Następnie postępuj zgodnie z poniższymi instrukcjami odpowiednio do używanej konfiguracji (w programie Visual Studio, Visual Studio Code lub bezpośrednio w wierszu polecenia).

### <a name="update-no-locq-projects-in-visual-studio"></a>Aktualizowanie projektów języka Q# w programie Visual Studio
 
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
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
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


### <a name="update-no-locq-projects-in-visual-studio-code"></a>Aktualizowanie projektów języka Q# w programie Visual Studio Code

1. W programie Visual Studio Code otwórz folder zawierający projekt, który chcesz zaktualizować.
2. Wybierz pozycję **Terminal** -> **New Terminal** (Nowy terminal).
3. Postępuj zgodnie z instrukcjami aktualizowania przy użyciu wiersza polecenia (tuż poniżej).

### <a name="update-no-locq-projects-using-the-command-line"></a>Aktualizowanie projektów języka Q# przy użyciu wiersza polecenia

1. Przejdź do folderu zawierającego główny plik projektu.

2. Uruchom następujące polecenie:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Określ bieżącą wersję zestawu QDK. Aby ją znaleźć, możesz sprawdzić [informacje o wersji](https://docs.microsoft.com/quantum/relnotes/). Wersja będzie miała format podobny do następującego: `0.12.20072031`.

4. W każdym z plików `.csproj` wykonaj następujące czynności:

    - Zaktualizuj platformę docelową do wersji `netcoreapp3.1` (lub `netstandard2.1`, jeśli jest to projekt biblioteki). W tym celu edytuj wiersze w następującym formacie:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Więcej szczegółowych informacji na temat określania platform docelowych znajdziesz [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Zmień odwołanie do zestawu SDK w definicji projektu. Upewnij się, że numer wersji odpowiada wartości określonej w **kroku 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
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
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
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

Po zaktualizowaniu projektów języka Q# możesz zaktualizować sam zestaw QDK zgodnie z poniższymi instrukcjami.

## <a name="updating-the-qdk"></a>Aktualizowanie zestawu QDK

Proces aktualizowania zestawu QDK zależy od używanego języka programowania i środowiska.
Wybierz używane środowisko deweloperskie poniżej.

* [Python: aktualizowanie pakietu `qsharp`](#update-the-qsharp-python-package)
* [Notesy Jupyter Notebook: aktualizowanie jądra IQ#](#update-the-iq-jupyter-kernel)
* [Visual Studio: aktualizowanie rozszerzenia QDK](#update-visual-studio-qdk-extension)
* [VS Code: aktualizowanie rozszerzenia QDK](#update-vs-code-qdk-extension)
* [Wiersz polecenia i język C#: aktualizowanie szablonów projektów](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a>Aktualizowanie pakietu `qsharp` języka Python

Procedura aktualizacji zależy od tego, czy program został pierwotnie zainstalowany przy użyciu środowiska conda, czy przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP.

#### <a name="update-using-conda-recommended"></a>[Aktualizowanie przy użyciu środowiska conda (zalecane)](#tab/tabid-conda)

1. Aktywuj środowisko conda, w którym zainstalowano pakiet `qsharp`, a następnie uruchom to polecenie, aby go zaktualizować:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Uruchom następujące polecenie z poziomu lokalizacji plików `.qs`:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Aktualizowanie przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP (zaawansowane)](#tab/tabid-dotnetcli)

1. Zaktualizuj jądro `iqsharp` 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Zweryfikuj wersję jądra `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe:

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    Nie przejmuj się, jeśli Twoja wersja jądra `iqsharp` jest nowsza. Powinna ona być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).

1. Zaktualizuj pakiet `qsharp`:

    ```
    pip install qsharp --upgrade
    ```

1. Zweryfikuj wersję pakietu `qsharp`:

    ```
    pip show qsharp
    ```

    Powinny zostać wyświetlone następujące dane wyjściowe:

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Uruchom następujące polecenie z poziomu lokalizacji plików `.qs`:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

Teraz możesz korzystać ze zaktualizowanego pakietu `qsharp` języka Python do uruchamiania istniejących programów kwantowych.

### <a name="update-the-ino-locq-jupyter-kernel"></a>Aktualizowanie jądra Jupyter IQ#

Procedura aktualizacji zależy od tego, czy program został pierwotnie zainstalowany przy użyciu środowiska conda, czy przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP.

#### <a name="update-using-conda-recommended"></a>[Aktualizowanie przy użyciu środowiska conda (zalecane)](#tab/tabid-conda)

1. Aktywuj środowisko conda, w którym zainstalowano pakiet `qsharp`, a następnie uruchom to polecenie, aby je zaktualizować:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Uruchom następujące polecenie w komórce w każdym z istniejących notesów Jupyter Notebook języka Q#:

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Aktualizowanie przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP (zaawansowane)](#tab/tabid-dotnetcli)

1. Zaktualizuj pakiet `Microsoft.Quantum.IQSharp`:

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Zweryfikuj wersję pakietu `iqsharp`:

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Dane wyjściowe powinny być podobne do następujących:

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    Nie przejmuj się, jeśli Twoja wersja jądra `iqsharp` jest nowsza. Powinna ona być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).

1. Uruchom następujące polecenie w komórce w każdym z istniejących notesów Jupyter Notebook języka Q#:

    ```
    %workspace reload
    ```

***

Teraz możesz używać zaktualizowanego jądra IQ# do uruchamiania istniejących notesów Jupyter Notebook języka Q#.

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

### <a name="c-using-the-dotnet-command-line-tool"></a>Język C# i narzędzie wiersza polecenia `dotnet`

1. Zaktualizuj szablony projektów kwantowych dla platformy .NET

    Za pomocą wiersza polecenia:

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   Alternatywnie, jeśli zamierzasz używać szablonów wiersza polecenia i masz już zainstalowane rozszerzenie QDK programu VS Code, możesz zaktualizować szablony projektu z poziomu samego rozszerzenia:

   - [Aktualizowanie rozszerzenia QDK](#update-vs-code-qdk-extension)
   - W programie VS Code przejdź do pozycji **View** -> **Command Palette** (Widok, Paleta poleceń).
   - Wybierz pozycję **Q#: Install command line project templates (Q#: zainstaluj szablony projektu wiersza polecenia)**
   - Po kilku sekundach powinno zostać wyświetlone okno podręczne z potwierdzeniem: „project templates installed successfully” (pomyślnie zainstalowano szablony projektów).

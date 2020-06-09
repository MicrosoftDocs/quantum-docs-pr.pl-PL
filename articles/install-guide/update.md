---
title: Aktualizowanie zestawu Quantum Development Kit (QDK)
description: 'Opisuje, w jaki sposób aktualizować projekty Q # i Microsoft Quantum Development Kit do bieżącej wersji.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 89db1a671767b0cc083a251918bbeeed2b39b883
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578185"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizowanie Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zaktualizować Microsoft Quantum Development Kit (QDK) do najnowszej wersji.

W tym artykule przyjęto założenie, że zainstalowano już QDK. Jeśli instalujesz po raz pierwszy, zapoznaj się z [Podręcznikiem instalacji](xref:microsoft.quantum.install).

Zalecamy zachowywanie aktualności przy użyciu najnowszej wersji QDK. Postępuj zgodnie z tym przewodnikiem aktualizacji, aby przeprowadzić uaktualnienie do najnowszej wersji programu QDK. Proces składa się z dwóch części:
1. Aktualizowanie istniejących plików i projektów Q # w celu wyrównania kodu przy użyciu dowolnej zaktualizowanej składni.
2. Aktualizowanie samego QDK dla wybranego środowiska deweloperskiego.

## <a name="updating-q-projects"></a>Aktualizowanie projektów Q # 

Bez względu na to, czy używasz języka C# lub Python do hostowania operacji Q #, postępuj zgodnie z tymi instrukcjami, aby zaktualizować projekty Q #.

1. Najpierw sprawdź, czy masz najnowszą wersję [zestaw .NET Core SDK 3,1](https://dotnet.microsoft.com/download). Uruchom następujące polecenie w wierszu polecenia:

    ```dotnetcli
    dotnet --version
    ```

    Sprawdź, czy dane wyjściowe są `3.1.100` lub nowsze. Jeśli nie, zainstaluj [najnowszą wersję](https://dotnet.microsoft.com/download) i sprawdź ponownie. Następnie postępuj zgodnie z poniższymi instrukcjami, w zależności od konfiguracji (Visual Studio, Visual Studio Code lub bezpośrednio w wierszu polecenia).

### <a name="update-q-projects-in-visual-studio"></a>Aktualizuj projekty Q # w programie Visual Studio
 
1. Zaktualizuj do najnowszej wersji programu Visual Studio 2019, zobacz [tutaj](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) , aby uzyskać instrukcje.
2. Otwórz rozwiązanie w programie Visual Studio.
3. Z menu wybierz opcję **Kompiluj**  ->  **czyste rozwiązanie**.
4. W każdym z plików. csproj zaktualizuj platformę docelową do `netcoreapp3.1` (lub `netstandard2.1` Jeśli jest to projekt biblioteki).
    Oznacza to, że edycja wierszy formularza:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Więcej szczegółowych informacji na temat określania platform docelowych można znaleźć [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

5. W każdym z plików. csproj Ustaw zestaw SDK na `Microsoft.Quantum.Sdk` , jak wskazano w wierszu poniżej. Należy zauważyć, że numer wersji powinien być najnowszy dostępny i można go określić, przeglądając [Informacje o wersji](https://docs.microsoft.com/quantum/relnotes/).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Zapisz i Zamknij wszystkie pliki w rozwiązaniu.

7. Wybierz pozycję **Narzędzia**  ->  **wiersz polecenia**  ->  **wiersz polecenia dla deweloperów**. Alternatywnie można użyć konsoli zarządzania pakietami w programie Visual Studio.

8. Dla każdego projektu w rozwiązaniu Uruchom następujące polecenie, aby **usunąć** ten pakiet:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Jeśli projekty korzystają z innych pakietów Microsoft. Quantum lub Microsoft. Azure. Quantum (np. Microsoft. Quantum. Numerics), uruchom polecenie **Add** , aby zaktualizować używaną wersję.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Zamknij wiersz polecenia i wybierz pozycję **Kompiluj**  ->  **kompilację rozwiązania** ( *nie* wybieraj opcji Skompiluj ponownie rozwiązanie).

Teraz możesz przejść do [aktualizacji rozszerzenia programu Visual Studio QDK](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Aktualizuj projekty Q # w Visual Studio Code

1. W Visual Studio Code Otwórz folder zawierający projekt do zaktualizowania.
2. Wybierz pozycję **Terminal**  ->  **Nowy terminal**.
3. Postępuj zgodnie z instrukcjami dotyczącymi aktualizowania przy użyciu wiersza polecenia (bezpośrednio poniżej).

### <a name="update-q-projects-using-the-command-line"></a>Aktualizowanie projektów Q # przy użyciu wiersza polecenia

1. Przejdź do folderu zawierającego główny plik projektu.

2. Uruchom następujące polecenie:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Ustal bieżącą wersję QDK. Aby go znaleźć, możesz przejrzeć informacje o [wersji](https://docs.microsoft.com/quantum/relnotes/). Wersja będzie wyglądać w formacie podobnym do `0.11.2006.207` .

4. W każdym z `.csproj` plików wykonaj następujące czynności:

    - Zaktualizuj platformę docelową do `netcoreapp3.1` (lub `netstandard2.1` Jeśli jest to projekt biblioteki). Oznacza to, że edycja wierszy formularza:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Więcej szczegółowych informacji na temat określania platform docelowych można znaleźć [tutaj](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Zastąp odwołanie do zestawu SDK w definicji projektu. Upewnij się, że numer wersji odpowiada wartości określonej w **kroku 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Usuń odwołanie do pakietu `Microsoft.Quantum.Development.Kit` , jeśli jest obecny, które zostanie określone w następującym wpisie:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Zaktualizuj wersję wszystkich pakietów Quantum firmy Microsoft do ostatnio wydanej wersji QDK (określonej w **kroku 3**). Te pakiety są nazwane następującymi wzorcami:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        Odwołania do pakietów mają następujący format:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Zapisz zmodyfikowany plik.

    - Przywróć zależności projektu, wykonując następujące czynności:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Przejdź z powrotem do folderu zawierającego główny projekt i uruchom:

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

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Nie martw się, jeśli Twoja `iqsharp` wersja jest nowsza, powinna być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).

3. Aktualizowanie `qsharp` pakietu

    ```
    pip install qsharp --upgrade
    ```

4. Sprawdź `qsharp` wersję

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

5. Uruchom następujące polecenie z lokalizacji `.qs` plików

    ```
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

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Nie martw się, jeśli Twoja `iqsharp` wersja jest nowsza, powinna być zgodna z [najnowszą wersją](xref:microsoft.quantum.relnotes).

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

   - Przejdź do **widoku**—  ->  **paleta poleceń**
   - Wybierz pozycję **Q #: Instalowanie szablonów projektu**
   - Po kilku sekundach powinien zostać wyświetlony podręczny komunikat potwierdzający pomyślne zainstalowanie szablonów projektu.

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, przy użyciu `dotnet` narzędzia wiersza polecenia

1. Aktualizowanie szablonów projektów Quantum dla platformy .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

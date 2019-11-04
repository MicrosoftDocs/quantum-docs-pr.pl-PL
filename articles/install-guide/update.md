---
title: Dowiedz się, jak aktualizować Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185855"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aktualizowanie Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zaktualizować Microsoft Quantum Development Kit (QDK) do najnowszej wersji.

W tym artykule przyjęto założenie, że zainstalowano już QDK. Jeśli instalujesz po raz pierwszy, zapoznaj się z [Podręcznikiem instalacji](xref:microsoft.quantum.install).

Kroki aktualizacji zależą od środowiska deweloperskiego. Wybierz środowisko z następujących sekcji.

## <a name="python"></a>Python

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
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
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Teraz można używać zaktualizowanej wersji QDK do uruchamiania istniejących programów Quantum.

## <a name="jupyter-notebooks"></a>Notesy programu Jupyter

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Teraz możesz otworzyć istniejący Notes programu Jupyter i uruchomić go ze zaktualizowanym QDK.

## <a name="c-on-windows-using-visual-studio"></a>C#w systemie Windows, korzystanie z programu Visual Studio

1. Aktualizowanie rozszerzenia Q # programu Visual Studio

    - Program Visual Studio poprosi o zaakceptowanie aktualizacji [rozszerzenia programu Visual Studio Quantum](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Zaakceptuj aktualizację

    > [!NOTE]
    > Szablony projektu są aktualizowane przy użyciu rozszerzenia. Zaktualizowane szablony mają zastosowanie tylko do nowo utworzonych projektów. Kod dla istniejących projektów nie jest aktualizowany, gdy rozszerzenie zostanie zaktualizowane.

1. Aktualizowanie pakietów QDK

    - Otwórz istniejącą aplikację
    - Wybierz **zależności** w Eksplorator rozwiązań
    - Wybierz pozycję **Zarządzaj pakietami NuGet**
    - Aktualizowanie pakietów **Microsoft. Quantum** do najnowszej wersji

1. Teraz możesz uruchomić aplikację przy użyciu najnowszej QDK.

## <a name="c-using-vs-code"></a>C#, przy użyciu VS Code

1. Aktualizowanie rozszerzenia Quantum VS Code

    - Uruchom ponownie VS Code
    - Przejdź do karty **rozszerzenia**
    - Wybierz **Microsoft Quantum Development Kit rozszerzenia Visual Studio Code**
    - Załaduj ponownie rozszerzenie

1. Aktualizowanie szablonów projektów Quantum:

   - Przejdź do **widoku** **paleta poleceń** -> 
   - Wybierz pozycję **Q #: Instalowanie szablonów projektu**

1. Otwórz istniejącą aplikację w VS Code

   - Edytuj plik. csproj, aby dodać nowe wersje pakietu

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    Jeśli używasz innych pakietów `Microsoft.Quantum`, zaktualizuj je.

1. Teraz możesz uruchomić aplikację ze zaktualizowanym QDK

## <a name="c-using-the-dotnet-command-line-tool"></a>C#przy użyciu narzędzia wiersza polecenia `dotnet`

1. Aktualizowanie szablonów projektów Quantum dla platformy .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Aktualizowanie i uruchamianie istniejącej aplikacji

    - Aktualizowanie wersji pakietu QDK w aplikacji

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        Jeśli aplikacja korzysta z innych pakietów `Microsoft.Quantum`, zaktualizuj je.

    - Uruchamianie aplikacji

        ```bash
        dotnet run
        ```

    - Aplikacja będzie działać z nowymi wersjami pakietu

## <a name="whats-next"></a>Co dalej?

Teraz, po zaktualizowaniu zestawu Quantum Development Kit w preferowanym środowisku, można nadal opracowywać i uruchamiać programy Quantum. Jeśli nie zapisano jeszcze programu, możesz rozpocząć pracę z [pierwszym programem Quantum](xref:microsoft.quantum.write-program).

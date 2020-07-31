---
title: Programowanie przy użyciu języków Q# i Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 4d148435f01d975e690828dd02335758fc71dfe4
ms.sourcegitcommit: 2f4c637e194dc2b5d18539469ed37444e2800199
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/30/2020
ms.locfileid: "87436542"
---
# <a name="develop-with-q-and-python"></a>Programowanie przy użyciu języków Q# i Python

Zainstaluj zestaw QDK, aby tworzyć programy hosta w języku Python, umożliwiające wywoływanie operacji języka Q#.

## <a name="install-the-qsharp-python-package"></a>Instalowanie pakietu `qsharp` języka Python

### <a name="install-using-conda-recommended"></a>[Instalowanie przy użyciu środowiska conda (zalecane)](#tab/tabid-conda)

1. Zainstaluj narzędzie [Miniconda](https://docs.conda.io/en/latest/miniconda.html) lub [Anaconda](https://www.anaconda.com/products/individual#Downloads). **Uwaga:** Wymagana jest instalacja 64-bitowa.

1. Otwórz program Anaconda Prompt.

   - Lub, jeśli wolisz używać programu PowerShell albo pwsh: otwórz powłokę, uruchom polecenie `conda init powershell`, a następnie zamknij i ponownie otwórz powłokę.

1. Utwórz i aktywuj nowe środowisko conda o nazwie `qsharp-env` z wymaganymi pakietami (w tym Jupyter Notebook i IQ#), uruchamiając następujące polecenia:

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Uruchom polecenie `python -c "import qsharp"` z tego samego terminalu, aby zweryfikować instalację i wypełnić pamięć podręczną pakietów lokalnych wszystkimi wymaganymi składnikami zestawu QDK.

### <a name="install-using-net-cli-and-pip-advanced"></a>[Instalowanie przy użyciu interfejsu wiersza polecenia platformy .NET i narzędzia PIP (zaawansowane)](#tab/tabid-dotnetcli)

1. Wymagania wstępne:

    - Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze
    - Menedżer pakietów języka Python narzędzia [PIP](https://pip.pypa.io/en/stable/installing)
    - [Zestaw .NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Zainstaluj `qsharp`, pakiet języka Python, który umożliwia współdziałanie między językami Q# i Python.

    ```
    pip install qsharp
    ```

1. Zainstaluj IQ#, jądro używane w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i wykonywania operacji języka Q#.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Jeśli w kroku `dotnet iqsharp install` wystąpił błąd, otwórz nowe okno terminalu i spróbuj ponownie.
    > Jeśli to nadal nie działa, spróbuj znaleźć zainstalowane narzędzie `dotnet-iqsharp` (w systemie Windows `dotnet-iqsharp.exe`) i uruchomić następujące polecenie:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > gdzie `/path/to/dotnet-iqsharp` należy zastąpić ścieżką bezwzględną narzędzia `dotnet-iqsharp` w systemie plików.
    > Zwykle znajduje się ono w podfolderze `.dotnet/tools` w folderze profilu użytkownika.
    
***

Gotowe. Masz teraz zarówno pakiet `qsharp` języka Python, jak i jądro IQ# dla środowiska Jupyter, które udostępnia podstawowe funkcje kompilowania i wykonywania operacji języka Q# z poziomu środowiska Python i umożliwia korzystanie z notesów Jupyter Notebook dla języka Q#.

## <a name="choose-your-ide"></a>Wybieranie środowiska IDE

Chociaż języka Q# wraz z językiem Python można używać w dowolnym środowisku IDE, zdecydowanie zalecamy korzystanie z programu Visual Studio Code (VS Code) jako środowiska IDE na potrzeby aplikacji tworzonych przy użyciu języków Q# i Python. Dzięki rozszerzeniu QDK programu Visual Studio Code uzyskasz dostęp do bogatszej funkcjonalności, takiej jak ostrzeżenia, wyróżnianie składni, szablony projektów i inne.

Jeśli chcesz użyć programu VS Code:

- Zainstaluj program [VS Code](https://code.visualstudio.com/download) (dostępny dla systemów Windows, Linux i Mac).
- Zainstaluj [rozszerzenie QDK dla programu VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Jeśli chcesz użyć innego edytora, powyższe instrukcje przygotują Cię do wszystkiego.

## <a name="write-your-first-q-program"></a>Pisanie pierwszego programu w języku Q#

Teraz możesz już zweryfikować instalację pakietu `qsharp` języka Python, pisząc i wykonując prosty program w języku Q#.

1. Utwórz minimalną operację języka Q#, tworząc plik o nazwie `Operation.qs` i dodając do niego następujący kod:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. W tym samym folderze, w którym znajduje się plik `Operation.qs`, utwórz program w języku Python o nazwie `host.py`, aby symulować operację `SampleQuantumRandomNumberGenerator()` języka Q#:

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. Ze środowiska utworzonego podczas instalacji (tj. środowiska conda lub środowiska języka Python, w którym zainstalowano element `qsharp`), uruchom program:

    ```
    python host.py
    ```

1. Powinien zostać wyświetlony wynik wywołanej operacji. W tym przypadku, ponieważ operacja generuje losowy wynik, na ekranie zostanie wyświetlona wartość `0` lub `1`. W przypadku wielokrotnego uruchamiania programu każdy wynik powinien być wyświetlany przez w przybliżeniu połowę czasu.

> [!NOTE]
> * Ten kod języka Python to zwykły program w języku Python. Możesz użyć dowolnego środowiska języka Python, w tym notesów Jupyter Notebook opartych na języku Python, aby napisać program w języku Python i wywołać operacje języka Q#. Program w języku Python może zaimportować operacje języka Q# z dowolnych plików QS znajdujących się w tym samym folderze co sam kod języka Python.

## <a name="next-steps"></a>Następne kroki

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz postępować zgodnie z tym samouczkiem, aby napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).

---
title: Programowanie w języku Q# przy użyciu notesów Jupyter Notebook
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: bbd1f58ba7de205e452be7bac72b5fd78e7acd56
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871454"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Programowanie w języku Q# przy użyciu notesów Jupyter Notebook

Zainstaluj zestaw QDK na potrzeby opracowywania operacji języka Q# w notesach Jupyter Notebook języka Q#.

Notesy Jupyter Notebook zapewniają możliwość wykonywania kodu w miejscu, a także instrukcje, notatki i inną zawartość. Jest to idealne środowisko do pisania kodu języka Q# z osadzonymi wyjaśnieniami lub interaktywnych samouczków wykonywania obliczeń kwantowych. Oto jak zacząć tworzyć własne notesy języka Q#.

> [!NOTE]
> * W notesach Jupyter Notebook języka Q# można uruchamiać tylko kod języka Q# i nie można wywoływać operacji z zewnętrznych programów hosta (na przykład z plików języka Python lub C#). To środowisko nie będzie odpowiednie, jeśli chcesz połączyć program kwantowy z zewnętrznym klasycznym programem hosta.

## <a name="install-the-iq-jupyter-kernel"></a>Instalowanie jądra Jupyter IQ#

IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie zestawu .NET Core SDK używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.

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

### <a name="install-using-net-cli-advanced"></a>[Instalowanie przy użyciu interfejsu wiersza polecenia platformy .NET (zaawansowane)](#tab/tabid-dotnetcli)

1. Wymagania wstępne:

    - Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Zestaw .NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Zainstaluj pakiet `Microsoft.Quantum.IQSharp`.

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

Gotowe. Masz teraz jądro IQ# dla środowiska Jupyter, które udostępnia podstawowe funkcje kompilowania i wykonywania operacji języka Q# z poziomu notesów Jupyter Notebook dla języka Q#.

## <a name="create-your-first-q-notebook"></a>Tworzenie pierwszego notesu w języku Q#

Teraz możesz już zweryfikować instalację notesu Jupyter Notebook języka Q#, pisząc i wykonując prostą operację w języku Q#.

1. Ze środowiska utworzonego podczas instalacji (tj. utworzonego środowiska conda lub środowiska języka Python, w którym zainstalowano pakiet Jupyter) uruchom następujące polecenie, aby uruchomić serwer notesu Jupyter Notebook:

    ```
    jupyter notebook
    ```

    - Jeśli notes Jupyter Notebook nie zostanie otwarty automatycznie w przeglądarce, skopiuj i wklej adres URL otrzymany w wierszu polecenia do okna przeglądarki.

1. Wybierz pozycję „Nowy” → „Q#”, aby utworzyć notes Jupyter Notebook z jądrem Q#, i dodaj następujący kod do pierwszej komórki notesu:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Uruchom tę komórkę notesu:

    ![Komórka notesu Jupyter Notebook z kodem języka Q#](~/media/install-guide-jupyter.png)

    W danych wyjściowych komórki powinien zostać wyświetlony element `SampleQuantumRandomNumberGenerator`. W przypadku uruchamiania w notesach Jupyter Notebook kod języka Q# jest kompilowany, a komórka zwraca w danych wyjściowych nazwy wszystkich znalezionych operacji.

1. W nowej komórce wykonaj utworzoną operację w symulatorze za pomocą polecenia `%simulate`:

    ![Komórka notesu Jupyter Notebook z poleceniem magic %simulate](~/media/install-guide-jupyter-simulate.png)

    Powinien zostać wyświetlony wynik wywołanej operacji. W tym przypadku, ponieważ operacja generuje losowy wynik, na ekranie zostanie wyświetlona wartość `Zero` lub `One`. W przypadku wielokrotnego uruchamiania komórki każdy wynik powinien być wyświetlany przez w przybliżeniu połowę czasu.

## <a name="next-steps"></a>Następne kroki

Po zainstalowaniu zestawu QDK na potrzeby notesów Jupyter Notebook języka Q# możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng), pisząc kod języka Q# bezpośrednio w środowisku Jupyter Notebook.

Aby znaleźć więcej przykładów zastosowań notesów Jupyter Notebook języka Q#, zobacz:

- [Wprowadzenie do języka Q# i notesów Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Tam znajdziesz notes Jupyter Notebook języka Q# zawierający więcej szczegółów dotyczących tego, jak używać języka Q# w środowisku Jupyter.
- [Quantum Katas](xref:microsoft.quantum.overview.katas) to kolekcja typu open-source, zawierająca realizowane samodzielnie samouczki oraz zestawy ćwiczeń programistycznych w formie notesów Jupyter Notebook języka Q#. [Notesy samouczków Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) to dobry sposób, aby zacząć. Celem samouczków Quantum Katas jest połączenie nauki elementów obliczeń kwantowych i tworzenia zawartości w języku Q#. To doskonały przykład zawartości, którą można tworzyć za pomocą notesów Jupyter Notebook języka Q#.

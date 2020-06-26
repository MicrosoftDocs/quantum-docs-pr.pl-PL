---
title: Programowanie w języku Q# przy użyciu notesów Jupyter Notebook
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274163"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Programowanie w języku Q# przy użyciu notesów Jupyter Notebook

Zainstaluj zestaw QDK na potrzeby opracowywania operacji języka Q# w notesach Jupyter Notebook języka Q#.

Notesy Jupyter Notebook zapewniają możliwość wykonywania kodu w miejscu, a także instrukcje, notatki i inną zawartość. Jest to idealne środowisko do pisania kodu języka Q# z osadzonymi wyjaśnieniami lub interaktywnych samouczków wykonywania obliczeń kwantowych. Oto jak zacząć tworzyć własne notesy języka Q#.

IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie zestawu .NET Core SDK używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.

> [!NOTE]
> * W notesach Jupyter Notebook języka Q# można uruchamiać tylko kod języka Q# i nie można wywoływać operacji z zewnętrznych programów hosta (na przykład z plików języka Python lub C#). To środowisko nie będzie odpowiednie, jeśli chcesz połączyć program kwantowy z zewnętrznym klasycznym programem hosta.

1. Wymagania wstępne

    - Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Zestaw .NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Instalowanie pakietu `iqsharp`

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

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Uruchom następujące polecenie, aby uruchomić serwer notesów:

        ```
        jupyter notebook
        ```

    - Aby otworzyć notes Jupyter Notebook, skopiuj i wklej adres URL otrzymany w wierszu polecenia do okna przeglądarki.

    - Utwórz notes Jupyter Notebook z jądrem Q# i dodaj następujący kod do pierwszej komórki notesu:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Uruchom tę komórkę notesu:

        ![Komórka notesu Jupyter Notebook z kodem języka Q#](~/media/install-guide-jupyter.png)

        W danych wyjściowych komórki powinien zostać wyświetlony element `SayHello`. W przypadku uruchamiania w notesach Jupyter Notebook kod języka Q# jest kompilowany, a notes zwraca w danych wyjściowych nazwy znalezionych operacji.


    - W nowej komórce wykonaj utworzoną operację w symulatorze za pomocą polecenia `%simulate`:

        ![Komórka notesu Jupyter Notebook z poleceniem magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Na ekranie powinien zostać wyświetlony komunikat wraz z wynikiem wywołanej operacji (w tym przypadku jest to pusta krotka `()`, ponieważ operacja zwraca po prostu typ `Unit`).

## <a name="next-steps"></a>Następne kroki

Po zainstalowaniu zestawu QDK na potrzeby notesów Jupyter Notebook języka Q# możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng), pisząc kod języka Q# bezpośrednio w środowisku Jupyter Notebook.

Aby znaleźć więcej przykładów zastosowań notesów Jupyter Notebook języka Q#, zobacz:
- [Wprowadzenie do języka Q# i notesów Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Tam znajdziesz notes Jupyter Notebook języka Q#, w którym pokazano, jak używać języka Q# w tym środowisku.
- [Quantum Katas](xref:microsoft.quantum.overview.katas) to kolekcja typu open-source, zawierająca realizowane samodzielnie samouczki oraz zestawy ćwiczeń programistycznych w formie notesów Jupyter Notebook języka Q#. [Notesy samouczków Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) to dobry sposób, aby zacząć. Celem samouczków Quantum Katas jest połączenie nauki elementów obliczeń kwantowych i tworzenia zawartości w języku Q#. To doskonały przykład zawartości, którą można tworzyć za pomocą notesów Jupyter Notebook języka Q#.

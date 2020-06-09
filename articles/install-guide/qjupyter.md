---
title: Programowanie przy użyciu notesów Jupyter w języku Q#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 9117794d6cf6f05fa34e05c21fad8977d0e76505
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577824"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Programowanie przy użyciu notesów Jupyter w języku Q#

Zainstaluj QDK na potrzeby opracowywania operacji Q # w notesach Q # Jupyter.

Notesy Jupyter umożliwiają wykonywanie kodu w miejscu wraz z instrukcjami, notatkami i inną zawartością. To środowisko jest idealne do pisania kodu Q # z objaśnieniami osadzonymi lub interaktywnymi samouczkami przetwarzania. Oto jak zacząć tworzyć własne notesy języka Q#.

IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie zestawu .NET Core SDK używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.

> [!NOTE]
> * W notesach Q # Jupyter można uruchomić tylko kod Q #, a operacji nie można wywołać z zewnętrznych programów hosta (np. plików Python lub C#). To środowisko nie jest odpowiednie, jeśli celem jest połączenie zewnętrznego klasycznego programu hosta z programem Quantum.

1. Wymagania wstępne

    - [Python](https://www.python.org/downloads/) 3,6 lub nowszy
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Zestaw .NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Instalowanie pakietu `iqsharp`

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Uruchom następujące polecenie, aby uruchomić serwer notesów:

        ```
        jupyter notebook
        ```

    - Aby otworzyć Jupyter Notebook, skopiuj i wklej adres URL podany w wierszu polecenia do przeglądarki.

    - Utwórz Jupyter Notebook przy użyciu jądra Q # i Dodaj następujący kod do pierwszej komórki notesu:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Uruchom tę komórkę notesu:

        ![Jupyter Notebook komórki z kodem Q #](~/media/install-guide-jupyter.png)

        W danych wyjściowych komórki powinien zostać wyświetlony element `SayHello`. Podczas uruchamiania w Jupyter Notebook kod Q # jest kompilowany, a Notes będzie wyprowadzał nazwę znalezionych operacji.


    - W nowej komórce wykonaj właśnie utworzoną operację (w symulatorze) za pomocą `%simulate` polecenia:

        ![Jupyter Notebook komórki z użyciem symulowania Magic](~/media/install-guide-jupyter-simulate.png)

        Powinien zostać wyświetlony komunikat wydrukowany na ekranie wraz z wynikiem wywołanej operacji (w tym miejscu zostanie wyświetlona pusta krotka, `()` ponieważ operacja po prostu zwraca `Unit` Typ).

## <a name="next-steps"></a>Następne kroki

Po zainstalowaniu QDK dla notesów Q # Jupyter można napisać i uruchomić [swój pierwszy program Quantum](xref:microsoft.quantum.quickstarts.qrng) , pisząc kod Q bezpośrednio w środowisku Jupyter Notebook.

Aby uzyskać więcej przykładów, co możesz zrobić z notesami Q # Jupyter, zapoznaj się z tematem:
- [Wprowadzenie do programu Q # i Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Znajdziesz Jupyter Notebook Q #, który pokazuje, jak używać Q # w tym środowisku.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), Kolekcja typu "open source" z własnymi samouczkami i zestawami ćwiczeń programistycznych w postaci notesów Q # Jupyter. [Notesy w samouczku Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) są dobrym punktem początkowym. Katas Quantum jest celem uczenia się elementów opartych na obliczeniach Quantum i programowania Q # w tym samym czasie. Są one doskonałym przykładem rodzaju zawartości, którą można utworzyć za pomocą notesów Q # Jupyter.

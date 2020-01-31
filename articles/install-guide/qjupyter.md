---
title: 'Tworzenie za pomocą notesów Q # Jupyter'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831073"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Tworzenie za pomocą notesów Q # Jupyter

Zainstaluj QDK na potrzeby opracowywania operacji Q # w notesach Q # Jupyter.

Notesy Jupyter umożliwiają wykonywanie kodu w miejscu wraz z instrukcjami, notatkami i inną zawartością. To środowisko jest idealne do pisania kodu Q # z objaśnieniami osadzonymi lub interaktywnymi samouczkami przetwarzania. Oto jak zacząć tworzyć własne notesy języka Q#.

IQ# (wymawiane jak „i-q-sharp”) to rozszerzenie zestawu .NET Core SDK używane głównie w środowiskach Jupyter i Python, które zapewnia podstawowe funkcje kompilowania i symulowania operacji języka Q#.

> [!NOTE]
> * W notesach Q # Jupyter można uruchomić tylko kod Q #, a operacji nie można wywołać z zewnętrznych programów hosta (np. Python lub C# plików). To środowisko nie jest odpowiednie, jeśli celem jest połączenie zewnętrznego klasycznego programu hosta z programem Quantum.

1. Wymagania wstępne

    - Środowisko [Python](https://www.python.org/downloads/) 3.6 lub nowsze
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Zestaw .NET Core SDK 3,1 lub nowszy](https://www.microsoft.com/net/download)

1. Instalowanie pakietu `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Weryfikowanie instalacji przez utworzenie aplikacji `Hello World`

    - Uruchom następujące polecenie, aby uruchomić serwer notesów:

        ```bash
        jupyter notebook
        ```

    - Aby otworzyć Notes Jupyter i wkleić adres URL podany w wierszu polecenia do przeglądarki.

    - Utwórz notes Jupyter z jądrem Q# i dodaj następujący kod do pierwszej komórki notesu:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Uruchom tę komórkę notesu:

        ![Komórka notesu Jupyter z kodem języka Q#](~/media/install-guide-jupyter.png)

        W danych wyjściowych komórki powinien zostać wyświetlony element `SayHello`. W przypadku uruchamiania w notesach Jupyter kod języka Q# jest kompilowany, a notes zwraca w danych wyjściowych nazwę znalezionych operacji.


    - W nowej komórce wykonaj właśnie utworzoną operację (w symulatorze) za pomocą polecenia `%simulate`:

        ![Komórka notesu Jupyter z poleceniem magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Powinien zostać wyświetlony komunikat wydrukowany na ekranie wraz z wynikiem wywołanej operacji (w tym miejscu zostanie wyświetlona pusta krotka `()`, ponieważ operacja po prostu zwróci typ `Unit`).

## <a name="whats-next"></a>Co dalej?

Po zainstalowaniu zestawu Quantum Development Kit w preferowanym środowisku możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.write-program).

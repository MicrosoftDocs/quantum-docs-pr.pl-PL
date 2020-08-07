---
title: Tworzenie kwantowego generatora liczb losowych
description: Utwórz Q# projekt, który pokazuje podstawowe koncepcje Quantum, takie jak Podpozycja, tworząc generator liczb losowych Quantum.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8db892091794cb1166e41744572d8938d975abf2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869770"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Samouczek: implementowanie kwantowego generatora liczb losowych w języku Q\#

Prosty przykład algorytmu Quantum zapisany w Q# jest generatorem liczb losowych Quantum. Ten algorytm wykorzystuje zjawiska mechaniki kwantowej, aby utworzyć liczbę losową.

## <a name="prerequisites"></a>Wymagania wstępne

- Zestaw Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Utwórz Q# projekt do [użycia Q# z wiersza polecenia](xref:microsoft.quantum.install.standalone)lub programu [hosta Python](xref:microsoft.quantum.install.python) lub [programu hosta języka C#](xref:microsoft.quantum.install.cs).

## <a name="write-a-no-locq-operation"></a>Napisz Q# operację

### <a name="no-locq-operation-code"></a>Q#kod operacji

1. Zastąp zawartość pliku Program.qs następującym kodem:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Jak wspomniano w artykule [Informacje na temat obliczeń kwantowych](xref:microsoft.quantum.overview.understanding), kubit jest jednostką informacji kwantowych, która może być w superpozycji. Przy pomiarze kubit może mieć tylko wartość 0 lub 1. Jednak podczas wykonywania stan kubitu reprezentuje prawdopodobieństwo odczytania wartości 0 lub 1 przy pomiarze. Ten stan probabilistyczny jest nazywany superpozycją. Przy użyciu tego prawdopodobieństwa można generować liczby losowe.

W naszej Q# operacji wprowadzamy `Qubit` Typ danych, natywny dla Q# . Element `Qubit` można przydzielić tylko za pomocą instrukcji `using`. Po przydzieleniu kubit jest zawsze w stanie `Zero`. 

Za pomocą operacji `H` można wprowadzić element `Qubit` w stan superpozycji. Aby zmierzyć kubit i odczytać jego wartość, użyj operacji wewnętrznej `M`.

Gdy wprowadzimy element `Qubit` w stan superpozycji i wykonamy na nim pomiar, wartość wyniku będzie inna przy każdym wywołaniu kodu.

Po cofnięciu przydziału elementu `Qubit` należy z powrotem jawnie ustawić dla niego stan `Zero` — w przeciwnym razie symulator zgłosi błąd czasu wykonywania. Można to łatwo zrobić, wywołując funkcję `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Wizualizowanie kodu za pomocą sfery Blocha

Na sferze Blocha biegun północny reprezentuje wartość klasyczną **0**, a biegun południowy reprezentuje wartość klasyczną **1**. Każdą superpozycję można przedstawić jako punkt na sferze (reprezentowany przez strzałkę). Im bliżej od końca strzałki do bieguna, tym większe jest prawdopodobieństwo, że przy pomiarze kubit ulegnie kolapsowi do wartości klasycznej przypisanej do tego bieguna. Na przykład stan kubitu reprezentowany przez czerwoną strzałkę poniżej ma większe prawdopodobieństwo zwrócenia wartości **0** przy pomiarze.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

Ta reprezentacja może posłużyć do wizualizacji działania kodu:

* Zaczniemy od kubitu zainicjowanego w stanie **0** i zastosujemy funkcję `H`, aby utworzyć superpozycję, w której prawdopodobieństwa wartości **0** i **1** są jednakowe.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* Następnie zmierzymy kubit i zapiszemy dane wyjściowe:

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

Ponieważ wynik pomiaru jest całkowicie losowy, uzyskaliśmy losowy bit. Możemy wywołać tę operację kilka razy, aby utworzyć liczby całkowite. Jeśli na przykład wywołamy operację trzykrotnie w celu uzyskania trzech losowych bitów, możemy utworzyć losowe liczby 3-bitowe (czyli liczbę losową z zakresu od 0 do 7).


## <a name="creating-a-complete-random-number-generator"></a>Tworzenie kompletnego generatora liczb losowych

Teraz, gdy mamy Q# operację generującą bity losowe, możemy użyć jej do utworzenia kompletnego generatora liczb losowych Quantum. Możemy użyć Q# aplikacji wiersza polecenia lub programu hosta.



### <a name="no-locq-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[Q#aplikacje wiersza polecenia z programem Visual Studio lub Visual Studio Code](#tab/tabid-qsharp)

Aby utworzyć pełną Q# aplikację wiersza polecenia, Dodaj następujący punkt wejścia do Q# programu: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

Plik wykonywalny uruchomi operację lub funkcję oznaczoną atrybutem `@EntryPoint()` w symulatorze lub estymatorze zasobów, w zależności od konfiguracji projektu i opcji wiersza polecenia.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

W programie Visual Studio wystarczy nacisnąć klawisze Ctrl + F5, aby wykonać skrypt.

W programie VS Code za pierwszym razem skompiluj plik Program.qs, wpisując w terminalu następujące polecenie:

```dotnetcli
dotnet build
```

Przy kolejnych uruchomieniach nie musisz ponownie kompilować pliku. Aby go uruchomić, wprowadź następujące polecenie i naciśnij klawisz Enter:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Język Python z programem Visual Studio Code lub wierszem polecenia](#tab/tabid-python)

Aby uruchomić nowy Q# program z języka Python, Zapisz następujący kod jako `host.py` :

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Następnie możesz uruchomić program hosta języka Python z poziomu wiersza polecenia:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[Język C# w programie Visual Studio Code lub Visual Studio](#tab/tabid-csharp)

Aby uruchomić nowy Q# program w języku c#, zmodyfikuj, `Driver.cs` aby zawierał następujący kod w języku c#:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Następnie możesz uruchomić program hosta języka C# z poziomu wiersza polecenia (w programie Visual Studio naciśnij klawisz F5):

```bash
$ dotnet run
The random number generated is 42
```

***

---
title: Tworzenie kwantowego generatora liczb losowych
description: Utwórz projekt języka Q# demonstrujący podstawowe koncepcje kwantowe, takie jak superpozycja, tworząc kwantowy generator liczb losowych.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 5a433606f08f4c6a4ab7b5df67a7f0c30d2b3f0d
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683003"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Szybki start: implementowanie kwantowego generatora liczb losowych w języku Q\#

Prostym przykładem kwantowego algorytmu napisanego w języku Q# jest kwantowy generator liczb losowych. Ten algorytm wykorzystuje zjawiska mechaniki kwantowej, aby utworzyć liczbę losową.

## <a name="prerequisites"></a>Wymagania wstępne

- Zestaw Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Tworzenie projektu języka Q#](xref:microsoft.quantum.howto.createproject)

## <a name="write-a-q-operation"></a>Tworzenie operacji w języku Q#

### <a name="q-operation-code"></a>Kod operacji języka Q#

1. Zastąp zawartość pliku Program.qs następującym kodem:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Jak wspomniano w artykule [Co to są obliczenia kwantowe?](xref:microsoft.quantum.overview.what), kubit jest jednostką informacji kwantowych, która może być w superpozycji. Przy pomiarze kubit może mieć tylko wartość 0 lub 1. Jednak podczas wykonywania stan kubitu reprezentuje prawdopodobieństwo odczytania wartości 0 lub 1 przy pomiarze. Ten stan probabilistyczny jest nazywany superpozycją. Przy użyciu tego prawdopodobieństwa można generować liczby losowe.

W naszej operacji języka Q# wprowadzamy typ danych `Qubit` (natywny dla języka Q#). Element `Qubit` można przydzielić tylko za pomocą instrukcji `using`. Po przydzieleniu kubit jest zawsze w stanie `Zero`. 

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

Teraz, gdy mamy operację Q#, która generuje losowe bity, możemy jej użyć do utworzenia kompletnego kwantowego generatora liczb losowych. Możemy użyć aplikacji wiersza polecenia języka Q# lub programu hosta.



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[Aplikacje wiersza polecenia języka Q# w programie Visual Studio lub Visual Studio Code](#tab/tabid-qsharp)

Aby utworzyć kompletną aplikację wiersza polecenia języka Q#, dodaj następujący punkt wejścia do swojego programu w języku Q#. 

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

Aby uruchomić nowy program języka Q# z poziomu środowiska Python, zapisz następujący kod jako `host.py`:

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Następnie możesz uruchomić program hosta języka Python z poziomu wiersza polecenia:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[Język C# w programie Visual Studio Code lub Visual Studio](#tab/tabid-csharp)

Aby uruchomić nowy program języka Q# z poziomu środowiska C#, zmodyfikuj element `Driver.cs` tak, aby zawierał następujący kod języka C#:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Następnie możesz uruchomić program hosta języka C# z poziomu wiersza polecenia (w programie Visual Studio naciśnij klawisz F5):

```bash
$ dotnet run
The random number generated is 42
```

***

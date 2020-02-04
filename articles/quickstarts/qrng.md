---
title: Tworzenie kwantowego generatora liczb losowych
description: Utwórz projekt języka Q# demonstrujący podstawowe koncepcje kwantowe, takie jak superpozycja, tworząc kwantowy generator liczb losowych.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 134617455b720cc755b9ee9fb68fb59e624d3f1a
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820932"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Szybki start: Implementowanie kwantowego generatora liczb losowych w języku Q#
Prostym przykładem kwantowego algorytmu napisanego w języku Q# jest kwantowy generator liczb losowych. Ten algorytm wykorzystuje zjawiska mechaniki kwantowej, aby utworzyć liczbę losową. 

## <a name="prerequisites"></a>Wymagania wstępne

- Zestaw Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Tworzenie projektu języka Q#](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Tworzenie operacji w języku Q#

### <a name="q-operation-code"></a>Kod operacji języka Q#

1. Zastąp zawartość pliku Operation.qs następującym kodem:

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(qubit = Qubit())  { // Allocate a qubit.
                H(qubit);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(v);     // Measure the qubit value.
                Reset(qubit);
                return r;
            }
        }
    }
    ```

Jak wspomniano w artykule [Co to są obliczenia kwantowe?](xref:microsoft.quantum.overview.what), kubit jest jednostką informacji kwantowych, która może być w superpozycji. Przy pomiarze kubit może mieć tylko wartość 0 lub 1. Jednak podczas wykonywania stan kubitu reprezentuje prawdopodobieństwo odczytania wartości 0 lub 1 przy pomiarze. Ten stan probabilistyczny jest nazywany superpozycją. Przy użyciu tego prawdopodobieństwa można generować liczby losowe.

W naszej operacji języka Q# wprowadzamy typ danych `Qubit` (natywny dla języka Q#). Element `Qubit` można przydzielić tylko za pomocą instrukcji `using`. Po przydzieleniu kubit jest zawsze w stanie `Zero`. 

Za pomocą operacji `H` można wprowadzić element `Qubit` w stan superpozycji. Aby zmierzyć kubit i odczytać jego wartość, użyj operacji wewnętrznej `M`.

Gdy wprowadzimy element `Qubit` w stan superpozycji i wykonamy na nim pomiar, wartość wyniku będzie inna przy każdym wywołaniu kodu. 

Po cofnięciu przydziału elementu `Qubit` należy z powrotem jawnie ustawić dla niego stan `Zero` — w przeciwnym razie symulator zgłosi błąd czasu wykonywania. Można to łatwo zrobić, wywołując funkcję `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Wizualizowanie kodu za pomocą sfery Blocha

Na sferze Blocha biegun północny reprezentuje wartość klasyczną **0**, a biegun południowy reprezentuje wartość klasyczną **1**. Każdą superpozycję można przedstawić jako punkt na sferze (reprezentowany przez strzałkę). Im bliżej od końca strzałki do bieguna, tym większe jest prawdopodobieństwo, że przy pomiarze kubit ulegnie kolapsowi do wartości klasycznej przypisanej do tego bieguna. Na przykład stan kubitu reprezentowany przez czerwoną strzałkę poniżej ma większe prawdopodobieństwo zwrócenia wartości **0** przy pomiarze.

<img src="~/media/qrng-Bloch.png" width="175">

Ta reprezentacja może posłużyć do wizualizacji działania kodu:

* Zaczniemy od kubitu zainicjowanego w stanie **0** i zastosujemy funkcję `H`, aby utworzyć superpozycję, w której prawdopodobieństwa wartości **0** i **1** są jednakowe.

<img src="~/media/qrng-H.png" width="450">

* Następnie zmierzymy kubit i zapiszemy dane wyjściowe:

<img src="~/media/qrng-meas.png" width="450">

Ponieważ wynik pomiaru jest całkowicie losowy, uzyskaliśmy losowy bit. Możemy wywołać tę operację kilka razy, aby utworzyć liczby całkowite. Jeśli na przykład wywołamy operację trzykrotnie w celu uzyskania trzech losowych bitów, możemy utworzyć losowe liczby 3-bitowe (czyli liczbę losową z zakresu od 0 do 7).

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>Tworzenie kompletnego generatora liczb losowych przy użyciu programu hosta

Teraz, gdy mamy operację Q#, która generuje losowe bity, możemy jej użyć do utworzenia kompletnego kwantowego generatora liczb losowych przy użyciu programu hosta.

 ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[Język Python z programem Visual Studio Code lub wierszem polecenia](#tab/tabid-python)
 
 Aby uruchomić nowy program języka Q# z poziomu środowiska Python, zapisz następujący kod jako `host.py`:
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 Następnie możesz uruchomić program hosta języka Python z poziomu wiersza polecenia:
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[Język C# z programem Visual Studio Code lub wierszem polecenia](#tab/tabid-csharp)
 
 Aby uruchomić nowy program języka Q# z poziomu środowiska C#, zmodyfikuj element `Driver.cs` tak, aby zawierał następujący kod języka C#:
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 Następnie możesz uruchomić program hosta języka C# z poziomu wiersza polecenia:
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[Język C# w programie Visual Studio 2019](#tab/tabid-vs2019)

 Aby uruchomić nowy program języka Q# z poziomu środowiska C# w programie Visual Studio, zmodyfikuj element `Driver.cs` tak, aby zawierał następujący kod języka C#:

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 Następnie naciśnij klawisz F5. Program zacznie działać i pojawi się nowe okno z wygenerowaną liczbą losową: 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***

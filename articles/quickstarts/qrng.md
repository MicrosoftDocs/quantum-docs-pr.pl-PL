---
title: Tworzenie kwantowego generatora liczb losowych
description: Utwórz projekt języka Q# demonstrujący podstawowe koncepcje kwantowe, takie jak superpozycja, tworząc kwantowy generator liczb losowych.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: c3039b92c4b3235a397d5cf31280ac2673706e9d
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462836"
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
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

Jak wspomniano w artykule [Co to są obliczenia kwantowe?](xref:microsoft.quantum.overview.what), kubit jest jednostką informacji kwantowych, która może być w superpozycji. Przy pomiarze kubit może mieć tylko wartość 0 lub 1. Jednak podczas wykonywania stan kubitu reprezentuje prawdopodobieństwo odczytania wartości 0 lub 1 przy pomiarze. Ten stan probabilistyczny jest nazywany superpozycją. Przy użyciu tego prawdopodobieństwa można generować liczby losowe.

W naszej operacji języka Q# wprowadzamy typ danych `Qubit` (natywny dla języka Q#). Element `Qubit` można przydzielić tylko za pomocą instrukcji `using`. Po przydziale kubit jest zawsze w stanie `Zero`. 

Za pomocą operacji `H` można wprowadzić element `Qubit` w stan superpozycji. Aby zmierzyć kubit i odczytać jego wartość, użyj operacji wewnętrznej `M`.

Gdy wprowadzimy element `Qubit` w stan superpozycji i wykonamy na nim pomiar, wartość wyniku będzie inna przy każdym wywołaniu kodu. 

Po cofnięciu przydziału elementu `Qubit` należy z powrotem jawnie ustawić dla niego stan `Zero` — w przeciwnym razie symulator zgłosi błąd czasu wykonywania. Można to łatwo zrobić, wywołując funkcję `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Wizualizowanie kodu za pomocą sfery Blocha

Na sferze Blocha biegun północny reprezentuje wartość klasyczną **0**, a biegun południowy reprezentuje wartość klasyczną **1**. Każdą superpozycję można przedstawić jako punkt na sferze (reprezentowany przez strzałkę). Im bliżej od końca strzałki do bieguna, tym większe jest prawdopodobieństwo, że przy pomiarze kubit ulegnie kolapsowi do wartości klasycznej przypisanej do tego bieguna. Na przykład stan kubitu reprezentowany przez czerwoną strzałkę poniżej ma większe prawdopodobieństwo zwrócenia wartości **0** przy pomiarze.

<img src="./Bloch.svg" width="175">

Ta reprezentacja może posłużyć do wizualizacji działania kodu:

* Zaczniemy od kubitu zainicjowanego w stanie **0** i zastosujemy funkcję `H`, aby utworzyć superpozycję, w której prawdopodobieństwa wartości **0** i **1** są jednakowe.

<img src="./H.svg" width="450">

* Następnie zmierzymy kubit i zapiszemy dane wyjściowe:

<img src="./Measurement2.svg" width="450">

Ponieważ wynik pomiaru jest całkowicie losowy, uzyskaliśmy losowy bit. Możemy wywołać tę operację kilka razy, aby utworzyć liczby całkowite. Jeśli na przykład wywołamy operację trzykrotnie w celu uzyskania trzech losowych bitów, możemy utworzyć losowe liczby 3-bitowe (czyli liczbę losową z zakresu od 0 do 7).

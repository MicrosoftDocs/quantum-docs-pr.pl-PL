---
title: 'Techniki Q # — testowanie i debugowanie | Microsoft Docs'
description: 'Techniki Q # — testowanie i debugowanie'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: d352ffa315b654cfcf8991fa116465d3dad49f0a
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864274"
---
# <a name="testing-and-debugging"></a>Testowanie i debugowanie

Podobnie jak w przypadku klasycznego programowania, konieczna jest możliwość sprawdzenia, czy programy Quantum działają zgodnie z oczekiwaniami, i aby można było zdiagnozować program Quantum, który jest nieprawidłowy.
W tej sekcji omówiono narzędzia oferowane przez Q # do testowania i debugowania programów Quantum.

## <a name="unit-tests"></a>Testy jednostkowe

Typowym podejściem do testowania klasycznych programów jest pisanie małych programów o nazwie *testy jednostkowe* , które uruchamiają kod w bibliotece i porównując dane wyjściowe z nieoczekiwanymi wynikami.
Na przykład firma Microsoft może chcieć upewnić się, że `Square(2)` zwraca `4`, ponieważ *wiemy, że* $2 ^ 2 = $4.

Polecenie Q # obsługuje tworzenie testów jednostkowych dla programów Quantum i które mogą być wykonywane jako testy w ramach struktury testów jednostkowych [xUnit](https://xunit.github.io/) .

### <a name="creating-a-test-project"></a>Tworzenie projektu testowego

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Open Visual Studio 2019. Przejdź do menu `File` i wybierz pozycję `New` > `Project...`.
W prawym górnym rogu Wyszukaj pozycję `Q#`i wybierz szablon `Q# Test Project`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

W ulubionym wierszu polecenia Uruchom następujące polecenie:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Nowy projekt będzie miał `Tests.qs`jednego pliku, który stanowi wygodne miejsce do zdefiniowania nowych testów.
Początkowo ten plik zawiera jeden przykładowy test jednostkowy `AllocateQubit`, który sprawdza, czy nowo przydzieloną qubit znajduje się w stanie $ \ket{0}$ i drukuje komunikat:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

: New: Każda operacja Q # lub funkcja, która przyjmuje argument typu `Unit` i zwraca `Unit` może być oznaczona jako test jednostkowy za pośrednictwem atrybutu `@Test("...")`. Argument tego atrybutu, `"QuantumSimulator"` powyżej, określa obiekt docelowy, na którym wykonywany jest test. Pojedynczy test można wykonać na wielu celach. Na przykład Dodaj atrybut `@Test("ResourcesEstimator")` powyżej `AllocateQubit`. 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Zapisz plik i wykonaj wszystkie testy. Teraz powinny być dwa testy jednostkowe, jeden, gdzie AllocateQubit jest wykonywany w QuantumSimulator i jeden, gdzie jest wykonywany w ResourceEstimator. 

Kompilator Q # rozpoznaje wbudowane elementy docelowe "QuantumSimulator", "ToffoliSimulator" i "ResourcesEstimator" jako prawidłowe cele wykonywania dla testów jednostkowych. Istnieje również możliwość określenia dowolnej w pełni kwalifikowanej nazwy, aby zdefiniować niestandardowy cel wykonania. 

### <a name="running-q-unit-tests"></a>Uruchamianie testów jednostkowych Q #

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Jako jednorazowe skonfigurowanie poszczególnych rozwiązań przejdź do menu `Test` i wybierz `Test Settings` > `Default Processor Architecture` > `X64`.

> [!TIP]
> Domyślne ustawienie architektury procesora dla programu Visual Studio jest przechowywane w pliku opcji rozwiązania (`.suo`) dla każdego rozwiązania.
> W przypadku usunięcia tego pliku należy ponownie wybrać `X64` jako architekturę procesora.

Skompiluj projekt, przejdź do menu `Test` i wybierz pozycję `Windows` > `Test Explorer`. `AllocateQubit` zostanie wyświetlona na liście testów w grupie `Not Run Tests`. Wybierz `Run All` lub Uruchom ten test indywidualny, który powinien zostać przekazany!

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

Aby uruchomić testy, przejdź do folderu projektu (folder, który zawiera `Tests.csproj`), a następnie wykonaj polecenie:

```bash
$ dotnet restore
$ dotnet test
```

Powinny zostać wyświetlone dane wyjściowe podobne do następujących:

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

Testy jednostkowe można filtrować według ich nazwy i/lub celu wykonania:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

Funkcja wewnętrzna <xref:microsoft.quantum.intrinsic.message> ma typ `(String -> Unit)` i umożliwia tworzenie komunikatów diagnostycznych.

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Po wykonaniu testu w Eksploratorze testów i kliknięciu testu zostanie wyświetlony panel z informacjami o wykonywaniu testów: stanie zakończonych niepowodzeniem, czas, który upłynął, i link "output". Kliknięcie linku "output" spowoduje otwarcie danych wyjściowych testu w nowym oknie.

![dane wyjściowe testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

Stan przekazywania/niepowodzenia dla każdego testu jest drukowany w konsoli programu przez `dotnet test`.
W przypadku niepowodzeń testów są one również drukowane w konsoli programu w celu ułatwienia zdiagnozowania błędu.

***

## <a name="assertions"></a>Potwierdzenia

Ponieważ funkcje w pytaniach Q # nie mają _logicznych_ efektów ubocznych, wszelkie _Inne rodzaje_ efektów wykonywania funkcji, której typem danych wyjściowych jest pusta `()` krotka, nie można nigdy zaobserwować w programie Q #.
Oznacza to, że komputer docelowy może nie wykonywać żadnej funkcji, która zwraca `()` z gwarancją, że to pominięcie nie zmodyfikuje zachowania żadnego z następujących kodów Q #.
Dzięki temu funkcje zwracają `()` użytecznym narzędziem do osadzania potwierdzeń i logiki debugowania do programów Q #. 

Tę samą logikę można zastosować do implementacji zatwierdzeń. Rozważmy prosty przykład:

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

W tym miejscu słowo kluczowe `fail` wskazuje, że obliczenia nie powinny być wykonywane, a na komputerze docelowym z uruchomionym programem Q # nie należy przechodzić.
Według definicji nie można zaobserwować błędu tego rodzaju z poziomu Q #, ponieważ po osiągnięciu instrukcji `fail` nie jest uruchamiany żaden dodatkowy kod Q #.
W takim przypadku, jeśli będziemy przełączać się do `AssertPositive`, możemy zapewnić, że jego dane wejściowe były dodatnie.

W oparciu o te pomysły [Preludium](xref:microsoft.quantum.libraries.standard.prelude) oferuje dwa szczególnie przydatne potwierdzenia, <xref:microsoft.quantum.intrinsic.assert> i <xref:microsoft.quantum.intrinsic.assertprob> oba modeluje jako operacje na `()`. Każdy z tych zatwierdzeń przyjmuje operatora Pauli opisujące konkretną miarę zainteresowania, rejestr Quantum, na którym ma zostać wykonane pomiary, i hipotetyczny wynik.
Na komputerach docelowych, które współpracują przez symulację, nie są one powiązane z [theoremem bez klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem)i mogą wykonywać takie pomiary bez zakłócania rejestracji przesłanej do takich potwierdzeń.
Symulator może następnie wyglądać podobnie do powyższej funkcji `AssertPositive`, przerywanie obliczeń, jeśli hipotetyczny wynik nie zostanie zaobserwowany w praktyce:

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

Na fizycznym sprzęcie Quantum, gdzie theorem bez klonowania uniemożliwia badanie stanu Quantum, operacje `Assert` i `AssertProb` po prostu zwracają `()` bez żadnego skutku.

Przestrzeń nazw <xref:microsoft.quantum.diagnostics> zawiera kilka więcej funkcji rodziny `Assert`, co pozwala nam sprawdzić bardziej zaawansowane warunki. 

## <a name="dump-functions"></a>Funkcje zrzutu

Aby ułatwić rozwiązywanie problemów z programami Quantum, przestrzeń nazw <xref:microsoft.quantum.diagnostics> oferuje dwie funkcje, które mogą zrzutować do pliku bieżący stan maszyny docelowej: <xref:microsoft.quantum.diagnostics.dumpmachine> i <xref:microsoft.quantum.diagnostics.dumpregister>. Wygenerowane dane wyjściowe każdego z nich są zależne od maszyny docelowej.

### <a name="dumpmachine"></a>DumpMachine

Kompleksowy symulator Quantum dystrybuowany w ramach zestawu Quantum Development Kit zapisuje w pliku [funkcję Wave](https://en.wikipedia.org/wiki/Wave_function) całego systemu Quantum jako tablicę jednowymiarową liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru stanu podstawy obliczeniowej $ \ket{n} $, gdzie $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ dla usługi BITS $\{b_i\}$. Na przykład na komputerze z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ wywołując <xref:microsoft.quantum.diagnostics.dumpmachine> generuje te dane wyjściowe:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

Pierwszy wiersz zawiera komentarz z identyfikatorami odpowiednich qubits w ich znaczącej kolejności.
Pozostała część wierszy zawiera opis amplitudy prawdopodobieństwa pomiaru wektora stanu \ket{n} $ w obu formatach kartezjańskiego i biegunowych. Szczegółowo dla pierwszego wiersza:

* **`∣0❭:`** ten wiersz odnosi się do `0` stanu podstawy obliczeń
* **`0.707107 +  0.000000 i`** : amplituda prawdopodobieństwa w formacie kartezjańskiego.
* **` == `** : znak `equal` oddzieli obie równoważne reprezentacje.
* **`**********  `** : graficzna reprezentacja rozmiaru, liczba `*` jest proporcjonalna do prawdopodobieństwa mierzenia tego wektora stanu.
* **`[ 0.500000 ]`** : wartość liczbowa wielkości
* **`    ---`** : graficzna reprezentacja fazy amplitudy (patrz poniżej).
* **`[ 0.0000 rad ]`** : wartość liczbowa fazy (w radianach).

Obie wartości i fazy są wyświetlane ze graficzną reprezentacją. Reprezentacja wielkości jest prosta do przodu: pokazuje pasek `*`, tym większe prawdopodobieństwo powyższego poziomu paska. Dla fazy pokazywane są następujące symbole reprezentujące kąt na podstawie zakresów:

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

W poniższych przykładach przedstawiono `DumpMachine` niektórych typowych stanów:

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > Identyfikator qubit jest przypisywany w czasie wykonywania i nie musi być wyrównany do kolejności, w której został przydzielony qubit lub jej pozycji w rejestrze qubit.


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Identyfikator qubit można ustalić w programie Visual Studio, umieszczając punkt przerwania w kodzie i sprawdzając wartość zmiennej qubit, na przykład:
  > 
  > ![Pokaż identyfikator qubit w programie Visual Studio](~/media/qubit_id.png)
  >
  > qubit z indeksem `0` na `register2` ma identyfikator =`3`, qubit z indeksem `1` ma identyfikator =`2`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Identyfikator qubit można ustalić przy użyciu funkcji <xref:microsoft.quantum.intrinsic.message> i przekazywać zmienną qubit w komunikacie, na przykład:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > który może generować następujące dane wyjściowe:
  >```
  > 0=q:3; 1=q:2
  >```
  > co oznacza, że qubit z indeksem `0` na `register2` ma identyfikator =`3`, qubit z indeksem `1` ma identyfikator =`2`.


***

<xref:microsoft.quantum.diagnostics.dumpmachine> jest częścią <xref:microsoft.quantum.diagnostics> przestrzeni nazw, dlatego aby można było jej używać, należy dodać instrukcję `open`:

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister> działa jak <xref:microsoft.quantum.diagnostics.dumpmachine>, z tą różnicą, że pobiera również tablicę qubits w celu ograniczenia ilości informacji tylko do odpowiednich qubits.

Podobnie jak w przypadku <xref:microsoft.quantum.diagnostics.dumpmachine>, informacje generowane przez <xref:microsoft.quantum.diagnostics.dumpregister> są zależne od maszyny docelowej. W przypadku kompleksowego symulatora Quantum zapisuje w pliku funkcję Wave do globalnej fazy podsystemu Quantum wygenerowanego przez podaną qubits w tym samym formacie co <xref:microsoft.quantum.diagnostics.dumpmachine>.  Na przykład należy ponownie wykonać maszynę z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ Pi/4} ((\frac{1}{\sqrt{2}} \ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}) \end{align} $ $ wywołujący <xref:microsoft.quantum.diagnostics.dumpregister> dla `qubit[0]` generuje te dane wyjściowe :

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

i wywołanie <xref:microsoft.quantum.diagnostics.dumpregister> dla `qubit[1]` generuje następujące dane wyjściowe:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Ogólnie rzecz biorąc, stan rejestru Entangled z innym rejestrem jest stanem mieszanym, a nie czystym. W takim przypadku <xref:microsoft.quantum.diagnostics.dumpregister> wyświetla następujący komunikat:

```
Qubits provided (0;) are entangled with some other qubit.
```

Poniższy przykład pokazuje, jak można użyć obu <xref:microsoft.quantum.diagnostics.dumpregister> i <xref:microsoft.quantum.diagnostics.dumpmachine> w kodzie Q:

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a>Debugowanie

W oparciu o `Assert` i `Dump` funkcje i operacje, funkcja Q # obsługuje podzbiór standardowych możliwości debugowania programu Visual Studio: [ustawianie punktów przerwania](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [Przechodzenie przez kod przy użyciu](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) klawisza F10 i [Sprawdzanie wartości zmiennych klasycznych](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) jest możliwe podczas wykonywania kodu w symulatorze.

Debugowanie w Visual Studio Code wykorzystuje funkcje debugowania udostępniane przez program C# for Visual Studio Code Extension obsługiwane przez OmniSharp i wymagające zainstalowania [najnowszej wersji](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 

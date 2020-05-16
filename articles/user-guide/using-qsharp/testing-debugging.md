---
title: Testowanie i debugowanie
description: Dowiedz się, jak korzystać z testów jednostkowych, faktów i potwierdzeń oraz funkcji zrzutów do testowania i debugowania programów Quantum.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: 374ac42255ab6b2c5eff8ab7879b3a5103181f7f
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430921"
---
# <a name="testing-and-debugging"></a>Testowanie i debugowanie

Podobnie jak w przypadku klasycznego programowania, konieczna jest możliwość sprawdzenia, czy programy Quantum działają zgodnie z oczekiwaniami, i aby można było zdiagnozować program Quantum, który jest nieprawidłowy.
W tej sekcji omówiono narzędzia oferowane przez Q # do testowania i debugowania programów Quantum.

## <a name="unit-tests"></a>Testy jednostkowe

Typowym podejściem do testowania klasycznych programów jest pisanie małych programów o nazwie *testy jednostkowe* , które uruchamiają kod w bibliotece i porównując dane wyjściowe z nieoczekiwanymi wynikami.
Na przykład firma Microsoft może chcieć upewnić się `Square(2)` , że zwraca `4` , ponieważ *a priori* wiemy, że $2 ^ 2 = $4.

Polecenie Q # obsługuje tworzenie testów jednostkowych dla programów Quantum i które mogą być wykonywane jako testy w ramach struktury testów jednostkowych [xUnit](https://xunit.github.io/) .

### <a name="creating-a-test-project"></a>Tworzenie projektu testowego

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Otwórz program Visual Studio 2019. Przejdź do `File` menu i wybierz opcję `New`  >  `Project...` .
W prawym górnym rogu Wyszukaj `Q#` i wybierz `Q# Test Project` szablon.

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

W ulubionym wierszu polecenia Uruchom następujące polecenie:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Twój nowy projekt będzie miał pojedynczy plik `Tests.qs` , który zapewnia wygodne miejsce do definiowania nowych testów Q # Unit.
Początkowo ten plik zawiera jeden przykładowy test jednostkowy, `AllocateQubit` który sprawdza, czy nowo przydzieloną qubit znajduje się w stanie $ \ket {0} $ i drukuje komunikat:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

: New: Każda operacja Q # lub funkcja, która przyjmuje argument typu `Unit` i Return, `Unit` może być oznaczona jako test jednostkowy za pośrednictwem `@Test("...")` atrybutu. Argument tego atrybutu, `"QuantumSimulator"` powyżej, określa obiekt docelowy, na którym wykonywany jest test. Pojedynczy test można wykonać na wielu celach. Na przykład Dodaj atrybut `@Test("ResourcesEstimator")` powyżej `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Zapisz plik i wykonaj wszystkie testy. Teraz powinny być dwa testy jednostkowe, jeden, gdzie AllocateQubit jest wykonywany w QuantumSimulator i jeden, gdzie jest wykonywany w ResourceEstimator. 

Kompilator Q # rozpoznaje wbudowane elementy docelowe "QuantumSimulator", "ToffoliSimulator" i "ResourcesEstimator" jako prawidłowe cele wykonywania dla testów jednostkowych. Istnieje również możliwość określenia dowolnej w pełni kwalifikowanej nazwy, aby zdefiniować niestandardowy cel wykonania. 

### <a name="running-q-unit-tests"></a>Uruchamianie testów jednostkowych Q #

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Jako jednorazowe skonfigurowanie poszczególnych rozwiązań przejdź do `Test` menu i wybierz opcję `Test Settings`  >  `Default Processor Architecture`  >  `X64` .

> [!TIP]
> Domyślne ustawienie architektury procesora dla programu Visual Studio jest przechowywane w pliku opcji rozwiązania ( `.suo` ) dla każdego rozwiązania.
> W przypadku usunięcia tego pliku należy `X64` ponownie wybrać swoją architekturę procesora.

Skompiluj projekt, przejdź do `Test` menu i wybierz opcję `Windows`  >  `Test Explorer` . `AllocateQubit`zostanie wyświetlony na liście testów w `Not Run Tests` grupie. Wybierz `Run All` lub Uruchom ten test indywidualny, który powinien zostać przekazany!

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

Aby uruchomić testy, przejdź do folderu projektu (folder zawierający `Tests.csproj` ) i wykonaj polecenie:

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

Wewnętrzna funkcja <xref:microsoft.quantum.intrinsic.message> ma typ `(String -> Unit)` i umożliwia tworzenie komunikatów diagnostycznych.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Po wykonaniu testu w Eksploratorze testów i kliknięciu testu zostanie wyświetlony panel z informacjami o wykonywaniu testów: stanie zakończonych niepowodzeniem, czas, który upłynął, i link "output". Kliknięcie linku "output" spowoduje otwarcie danych wyjściowych testu w nowym oknie.

![dane wyjściowe testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

Stan przekazywania/niepowodzenia dla każdego testu jest drukowany w konsoli przez `dotnet test` .
W przypadku niepowodzeń testów są one również drukowane w konsoli programu w celu ułatwienia zdiagnozowania błędu.

***

## <a name="facts-and-assertions"></a>Fakty i potwierdzenia

Ponieważ funkcje w Q # nie mają _logicznych_ efektów ubocznych, wszelkie _Inne rodzaje_ efektów wykonywania funkcji, której typem danych wyjściowych jest pusta krotka, `()` nie można nigdy zaobserwować w programie Q #.
Oznacza to, że komputer docelowy może zrezygnować z wykonywania jakiejkolwiek funkcji, która zwraca `()` z gwarancją, że to pominięcie nie zmodyfikuje zachowania żadnego z następujących kodów Q #.
Dzięki temu funkcje zwracają `()` (tj. `Unit` ) użyteczne narzędzie do osadzania potwierdzeń i logiki debugowania do programów Q #. 

Rozważmy prosty przykład:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

W tym miejscu słowo kluczowe `fail` wskazuje, że obliczenia nie powinny być wykonywane, a na komputerze docelowym, na którym jest uruchomiony program Q #, zostanie zwrócony wyjątek.
Według definicji nie można zaobserwować błędu tego rodzaju z poziomu Q #, ponieważ po osiągnięciu instrukcji nie jest uruchamiany żaden dodatkowy kod Q # `fail` .
W takim przypadku, jeśli będziemy przechodzić do wcześniejszego wywołania `PositivityFact` , możemy zapewnić, że jego dane wejściowe były dodatnie.

Należy pamiętać, że możemy zaimplementować takie samo zachowanie, jak `PositivityFact` Używanie [`Fact`](xref:microsoft.quantum.diagnostics.fact) funkcji z <xref:microsoft.quantum.diagnostics> przestrzeni nazw:

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

Z drugiej strony, *potwierdzenia*są używane podobnie do faktów, ale mogą być zależne od stanu maszyny docelowej. Są one odpowiednio zdefiniowane jako operacje, a fakty są definiowane jako funkcje (jak powyżej).
Aby zrozumieć rozróżnienie, należy rozważyć następujące użycie faktu w ramach potwierdzenia:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

W tym miejscu używamy operacji <xref:microsoft.quantum.environment.getqubitsavailabletouse> do zwrócenia liczby qubits dostępnych do użycia.
Ponieważ to wyraźnie zależy od stanu globalnego programu i jego środowiska wykonawczego, definicja `AssertQubitsAreAvailable` musi być operacją.
Można jednak użyć tego stanu globalnego, aby dać prostą `Bool` wartość jako dane wejściowe do `Fact` funkcji.

W oparciu o te pomysły [Preludium](xref:microsoft.quantum.libraries.standard.prelude) oferuje dwie szczególnie przydatne potwierdzenia <xref:microsoft.quantum.intrinsic.assert> i są <xref:microsoft.quantum.intrinsic.assertprob> modelowane jako operacje na `()` . Każdy z tych zatwierdzeń przyjmuje operatora Pauli opisujące konkretną miarę zainteresowania, rejestr Quantum, na którym ma zostać wykonane pomiary, i hipotetyczny wynik.
Na komputerach docelowych, które współpracują przez symulację, nie są one powiązane z [theoremem bez klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem)i mogą wykonywać takie pomiary bez zakłócania rejestracji przesłanej do takich potwierdzeń.
Symulator może następnie, podobnie jak `PositivityFact` powyżej, przerwać obliczenia, jeśli hipotetyczny wynik nie zostanie zaobserwowany w praktyce:

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

Na fizycznym sprzęcie Quantum, gdzie theorem No-kloning uniemożliwia badanie stanu Quantum, `Assert` `AssertProb` operacje i po prostu zwracają `()` bez żadnego skutku.

<xref:microsoft.quantum.diagnostics>Przestrzeń nazw udostępnia kilka funkcji `Assert` rodziny, które pozwalają nam sprawdzić bardziej zaawansowane warunki. 

## <a name="dump-functions"></a>Funkcje zrzutu

Aby ułatwić rozwiązywanie problemów z programami Quantum, <xref:microsoft.quantum.diagnostics> przestrzeń nazw oferuje dwie funkcje, które mogą zrzutować do pliku bieżący stan maszyny docelowej: <xref:microsoft.quantum.diagnostics.dumpmachine> i <xref:microsoft.quantum.diagnostics.dumpregister> . Wygenerowane dane wyjściowe każdego z nich są zależne od maszyny docelowej.

### <a name="dumpmachine"></a>DumpMachine

Kompleksowy symulator Quantum dystrybuowany w ramach zestawu Quantum Development Kit zapisuje w pliku [funkcję Wave](https://en.wikipedia.org/wiki/Wave_function) całego systemu Quantum jako tablicę jednowymiarową liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru stanu podstawy obliczeniowej $ \ket{n} $, gdzie $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ dla usługi BITS $ \{ b_i \} $. Na przykład na komputerze z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ wywołujący <xref:microsoft.quantum.diagnostics.dumpmachine> generuje te dane wyjściowe:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

Pierwszy wiersz zawiera komentarz z identyfikatorami odpowiednich qubits w ich znaczącej kolejności.
Pozostała część wierszy zawiera opis amplitudy prawdopodobieństwa pomiaru wektora stanu \ket{n} $ w obu formatach kartezjańskiego i biegunowych. Szczegółowo dla pierwszego wiersza:

* **`∣0❭:`** Ten wiersz odnosi się do `0` stanu podstawy obliczeń
* **`0.707107 +  0.000000 i`**: amplituda prawdopodobieństwa w formacie kartezjańskiego.
* **` == `**: znak oddzieli `equal` obie równoważne reprezentacje.
* **`**********  `**: Graficzna reprezentacja rozmiaru, liczba `*` jest proporcjonalna do prawdopodobieństwa mierzenia tego wektora stanu.
* **`[ 0.500000 ]`**: wartość liczbowa wielkości
* **`    ---`**: Graficzna reprezentacja fazy amplitudy (patrz poniżej).
* **`[ 0.0000 rad ]`**: wartość liczbowa fazy (w radianach).

Obie wartości i fazy są wyświetlane ze graficzną reprezentacją. Reprezentacja wielkości jest przesunięta do przodu: pokazuje pasek, tym większe prawdopodobieństwo powyższego poziomu `*` . Dla fazy pokazywane są następujące symbole reprezentujące kąt na podstawie zakresów:

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

W poniższych przykładach przedstawiono `DumpMachine` niektóre typowe Stany:

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


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Identyfikator qubit można ustalić w programie Visual Studio, umieszczając punkt przerwania w kodzie i sprawdzając wartość zmiennej qubit, na przykład:
  > 
  > ![Pokaż identyfikator qubit w programie Visual Studio](~/media/qubit_id.png)
  >
  > qubit z indeksem `0` o `register2` identyfikatorze = `3` , qubit z indeksem `1` ma identyfikator = `2` .

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Identyfikator qubit można ustalić przy użyciu <xref:microsoft.quantum.intrinsic.message> funkcji i przekazywać zmienną qubit w komunikacie, na przykład:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > który może generować następujące dane wyjściowe:
  >```
  > 0=q:3; 1=q:2
  >```
  > co oznacza, że qubit z indeksem `0` `register2` ma identyfikator = `3` , qubit z indeksem `1` ma identyfikator = `2` .


***

<xref:microsoft.quantum.diagnostics.dumpmachine>jest częścią <xref:microsoft.quantum.diagnostics> przestrzeni nazw, więc aby można było jej używać, należy dodać `open` instrukcję:

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

<xref:microsoft.quantum.diagnostics.dumpregister>działa jak <xref:microsoft.quantum.diagnostics.dumpmachine> , z tym wyjątkiem, że pobiera również tablicę qubits w celu ograniczenia ilości informacji tylko w odniesieniu do odpowiednich qubits.

Podobnie jak w przypadku <xref:microsoft.quantum.diagnostics.dumpmachine> , informacje generowane przez program <xref:microsoft.quantum.diagnostics.dumpregister> są zależne od maszyny docelowej. W przypadku kompleksowego symulatora Quantum zapisuje w pliku funkcję Wave do globalnej fazy podsystemu Quantum wygenerowanego przez podaną qubits w tym samym formacie co <xref:microsoft.quantum.diagnostics.dumpmachine> .  Na przykład wykonaj ponownie maszynę z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ Pi/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ wywołujący <xref:microsoft.quantum.diagnostics.dumpregister> dla `qubit[0]` wygenerowało następujące dane wyjściowe:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

i wywołanie <xref:microsoft.quantum.diagnostics.dumpregister> metody `qubit[1]` generuje następujące dane wyjściowe:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Ogólnie rzecz biorąc, stan rejestru Entangled z innym rejestrem jest stanem mieszanym, a nie czystym. W takim przypadku <xref:microsoft.quantum.diagnostics.dumpregister> wyświetla następujący komunikat:

```
Qubits provided (0;) are entangled with some other qubit.
```

Poniższy przykład pokazuje, jak można używać obu <xref:microsoft.quantum.diagnostics.dumpregister> i <xref:microsoft.quantum.diagnostics.dumpmachine> w kodzie Q:

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

W oparciu o `Assert` i `Dump` funkcje i operacje, funkcja Q # obsługuje podzbiór standardowych możliwości debugowania programu Visual Studio: [ustawianie punktów przerwania linii](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokowe wykonywanie kodu przy użyciu](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) klawisza F10 i [Sprawdzanie wartości zmiennych klasycznych](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) jest możliwe podczas wykonywania kodu w symulatorze.

Debugowanie w Visual Studio Code wykorzystuje funkcje debugowania dostępne w języku C# dla rozszerzenia Visual Studio Code obsługiwanego przez OmniSharp i wymaga zainstalowania [najnowszej wersji](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 

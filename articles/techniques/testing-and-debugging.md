---
title: Testowanie i debugowanie programów Q#
description: Dowiedz się, jak używać testów jednostkowych, faktów i potwierdzeń oraz funkcji zrzutu do testowania i debugowania programów kwantowych.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030586"
---
# <a name="testing-and-debugging"></a>Testowanie i debugowanie

Podobnie jak w przypadku programowania klasycznego, ważne jest, aby móc sprawdzić, czy programy kwantowe działają zgodnie z przeznaczeniem, i być w stanie zdiagnozować program kwantowy, który jest nieprawidłowy.
W tej sekcji omówimy narzędzia oferowane przez Q# do testowania i debugowania programów kwantowych.

## <a name="unit-tests"></a>Testy jednostkowe

Jednym z typowych podejść do testowania klasycznych programów jest pisanie małych programów zwanych *testami jednostkowymi,* które uruchamiają kod w bibliotece i porównuje jego dane wyjściowe z oczekiwanymi wyjściami.
Na przykład możemy chcieć `Square(2)` zapewnić, że zwraca `4`, ponieważ wiemy *a priori,* że $2^2 = 4$.

Q# obsługuje tworzenie testów jednostkowych dla programów kwantowych i które mogą być wykonywane jako testy w ramach testowania [jednostki xUnit.](https://xunit.github.io/)

### <a name="creating-a-test-project"></a>Tworzenie projektu testowego

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Otwórz program Visual Studio 2019. Przejdź do `File` menu `New`  >  `Project...`i wybierz opcję .
W prawym górnym rogu `Q#`wyszukaj `Q# Test Project` i wybierz szablon.

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

W ulubionym wierszu polecenia uruchom następujące polecenie:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Nowy projekt będzie miał `Tests.qs`jeden plik, który zapewnia wygodne miejsce do definiowania nowych testów jednostkowych Q#.
Początkowo ten plik zawiera `AllocateQubit` jeden przykładowy test jednostkowy, który sprawdza,{0}czy nowo przydzielony kubit jest w stanie $\ket $ i drukuje komunikat:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: Każda operacja lub funkcja Q#, `Unit` która `Unit` przyjmuje argument typu i `@Test("...")` zwraca, może być oznaczona jako test jednostkowy za pomocą atrybutu. Argument do tego atrybutu, `"QuantumSimulator"` powyżej, określa cel, na którym test jest wykonywany. Pojedynczy test może być wykonany na wielu obiektów docelowych. Na przykład dodaj atrybut `@Test("ResourcesEstimator")` `AllocateQubit`powyżej . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Zapisz plik i wykonaj wszystkie testy. Teraz powinny być dwa testy jednostkowe, jeden, gdzie AllocateQubit jest wykonywany na QuantumSimulator i jeden, gdzie jest wykonywany w ResourceEstimator. 

Kompilator Q# rozpoznaje wbudowane obiekty docelowe "QuantumSimulator", "ToffoliSimulator" i "ResourcesEstimator" jako prawidłowe cele wykonania dla testów jednostkowych. Istnieje również możliwość określenia dowolnej w pełni kwalifikowanej nazwy, aby zdefiniować niestandardowy cel wykonania. 

### <a name="running-q-unit-tests"></a>Uruchamianie testów jednostkowych Q#

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Jako jednorazowa konfiguracja na rozwiązanie `Test` przejdź do `Test Settings`  >  `Default Processor Architecture`  >  `X64`menu i wybierz opcję .

> [!TIP]
> Domyślne ustawienie architektury procesora dla programu Visual`.suo`Studio jest przechowywane w pliku opcji rozwiązania ( ) dla każdego rozwiązania.
> Jeśli usuniesz ten plik, `X64` musisz ponownie wybrać jako architekturę procesora.

Zbuduj projekt, przejdź `Test` do menu `Windows`  >  `Test Explorer`i wybierz . `AllocateQubit`pojawi się na liście testów `Not Run Tests` w grupie. Wybierz `Run All` lub uruchom ten indywidualny test, a powinien on przejść!

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

Aby uruchomić testy, przejdź do folderu `Tests.csproj`projektu (folderu, który zawiera) i wykonaj polecenie:

```bash
$ dotnet restore
$ dotnet test
```

Powinieneś uzyskać dane wyjściowe podobne do następujących:

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

Testy jednostkowe mogą być filtrowane zgodnie z ich nazwą i/lub celem wykonania:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

Funkcja <xref:microsoft.quantum.intrinsic.message> wewnętrzna ma typ `(String -> Unit)` i umożliwia tworzenie komunikatów diagnostycznych.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Po wykonaniu testu w Eksploratorze testów i kliknięciu testu pojawi się panel z informacjami o wykonaniu testu: Stan przekazany/Nieudany, czas, który upłynął i łącze "Dane wyjściowe". Jeśli klikniesz łącze "Dane wyjściowe", dane wyjściowe testu otworzą się w nowym oknie.

![wyjście testowe](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

Stan przebiegu/niepowodzenia dla każdego testu jest `dotnet test`drukowany na konsoli przez .
W przypadku testów, które nie po awarii są również drukowane na konsoli, aby ułatwić diagnozowanie awarii.

***

## <a name="facts-and-assertions"></a>Fakty i twierdzenia

Ponieważ funkcje w Q# nie mają _żadnych skutków_ ubocznych logiczne, wszelkie inne `()` _rodzaje_ efektów wykonywania funkcji, których typ wyjściowy jest pustą krotki nigdy nie można zaobserwować z poziomu programu Q#.
Oznacza to, że komputer docelowy może zdecydować `()` się nie wykonywać żadnej funkcji, która zwraca z gwarancją, że to pominięcie nie zmodyfikuje zachowanie żadnego następującego kodu Q#.
To sprawia, `()` że funkcje `Unit`zwracające (tj. ) przydatne narzędzie do osadzania potwierdzeń i debugowania logiki w programach Q#. 

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

W tym `fail` miejscu słowo kluczowe wskazuje, że obliczenia nie powinny być kontynuowane, zgłaszając wyjątek na komputerze docelowym z uruchomionym programem Q#.
Z definicji nie można zaobserwować błędu tego rodzaju z poziomu Q#, `fail` ponieważ po osiągnięciu instrukcji nie jest uruchamiany żaden kod Q#.
Tak więc, jeśli przejdziemy `PositivityFact`obok wezwania do , możemy być pewni, że jego wkład był pozytywny.

Należy zauważyć, że możemy `PositivityFact` zaimplementować takie samo zachowanie jak przy użyciu [`Fact`](xref:microsoft.quantum.diagnostics.fact) funkcji z obszaru <xref:microsoft.quantum.diagnostics> nazw:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

*Twierdzenia*, z drugiej strony, są używane podobnie do faktów, ale mogą być zależne od stanu maszyny docelowej. Odpowiednio, są one definiowane jako operacje, podczas gdy fakty są definiowane jako funkcje (jak powyżej).
Aby zrozumieć rozróżnienie, należy wziąć pod uwagę następujące użycie faktu w asercji:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

W tym miejscu używamy <xref:microsoft.quantum.environment.getqubitsavailabletouse> operacji, aby zwrócić liczbę kubitów dostępnych do użycia.
Ponieważ to wyraźnie zależy od globalnego stanu programu i jego `AssertQubitsAreAvailable` środowiska wykonywania, nasza definicja musi być również operacją.
Jednak możemy użyć tego stanu globalnego, `Bool` aby uzyskać `Fact` prostą wartość jako dane wejściowe do funkcji.

Opierając się na tych pomysłach, [preludium](xref:microsoft.quantum.libraries.standard.prelude) <xref:microsoft.quantum.intrinsic.assertprob> oferuje dwa szczególnie `()`przydatne twierdzenia, <xref:microsoft.quantum.intrinsic.assert> a oba wzorowane na operacjach na . Twierdzenia te obejmują operatora Pauliego opisującego konkretny pomiar zainteresowania, rejestr kwantowy, na którym ma być wykonany pomiar, oraz hipotetyczny wynik.
Na maszynach docelowych, które działają za pomocą symulacji, nie jesteśmy związani [twierdzeniem o braku klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem)i możemy wykonywać takie pomiary bez zakłócania rejestru przekazywanego do takich twierdzeń.
Symulator może następnie, podobnie `PositivityFact` jak funkcja powyżej, przerwać obliczenia, jeśli hipotetyczny wynik nie będzie przestrzegany w praktyce:

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

Na fizycznym sprzęcie kwantowym, gdzie teoria o braku `Assert` klonowania uniemożliwia badanie stanu kwantowego, operacje i `AssertProb` operacje po prostu wracają `()` bez innego efektu.

Obszar <xref:microsoft.quantum.diagnostics> nazw oferuje kilka innych `Assert` funkcji rodziny, które pozwalają nam sprawdzić bardziej zaawansowane warunki. 

## <a name="dump-functions"></a>Funkcje zrzutu

Aby ułatwić rozwiązywanie problemów <xref:microsoft.quantum.diagnostics> z programami kwantowymi, obszar nazw oferuje dwie funkcje, które mogą zrzucić do pliku bieżący stan komputera docelowego: <xref:microsoft.quantum.diagnostics.dumpmachine> i <xref:microsoft.quantum.diagnostics.dumpregister>. Wygenerowane dane wyjściowe każdego zależy od maszyny docelowej.

### <a name="dumpmachine"></a>DumpMachine

Pełnostanowy symulator kwantowy dystrybuowany jako część Quantum Development Kit zapisuje w pliku [funkcję fali](https://en.wikipedia.org/wiki/Wave_function) całego systemu kwantowego, jako jednowymiarową tablicę liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru stanu podstawy obliczeniowej $\ket{n}$, gdzie $\ket{n} = \ket{b_{n-1}... b_1b_0}$ dla bitów\{$ b_i\}$. Na przykład na komputerze z przydzielonymi tylko dwoma kubitami i w stanie kwantowym $$ \begin{align} \ket{\psi}{1}= \frac {\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ wywołanie <xref:microsoft.quantum.diagnostics.dumpmachine> generuje to dane wyjściowe:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

Pierwszy wiersz zawiera komentarz z identyfikatorami odpowiednich kubitów w ich znaczącej kolejności.
W pozostałych wierszach opisano amplitudę prawdopodobieństwa pomiaru wektora stanu podstawy $\ket{n}$ zarówno w formacie kartezjańskim, jak i biegunowym. W szczegółach dla pierwszego rzędu:

* **`∣0❭:`** ten wiersz odpowiada `0` obliczonemu stanowi podstawy
* **`0.707107 +  0.000000 i`**: amplituda prawdopodobieństwa w formacie kartezjańskim.
* **` == `**: `equal` znak oddziela obie równoważne reprezentacje.
* **`**********  `**: Graficzna reprezentacja wielkości, liczba `*` jest proporcjonalna do prawdopodobieństwa pomiaru tego wektora stanu.
* **`[ 0.500000 ]`**: wartość liczbowa wielkości
* **`    ---`**: graficzna reprezentacja fazy amplitudy (patrz poniżej).
* **`[ 0.0000 rad ]`**: wartość liczbową fazy (w radianach).

Zarówno wielkość, jak i faza są wyświetlane z graficzną reprezentacją. Reprezentacja wielkości jest prosta: pokazuje pasek `*`, im większe prawdopodobieństwo, tym większe będzie pasek. Dla fazy pokazujemy następujące symbole reprezentujące kąt na podstawie zakresów:

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

Poniższe przykłady `DumpMachine` pokazują dla niektórych wspólnych stanów:

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
  > Identyfikator kubitu jest przypisywany w czasie wykonywania i nie jest koniecznie wyrównany z kolejnością, w której kubit został przydzielony lub jego położeniem w rejestrze kubitów.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Można wymyślić identyfikator kubitu w programie Visual Studio, umieszczając punkt przerwania w kodzie i sprawdzając wartość zmiennej kubitowej, na przykład:
  > 
  > ![pokaż identyfikator kubitu w programie Visual Studio](~/media/qubit_id.png)
  >
  > kubit z `0` indeksem na `register2` `3`has id= `1` , kubit`2`z indeksem ma id = .

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Możesz wymyślić identyfikator kubitu za <xref:microsoft.quantum.intrinsic.message> pomocą funkcji i przekazując zmienną kubitową w wiadomości, na przykład:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > które mogłyby wygenerować ten wynik:
  >```
  > 0=q:3; 1=q:2
  >```
  > co `0` oznacza, że kubit `register2` z indeksem na ma id =`3`, kubit z indeksem `1` ma id =`2`.


***

<xref:microsoft.quantum.diagnostics.dumpmachine>jest częścią <xref:microsoft.quantum.diagnostics> obszaru nazw, więc aby go użyć, `open` należy dodać instrukcję:

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

<xref:microsoft.quantum.diagnostics.dumpregister>działa <xref:microsoft.quantum.diagnostics.dumpmachine>jak , z wyjątkiem to również wymaga tablicy kubitów, aby ograniczyć ilość informacji tylko do tych istotnych dla odpowiednich kubitów.

Podobnie <xref:microsoft.quantum.diagnostics.dumpmachine>jak w , <xref:microsoft.quantum.diagnostics.dumpregister> informacje generowane przez zależy od maszyny docelowej. Dla pełnego stanu symulator kwantowy zapisuje do pliku funkcji fali do globalnej fazy sub-systemu kwantowego generowane przez <xref:microsoft.quantum.diagnostics.dumpmachine>dostarczone kubity w tym samym formacie co .  Na{1}przykład, weź ponownie maszynę z przydzielonymi tylko dwoma kubitami i w stanie kwantowym $$ \begin{align}{2}\ket{\psi} = \frac {\sqrt }{00} \ket - \frac{(1 +{2} i)} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)} `qubit[0]` {2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ wywołanie <xref:microsoft.quantum.diagnostics.dumpregister> generuje to dane wyjściowe:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

i <xref:microsoft.quantum.diagnostics.dumpregister> wzywając `qubit[1]` do generuje ten wynik:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Ogólnie rzecz biorąc stan rejestru, który jest uwikłany w inny rejestr jest stan mieszany, a nie czysty. W takim <xref:microsoft.quantum.diagnostics.dumpregister> przypadku wysyła następujący komunikat:

```
Qubits provided (0;) are entangled with some other qubit.
```

Poniższy przykład pokazuje, jak <xref:microsoft.quantum.diagnostics.dumpregister> można <xref:microsoft.quantum.diagnostics.dumpmachine> używać zarówno w kodzie Q#:

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

Na początku `Assert` `Dump` i funkcje i operacje, Q# obsługuje podzbiór standardowych funkcji debugowania programu Visual Studio: [ustawianie punktów przerwania linii, przechodzenie](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints) [przez kod przy użyciu F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) i sprawdzanie wartości [zmiennych klasycznych](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) są możliwe podczas wykonywania kodu w symulatorze.

Debugowanie w programie Visual Studio Code wykorzystuje możliwości debugowania udostępniane przez rozszerzenie kodu programu Visual Studio c# obsługiwane przez omnisharp i wymaga zainstalowania [najnowszej wersji.](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) 

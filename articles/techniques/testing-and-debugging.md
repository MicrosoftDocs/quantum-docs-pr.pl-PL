---
title: 'Techniki Q # — testowanie i debugowanie | Microsoft Docs'
description: 'Techniki Q # — testowanie i debugowanie'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183492"
---
# <a name="testing-and-debugging"></a>Testowanie i debugowanie

Podobnie jak w przypadku klasycznego programowania, konieczna jest możliwość sprawdzenia, czy programy Quantum działają zgodnie z oczekiwaniami, i aby można było zdiagnozować program Quantum, który jest nieprawidłowy.
W tej sekcji omówiono narzędzia oferowane przez Q # do testowania i debugowania programów Quantum.

## <a name="unit-tests"></a>Testy jednostkowe

Typowym podejściem do testowania klasycznych programów jest pisanie małych programów o nazwie *testy jednostkowe* , które uruchamiają kod w bibliotece i porównując dane wyjściowe z nieoczekiwanymi wynikami.
Na przykład firma Microsoft może chcieć upewnić się, że `Square(2)` zwraca `4`, ponieważ *wiemy, że* $2 ^ 2 = $4.

Polecenie Q # obsługuje tworzenie testów jednostkowych dla programów Quantum i które mogą być wykonywane jako testy w ramach struktury testów jednostkowych [xUnit](https://xunit.github.io/) .

### <a name="creating-a-test-project"></a>Tworzenie projektu testowego

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Program Visual Studio 2019](#tab/tabid-vs2019)

Otwórz program Visual Studio 2019. Przejdź do menu `File` i wybierz pozycję `New` > `Project...`.
W Eksploratorze szablonów projektu w obszarze `Installed` > `Visual C#`wybierz szablon `Q# Test Project`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

W ulubionym wierszu polecenia Uruchom następujące polecenie:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

W obu przypadkach nowy projekt będzie miał otwarte dwa pliki.
Pierwszy plik, `Tests.qs`, zapewnia wygodne miejsce do definiowania nowych testów pytań typu "Q #".
Początkowo ten plik zawiera jeden przykładowy test jednostkowy `AllocateQubitTest`, który sprawdza, czy nowo przydzieloną qubit znajduje się w stanie $ \ket{0}$ i drukuje komunikat:

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Wszelkie operacje Q # zgodne z typem `(Unit => Unit)` lub funkcją zgodną z `(Unit -> Unit)` można wykonać jako test jednostkowy. 

Drugi plik, `TestSuiteRunner.cs` zawiera metodę, która odnajduje i uruchamia testy jednostkowe Q #. Jest to metoda `TestTarget` Adnotacja z atrybutem `OperationDriver`.
Atrybut `OperationDriver` jest częścią biblioteki rozszerzeń xUnit Microsoft. Quantum. Symulacja. xUnit.
Struktura testowania jednostkowego wywołuje `TestTarget` metody dla każdego testu jednostki Q #, który został odnaleziony.
Struktura przekazuje opis testu jednostkowego do metody za pomocą argumentu `op`. Następujący wiersz kodu:
```csharp
op.TestOperationRunner(sim);
```
wykonuje test jednostkowy na `QuantumSimulator`.

Domyślnie mechanizm odnajdywania testów jednostkowych szuka wszystkich funkcji Q # lub operacji typu zgodnego, które spełniają następujące właściwości:
* Znajduje się w tym samym zestawie, co metoda oznaczona adnotacją z atrybutem `OperationDriver`.
* Znajduje się w tej samej przestrzeni nazw co metoda z adnotacją `OperationDriver` atrybutu.
* Ma nazwę kończącą się na `Test`.

Zestaw, przestrzeń nazw i sufiks dla funkcji testów jednostkowych i operacji można ustawić przy użyciu opcjonalnych parametrów `OperationDriver` atrybutu:
* parametr `AssemblyName` ustawia nazwę zestawu, który jest wyszukiwany dla testów.
* parametr `TestNamespace` ustawia nazwę przestrzeni nazw, która jest wyszukiwana dla testów.
* `Suffix` ustawia sufiks nazw operacji lub funkcji, które są uznawane za testy jednostkowe.

Ponadto opcjonalny parametr `TestCasePrefix` umożliwia ustawienie prefiksu dla nazwy przypadku testowego. Prefiks przed nazwą operacji pojawi się na liście przypadków testowych. Na przykład `TestCasePrefix = "QSim:"` spowoduje, że `AllocateQubitTest` pojawić się jako `QSim:AllocateQubitTest` na liście znalezionych testów. Może to być przydatne do wskazania na przykład, który symulator jest używany do uruchomienia testu.

### <a name="running-q-unit-tests"></a>Uruchamianie testów jednostkowych Q #

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Program Visual Studio 2019](#tab/tabid-vs2019)

Jako jednorazowe skonfigurowanie poszczególnych rozwiązań przejdź do menu `Test` i wybierz `Test Settings` > `Default Processor Architecture` > `X64`.

> [!TIP]
> Domyślne ustawienie architektury procesora dla programu Visual Studio jest przechowywane w pliku opcji rozwiązania (`.suo`) dla każdego rozwiązania.
> W przypadku usunięcia tego pliku należy ponownie wybrać `X64` jako architekturę procesora.

Skompiluj projekt, przejdź do menu `Test` i wybierz pozycję `Windows` > `Test Explorer`. `AllocateQubitTest` zostanie wyświetlona na liście testów w grupie `Not Run Tests`. Wybierz `Run All` lub Uruchom ten test indywidualny, który powinien zostać przekazany!

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

***

## <a name="logging-and-assertions"></a>Rejestrowanie i potwierdzenia

Jedną z ważnych konsekwencji, że funkcje w Q # nie mają żadnych efektów ubocznych, jest to, że wszystkie efekty wykonywania funkcji, której typem danych wyjściowych jest pusta krotka `()` nie mogą być obserwowane w ramach programu Q #.
Oznacza to, że komputer docelowy może nie wykonywać żadnej funkcji, która zwraca `()` z gwarancją, że to pominięcie nie zmodyfikuje zachowania żadnego z następujących kodów Q #.
Dzięki temu funkcje zwracają `()` użytecznym narzędziem do osadzania potwierdzeń i logiki debugowania do programów Q #. 

### <a name="logging"></a>Rejestrowanie

Funkcja wewnętrzna <xref:microsoft.quantum.intrinsic.message> ma typ `(String -> Unit)` i umożliwia tworzenie komunikatów diagnostycznych.

Akcja `onLog` `QuantumSimulator` może służyć do definiowania akcji wykonywanych w przypadku wywołania kodu Q # `Message`. Domyślnie zarejestrowane komunikaty są drukowane w standardowym wyjściu.

Podczas definiowania zestawu testów jednostkowych, zarejestrowane komunikaty można skierować do danych wyjściowych testu. Gdy projekt jest tworzony na podstawie szablonu projektu testowego Q #, to przekierowanie jest wstępnie skonfigurowane dla pakietu i domyślnie utworzone w następujący sposób:

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Program Visual Studio 2019](#tab/tabid-vs2019)

Po wykonaniu testu w Eksploratorze testów i kliknięciu testu zostanie wyświetlony panel z informacjami o wykonywaniu testów: stanie zakończonych niepowodzeniem, czas, który upłynął, i link "output". Kliknięcie linku "output" spowoduje otwarcie danych wyjściowych testu w nowym oknie.

![dane wyjściowe testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

Stan przekazywania/niepowodzenia dla każdego testu jest drukowany w konsoli programu przez `dotnet test`.
W przypadku niepowodzeń testów dane wyjściowe zarejestrowane w wyniku wywołania `output.WriteLine(msg)` powyżej są również drukowane w konsoli programu w celu ułatwienia zdiagnozowania błędu.

***

### <a name="assertions"></a>Asercje

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

Kompleksowy symulator Quantum dystrybuowany w ramach zestawu Quantum Development Kit zapisuje w pliku [funkcję Wave](https://en.wikipedia.org/wiki/Wave_function) całego systemu Quantum jako tablicę jednowymiarową liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwo pomiaru stanu podstawy obliczeniowej $ \ket{n} $, gdzie $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ dla BITS $\{b_i\}$. Na przykład na komputerze z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ wywołując <xref:microsoft.quantum.diagnostics.dumpmachine> generuje te dane wyjściowe :

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


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Program Visual Studio 2019](#tab/tabid-vs2019)

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

Podobnie jak w przypadku <xref:microsoft.quantum.diagnostics.dumpmachine>, informacje generowane przez <xref:microsoft.quantum.diagnostics.dumpregister> są zależne od maszyny docelowej. W przypadku kompleksowego symulatora Quantum zapisuje w pliku funkcję Wave do globalnej fazy podsystemu Quantum wygenerowanego przez podaną qubits w tym samym formacie co <xref:microsoft.quantum.diagnostics.dumpmachine>.  Na przykład należy ponownie wykonać maszynę z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ Pi/4} ((\frac{1}{\sqrt{2}} \ KET{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ wywołując <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generuje te dane wyjściowe:

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

W oparciu o `Assert` i `Dump` funkcje i operacje, funkcja Q # obsługuje podzbiór standardowych możliwości debugowania programu Visual Studio: [ustawianie punktów przerwania linii](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokowe wykonywanie kodu przy użyciu języka F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) i [Sprawdzanie wartości zmiennych klasycznych ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)są one możliwe podczas wykonywania kodu w symulatorze.

Debugowanie w Visual Studio Code nie jest jeszcze obsługiwane.


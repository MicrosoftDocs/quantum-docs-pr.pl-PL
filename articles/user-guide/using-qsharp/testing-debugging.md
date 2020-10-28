---
title: Testowanie i debugowanie
description: Dowiedz się, jak korzystać z testów jednostkowych, faktów i potwierdzeń oraz funkcji zrzutów do testowania i debugowania programów Quantum.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5505086c5efac89f6940cde1ecae2ce629cfeda5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690970"
---
# <a name="testing-and-debugging"></a>Testowanie i debugowanie

Podobnie jak w przypadku klasycznego programowania, konieczna jest możliwość sprawdzenia, czy programy Quantum działają zgodnie z oczekiwaniami, i aby można było zdiagnozować nieprawidłowe zachowanie.
W tej sekcji omówiono narzędzia oferowane przez Q# program do testowania i debugowania programów Quantum.

## <a name="unit-tests"></a>Testy jednostkowe

Typowym podejściem do testowania klasycznych programów jest pisanie małych programów o nazwie *testy jednostkowe* , które uruchamiają kod w bibliotece i porównując dane wyjściowe z nieoczekiwanymi wynikami.
Można na przykład upewnić się, że `Square(2)` funkcja zwróci wartość, `4` ponieważ wiesz, że $2 ^ 2 = $4. *a priori*

Q# obsługuje tworzenie testów jednostkowych dla programów Quantum, które mogą być uruchamiane jako testy w ramach struktury testów jednostkowych [xUnit](https://xunit.github.io/) .

### <a name="creating-a-test-project"></a>Tworzenie projektu testowego

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Otwórz program Visual Studio 2019. Przejdź do menu **plik** i wybierz pozycję **Nowy > projekt..** .. W prawym górnym rogu Wyszukaj `Q#` i wybierz szablon **Q# projektu testowego** .

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

W ulubionym wierszu polecenia Uruchom następujące polecenie:
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Nowy projekt zawiera jeden plik `Tests.qs` , który zapewnia wygodne miejsce do definiowania nowych Q# testów jednostkowych.
Początkowo ten plik zawiera jeden przykładowy test jednostkowy, `AllocateQubit` który sprawdza, czy nowo przydzieloną qubit znajduje się w {0} stanie $ \ket $ i drukuje komunikat:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Każda Q# operacja lub funkcja, która przyjmuje argument typu `Unit` i Returns, `Unit` może być oznaczona jako test jednostkowy za pośrednictwem `@Test("...")` atrybutu. W poprzednim przykładzie argument dla tego atrybutu, `"QuantumSimulator"` określa obiekt docelowy, na którym przebiega testy. Pojedynczy test można uruchomić na wielu celach. Na przykład Dodaj atrybut `@Test("ResourcesEstimator")` przed `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Zapisz plik i uruchom wszystkie testy. Istnieją teraz dwa testy jednostkowe, jeden, gdzie `AllocateQubit` działa w `QuantumSimulator` programie, i jeden, gdzie działa w `ResourcesEstimator` . 

Q#Kompilator rozpoznaje wbudowane elementy docelowe `"QuantumSimulator"` , `"ToffoliSimulator"` i `"ResourcesEstimator"` jako prawidłowe elementy docelowe przebiegu dla testów jednostkowych. Istnieje również możliwość określenia dowolnej w pełni kwalifikowanej nazwy, aby zdefiniować niestandardowy cel uruchomienia. 

### <a name="running-no-locq-unit-tests"></a>Uruchamianie Q# testów jednostkowych

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

W ramach jednorazowej konfiguracji dla poszczególnych rozwiązań przejdź do menu **test** , a następnie wybierz pozycję **Ustawienia testu > domyślna architektura procesora > x64** .

> [!TIP]
> Domyślne ustawienie architektury procesora dla programu Visual Studio jest przechowywane w pliku opcji rozwiązania ( `.suo` ) dla każdego rozwiązania.
> W przypadku usunięcia tego pliku należy ponownie wybrać **procesor x64** jako architekturę procesora.

Skompiluj projekt, otwórz menu **test** i wybierz pozycję **Windows > Test Explorer** . **AllocateQubit** jest wyświetlana na liście testów w grupie **nie uruchomiono testów** . Wybierz opcję **Uruchom wszystko** lub Uruchom ten test indywidualny.

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

Aby uruchomić testy, przejdź do folderu projektu (folder zawierający `Tests.csproj` ) i uruchom polecenie:

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

Testy jednostkowe można filtrować według ich nazwy lub celu przebiegu:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


**_

Wewnętrzna funkcja <xref:Microsoft.Quantum.Intrinsic.Message> ma typ `(String -> Unit)` i umożliwia tworzenie komunikatów diagnostycznych.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Po uruchomieniu testu w Eksploratorze testów i kliknięciu testu zostanie wyświetlony panel z informacjami o przebiegu testu: stan powodzenia/niepowodzenia, czas, który upłynął, oraz link do danych wyjściowych. Kliknij przycisk _ *Output* *, aby otworzyć dane wyjściowe testu w nowym oknie.

![dane wyjściowe testu](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

Stan przekazywania/niepowodzenia dla każdego testu jest drukowany w konsoli przez `dotnet test` .
W przypadku niepowodzeń testów są one również drukowane w konsoli programu w celu ułatwienia zdiagnozowania błędu.

**_

## <a name="facts-and-assertions"></a>Fakty i potwierdzenia

Ze względu na to, że funkcje w programie Q# nie mają _logicznych_ efektów ubocznych, można nie obserwować w Q# programie żadnych innych rodzajów efektów z uruchamiania funkcji, której typ danych wyjściowych jest pustą krotką `()` .
Oznacza to, że komputer docelowy może nie uruchamiać żadnej funkcji, która zwraca `()` z gwarancją, że to pominięcie nie zmodyfikuje zachowania żadnego z następujących Q# kodów.
Takie zachowanie powoduje, że funkcje zwracają `()` (takie jak `Unit` ) użyteczne narzędzie do osadzania i debugowania w Q# programach. 

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

W tym miejscu słowo kluczowe `fail` wskazuje, że obliczenia nie powinny być wykonywane, i zgłasza wyjątek na maszynie docelowej, na której jest uruchomiony Q# program.
Według definicji nie można zaobserwować błędu tego rodzaju z poziomu programu Q# , ponieważ maszyna docelowa nie uruchamia już Q# kodu po osiągnięciu `fail` instrukcji.
W takim przypadku, jeśli będziemy przebiegać przed wywołaniem `PositivityFact` , możemy mieć pewność, że jego dane wejściowe były dodatnie.

Należy pamiętać, że możemy zaimplementować takie samo zachowanie, jak `PositivityFact` Używanie [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) funkcji z <xref:Microsoft.Quantum.Diagnostics> przestrzeni nazw:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

_Assertions *, z drugiej strony, są używane podobnie do faktów, ale mogą być zależne od stanu maszyny docelowej. Są one odpowiednio zdefiniowane jako operacje, natomiast fakty są definiowane jako funkcje (jak w poprzednim przykładzie).
Aby zrozumieć rozróżnienie, należy rozważyć następujące użycie faktu w ramach potwierdzenia:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

W tym miejscu używamy operacji <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> do zwrócenia liczby qubits dostępnych do użycia.
Ponieważ jest to zależne od stanu globalnego programu i jego środowiska uruchomieniowego, definicja `AssertQubitsAreAvailable` musi być operacją.
Można jednak użyć tego stanu globalnego, aby dać prostą `Bool` wartość jako dane wejściowe do `Fact` funkcji.

[Preludium, które](xref:microsoft.quantum.libraries.standard.prelude)tworzą na te pomysły, oferuje dwa szczególnie przydatne potwierdzenia <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> i <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> są modelowane jako operacje na `()` . Każdy z tych zatwierdzeń przyjmuje operatora Pauli opisujące konkretną miarę zainteresowania, rejestr Quantum, na którym wykonywane jest pomiary i hipotetyczny wynik.
Maszyny docelowe, które działają przez symulację, nie są związane [z theoremem bez klonowania](https://en.wikipedia.org/wiki/No-cloning_theorem)i mogą wykonywać takie pomiary bez zakłócania rejestrowania, który przekazuje do takich potwierdzeń.
Symulator może następnie, podobnie jak `PositivityFact` poprzedniej funkcji, zatrzymać obliczenia, jeśli hipotetyczny wynik nie jest zaobserwowany w praktyce:

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

Na fizycznym sprzęcie Quantum, gdzie theorem bez klonowania uniemożliwia badanie stanu Quantum, `AssertMeasurement` `AssertMeasurementProbability` operacje i po prostu zwracają `()` bez żadnego skutku.

<xref:Microsoft.Quantum.Diagnostics>Przestrzeń nazw udostępnia kilka funkcji `Assert` rodziny, za pomocą których można sprawdzić bardziej zaawansowane warunki. 

## <a name="dump-functions"></a>Funkcje zrzutu

Aby ułatwić rozwiązywanie problemów z programami Quantum, <xref:Microsoft.Quantum.Diagnostics> przestrzeń nazw oferuje dwie funkcje, które mogą zrzutować do pliku bieżący stan maszyny docelowej: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> i <xref:Microsoft.Quantum.Diagnostics.DumpRegister> . Wygenerowane dane wyjściowe każdego z nich są zależne od maszyny docelowej.

### <a name="dumpmachine"></a>DumpMachine

Kompleksowy symulator Quantum dystrybuowany w ramach zestawu Quantum Development Kit zapisuje w pliku [funkcję Wave](https://en.wikipedia.org/wiki/Wave_function) całego systemu Quantum jako tablicę jednowymiarową liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru stanu podstawy obliczeniowej $ \ket{n} $, gdzie $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ dla usługi BITS $ \{ b_i \} $. Na przykład na komputerze z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ wywołujący <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generuje te dane wyjściowe:

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
* **`0.707107 +  0.000000 i`** : amplituda prawdopodobieństwa w formacie kartezjańskiego.
* **` == `** : `equal` znak oddziela obie równoważne reprezentacje.
* **`**********  `** : Graficzna reprezentacja rozmiaru, liczba `*` jest proporcjonalna do prawdopodobieństwa mierzenia tego wektora stanu.
* **`[ 0.500000 ]`** : wartość liczbowa wielkości
* **`    ---`** : Graficzna reprezentacja fazy amplitudy (patrz następujące dane wyjściowe).
* **`[ 0.0000 rad ]`** : wartość liczbowa fazy (w radianach).

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
  > Identyfikator qubit można znaleźć w programie Visual Studio, umieszczając punkt przerwania w kodzie i sprawdzając wartość zmiennej qubit, na przykład:
  > 
  > ![Pokaż identyfikator qubit w programie Visual Studio](~/media/qubit_id.png)
  >
  > qubit z indeksem `0` o `register2` identyfikatorze = `3` , qubit z indeksem `1` ma identyfikator = `2` .

#### <a name="command-line--visual-studio-code"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Identyfikator qubit można zlokalizować przy użyciu <xref:Microsoft.Quantum.Intrinsic.Message> funkcji i przekazującej zmienną qubit w komunikacie, na przykład:
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


**_

Ponieważ <xref:Microsoft.Quantum.Diagnostics.DumpMachine> jest częścią  <xref:Microsoft.Quantum.Diagnostics> przestrzeni nazw, należy dodać instrukcję, `open` Aby uzyskać do niej dostęp:

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

<xref:Microsoft.Quantum.Diagnostics.DumpRegister> działa jak <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , z tym wyjątkiem, że pobiera również tablicę qubits w celu ograniczenia ilości informacji tylko do odpowiednich qubits.

Podobnie jak w przypadku <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , informacje generowane przez program <xref:Microsoft.Quantum.Diagnostics.DumpRegister> są zależne od maszyny docelowej. W przypadku kompleksowego symulatora Quantum zapisuje w pliku funkcję Wave do globalnej fazy podsystemu Quantum wygenerowanego przez podaną qubits w tym samym formacie co <xref:Microsoft.Quantum.Diagnostics.DumpMachine> .  Na przykład wykonaj ponownie maszynę z tylko dwoma qubits przydzielonymi i w stanie Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ Pi/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ), \end{align} $ $ wywołujący <xref:Microsoft.Quantum.Diagnostics.DumpRegister> dla `qubit[0]` wygenerowało następujące dane wyjściowe:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

i wywołanie <xref:Microsoft.Quantum.Diagnostics.DumpRegister> metody `qubit[1]` generuje następujące dane wyjściowe:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Ogólnie rzecz biorąc, stan rejestru Entangled z innym rejestrem jest stanem mieszanym, a nie czystym. W takim przypadku <xref:Microsoft.Quantum.Diagnostics.DumpRegister> wyświetla następujący komunikat:

```
Qubits provided (0;) are entangled with some other qubit.
```

Poniższy przykład pokazuje, jak można używać obu <xref:Microsoft.Quantum.Diagnostics.DumpRegister> i <xref:Microsoft.Quantum.Diagnostics.DumpMachine> w Q# kodzie:

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

W oparciu o `Assert` i `Dump` funkcje i operacje Q# obsługują podzbiór standardowych możliwości debugowania programu Visual Studio: [ustawianie punktów przerwania](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [krokowe wykonywanie kodu przy użyciu](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)klawisza F10 i [Sprawdzanie wartości zmiennych klasycznych](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) jest możliwe, gdy uruchamiasz kod w symulatorze.

Debugowanie w Visual Studio Code wykorzystuje funkcje debugowania dostępne w języku C# dla rozszerzenia Visual Studio Code obsługiwanego przez OmniSharp i wymaga zainstalowania [najnowszej wersji](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 

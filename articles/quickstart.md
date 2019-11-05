---
title: Podstawy obliczeń kwantowych w języku Q#
description: Dowiedz się, jak napisać program kwantowy w języku Q#. Opracowywanie aplikacji stanu Bella za pomocą zestawu QDK (Quantum Development Kit)
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 30135fa8a123e52a92b7187218f9980ba3cdbd2d
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442208"
---
# <a name="quantum-basics-with-q"></a>Podstawy obliczeń kwantowych w języku Q#

W tym przewodniku Szybki start pokazano, jak napisać program języka Q#, który manipuluje kubitami, mierzy je oraz przedstawia efekty superpozycji i splątania.  Przewodnik obejmuje instalowanie zestawu QDK, tworzenie programu i uruchamianie go na symulatorze kwantowym.  

Napiszesz aplikację o nazwie Bell, aby zademonstrować splątanie kwantowe.  Nazwisko Bell odnosi się do stanów Bella — specyficznych stanów kwantowych dwóch kubitów, które są używane do reprezentowania najprostszych przykładów superpozycji i splątania kwantowego. 

## <a name="pre-requisites"></a>Wymagania wstępne

Gdy wszystko będzie gotowe do rozpoczęcia kodowania, wykonaj następujące kroki przed kontynuowaniem: 

* [Zainstaluj](xref:microsoft.quantum.install) zestaw Quantum Development Kit przy użyciu preferowanego języka i środowiska programistycznego.
* Jeśli masz już zainstalowany zestaw QDK, upewnij się, że [zaktualizowano](xref:microsoft.quantum.update) go do najnowszej wersji.

Możesz też przeczytać opis, nie instalując zestawu QDK, przeglądając omówienia języka programowania Q# i pierwsze koncepcje obliczeń kwantowych.

## <a name="demonstrating-qubit-behavior-with-q"></a>Demonstrowanie zachowania kubitów przy użyciu języka Q#

Przypomnijmy prostą [definicję kubitu](xref:microsoft.quantum.overview.what#the-qubit).  Bity klasyczne przechowują jedną wartość binarną, taką jak 0 lub 1, natomiast kubit może być w stanie **superpozycji** wartości 0 i 1 równocześnie.  Koncepcyjnie kubit można uważać za kierunek w przestrzeni (nazywany też wektorem).  Kubit może mieć dowolny z możliwych kierunków. Dwa **stany klasyczne** są dwoma określonymi kierunkami — reprezentującymi stuprocentową szansę zmierzenia wartości 0 i stuprocentową szansę zmierzenia wartości 1.  Tę reprezentację można też bardziej formalnie zwizualizować za pomocą [sfery Blocha](/quantum/concepts/the-qubit?view=qsharp-preview#visualizing-qubits-and-transformations-using-the-bloch-sphere).


Pomiar pozwala uzyskać wynik binarny i zmienia stan kubitu. Wynikiem pomiaru jest wartość binarna 0 lub 1.  Kubit przechodzi z superpozycji (dowolny kierunek) do jednego ze stanów klasycznych.  Następne powtórzenia tego samego pomiaru bez wykonywania żadnych pośrednich interwencji dają taki sam wynik binarny.  

Wiele kubitów może być **splątanych**. Gdy mierzymy jeden ze splątanych kubitów, powoduje to również aktualizację naszej wiedzy o stanie pozostałych kubitów.

Teraz wszystko jest gotowe do zademonstrowania, jak wyrazić to zachowanie w języku Q#.  Rozpoczniesz od najprostszego możliwego programu i rozbudujesz go w celu zademonstrowania zjawisk superpozycji kwantowej i splątania kwantowego.

## <a name="setup"></a>Konfigurowanie

Aplikacje opracowane za pomocą zestawu Quantum Development Kit firmy Microsoft składają się z dwóch części:

1. Co najmniej jednego algorytmu kwantowego zaimplementowanego przy użyciu języka programowania kwantowego Q#.
1. Programu hosta zaimplementowanego w języku programowania takim jak Python lub C#, który służy jako główny punkt wejścia i wywołuje operacje języka Q# w celu wykonania algorytmu kwantowego.

#### <a name="pythontabtabid-python"></a>[Python](#tab/tabid-python)

1. Wybieranie lokalizacji dla aplikacji

1. Utwórz plik o nazwie `Bell.qs`. Ten plik będzie zawierać kod Q#.

1. Utwórz plik o nazwie `host.py`. Ten plik będzie zawierać kod hosta w języku Python.

#### <a name="c-command-linetabtabid-csharp"></a>[Wiersz polecenia języka C#](#tab/tabid-csharp).

1. Utwórz nowy projekt języka Q#:

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    Powinien być widoczny plik `.csproj`, plik kodu Q# o nazwie `Operations.qs` i plik programu hosta o nazwie `Driver.cs`

1. Zmiana nazwy pliku kodu Q#

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studiotabtabid-vs2019"></a>[Program Visual Studio](#tab/tabid-vs2019)

1. Tworzenie nowego projektu

   * Otwórz program Visual Studio.
   * Przejdź do menu **Plik**, a następnie wybierz pozycję **Nowy** -> **Projekt...** .
   * W eksploratorze szablonów projektów wpisz `Q#` w polu wyszukiwania i wybierz szablon `Q# Application`
   * Nadaj projektowi nazwę `Bell`.

1. Zmiana nazwy pliku kodu Q#

   * Przejdź do **Eksploratora rozwiązań**.
   * Kliknij prawym przyciskiem myszy plik `Operations.qs`.
   * Zmień jego nazwę na `Bell.qs`.

* * *

## <a name="write-a-q-operation"></a>Tworzenie operacji w języku Q#

Naszym celem jest przygotowanie dwóch kubitów w określonym stanie kwantowym, aby zademonstrować sposób wykonywania operacji na kubitach za pomocą języka Q# w celu zmieniania ich stanu, a także zademonstrować efekty superpozycji i splątania. Zrobimy to krok po kroku, aby przedstawić stany, operacje i pomiary kubitów.

**Omówienie:**  W pierwszym poniższym kodzie pokazujemy, jak pracować z kubitami w języku Q#.  Wprowadzimy dwie operacje (`M` i `X`), które przekształcają stan kubitu. 

W tym fragmencie kodu jest definiowana operacja `Set`, która przyjmuje parametr w postaci kubitu i kolejny parametr `desired`, reprezentujący stan, w który należy wprowadzić kubit.  Operacja `Set` wykonuje pomiar kubitu za pomocą operacji `M`.  W języku Q# pomiar kubitu zawsze zwraca wartość `Zero` lub `One`.  Jeśli pomiar zwróci wartość, która nie jest równa żądanej wartości, operacja Set „przerzuci” kubit, tzn. wykona operację `X`, która zmienia stan kubitu na nowy stan, w którym prawdopodobieństwa zwrócenia wartości `Zero` i `One` są odwrócone.  Aby zademonstrować efekt operacji `Set`, dodawana jest następnie operacja `TestBellState`.  Ta operacja przyjmuje jako dane wejściowe wartość `Zero` lub `One` i wywołuje operację `Set` pewną liczbę razy z tymi danymi wejściowymi, a także oblicza, ile razy została zwrócona wartość `Zero` z pomiaru kubitu i ile razy została zwrócona wartość `One`. Oczywiście w tej pierwszej symulacji operacji `TestBellState` oczekujemy, że dane wyjściowe będą wskazywać, iż wszystkie pomiary kubitu z ustawionym parametrem wejściowym `Zero` będą zwracać wartość `Zero`, a wszystkie pomiary kubitu z ustawionym parametrem wejściowym `One` będą zwracać wartość `One`.  Następnie dodamy kod do elementu `TestBellState` w celu zademonstrowania superpozycji i splątania.


### <a name="q-operation-code"></a>Kod operacji języka Q#

1. Zastąp zawartość pliku Bell.qs następującym kodem:

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    Można teraz wywołać tę operację, aby ustawić dla kubitu stan klasyczny, powodujący zwracanie wartości `Zero` przez 100% czasu lub zwracanie wartości `One` przez 100% czasu.  Wartości `Zero` i `One` są stałymi, które reprezentują dwa możliwe wyniki pomiaru kubitu.

    Operacja `Set` mierzy kubit.
    Jeśli kubit jest w żądanym stanie, operacja `Set` pozostawia go bez zmian; w przeciwnym razie zmieniamy stan kubitu na żądany, wykonując operację `X`.

### <a name="about-q-operations"></a>Informacje o operacjach języka Q#

Operacja języka Q# jest podprocedurą kwantową. Oznacza to, że jest ona procedurą zawierającą operacje kwantowe.

Argumenty operacji są przekazywane za pomocą krotki (w nawiasach).

Zwracany typ operacji jest określony po dwukropku. W tym przypadku operacja `Set` nie zwraca wartości, więc jest oznaczona jako zwracająca wartość `Unit`. W języku Q# jest to odpowiednik wartości `unit` języka F#, która jest w przybliżeniu analogiczna do wartości `void` w języku C# i pustej krotki (`Tuple[()]`) w języku Python.

W pierwszej operacji języka Q# użyto dwóch operacji kwantowych:

* Operacja [M](xref:microsoft.quantum.intrinsic.m), która mierzy stan kubitu
* Operacja [X](xref:microsoft.quantum.intrinsic.x), która przerzuca stan kubitu

Operacja kwantowa przekształca stan kubitu. Czasami mówi się o bramkach kwantowych zamiast operacji, analogicznie do klasycznych bramek logicznych. Bierze się to z wczesnej epoki obliczeń kwantowych, gdy algorytmy stanowiły tylko konstrukcje teoretyczne i były wizualizowane jako diagramy, podobnie do diagramów obwodów w obliczeniach klasycznych.

### <a name="add-q-test-code"></a>Dodawanie kodu testowego Q#

1. Dodaj następującą operację do pliku `Bell.qs` wewnątrz przestrzeni nazw po operacji `Set`:

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    Ta operacja (`TestBellState`) wykona `count` iteracji pętli, ustawi określoną wartość `initial` dla kubitu, a następnie zmierzy (`M`) wynik. Zbierze ona dane statystyczne dotyczące zmierzonej liczby zer i jedynek oraz zwróci je do obiektu wywołującego. Wykona także jedną inną wymaganą operację. Zresetuje kubit do znanego stanu (`Zero`) przed jego zwróceniem, co umożliwi innym przydzielenie tego kubitu w znanym stanie. Jest to wymagane przez instrukcję `using`.

### <a name="about-variables-in-q"></a>Informacje o zmiennych w języku Q#

Domyślnie zmienne w języku Q# są niezmienialne — ich wartości nie można zmienić po powiązaniu. Słowo kluczowe `let` jest używane do wskazania powiązania zmiennej niezmienialnej. Argumenty operacji są zawsze niezmienialne.

Jeśli potrzebujesz zmiennej, której wartość można zmienić, takiej jak `numOnes` w przykładzie, możesz zadeklarować zmienną za pomocą słowa kluczowego `mutable`. Wartość zmiennej modyfikowalnej zmienia się przy użyciu instrukcji `set`.

W obu przypadkach typ zmiennej jest wnioskowany przez kompilator. Język Q# nie wymaga żadnych adnotacji typu dla zmiennych.

### <a name="about-using-statements-in-q"></a>Informacje o instrukcjach `using` w języku Q#

Instrukcja `using` jest również szczególna dla języka Q#. Służy do przydzielania kubitów do użycia w bloku kodu. W języku Q# wszystkie kubity są dynamicznie przydzielane i zwalniane — nie są stałymi zasobami w całym okresie istnienia złożonego algorytmu. Instrukcja `using` przydziela zestaw kubitów na początku bloku i zwalnia te kubity na jego końcu.

## <a name="create-the-host-application-code"></a>Tworzenie kodu aplikacji hosta

#### <a name="pythontabtabid-python"></a>[Python](#tab/tabid-python)

1. Otwórz plik `host.py` i dodaj następujący kod:

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="ctabtabid-csharp"></a>[C#](#tab/tabid-csharp)

1. Zastąp zawartość pliku `Driver.cs` następującym kodem:

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>Informacje o kodzie aplikacji hosta

#### <a name="pythontabtabid-python"></a>[Python](#tab/tabid-python)

Aplikacja hosta w języka Python ma trzy części:

* Oblicza wszystkie argumenty wymagane dla algorytmu kwantowego. W przykładzie zmienna `count` ma stałą wartość 1000, a zmienna `initial` to wartość początkowa kubitu.
* Uruchamia algorytm kwantowy, wywołując metodę `simulate()` zaimportowanej operacji języka Q#.
* Przetwarza wynik operacji. W przykładzie zmienna `res` otrzymuje wynik operacji. Tutaj wynik jest krotką liczby zer (`num_zeros`) i liczby jedynek (`num_ones`) zmierzonych przez symulator. Rozdzielamy krotkę, aby uzyskać dwa pola, i drukujemy wyniki.

#### <a name="ctabtabid-csharp"></a>[C#](#tab/tabid-csharp)

Aplikacja hosta w języku C# ma cztery części:

* Konstruuje symulator kwantowy. W przykładzie element `qsim` jest symulatorem.
* Oblicza wszystkie argumenty wymagane dla algorytmu kwantowego. W przykładzie zmienna `count` ma stałą wartość 1000, a zmienna `initial` to wartość początkowa kubitu.
* Uruchamia algorytm kwantowy. Każda operacja języka Q# generuje klasę języka C# o tej samej nazwie. Ta klasa ma metodę `Run`, która **asynchronicznie** wykonuje operację. Wykonanie jest asynchroniczne, ponieważ wykonanie na rzeczywistym sprzęcie będzie asynchroniczne. Ponieważ metoda `Run` jest asynchroniczna, pobieramy właściwość `Result`. To blokuje wykonywanie do momentu zakończenia zadania i powoduje synchronicznie zwrócenie wyniku.
* Przetwarza wynik operacji. W przykładzie zmienna `res` otrzymuje wynik operacji. Tutaj wynik jest krotką liczby zer (`numZeros`) i liczby jedynek (`numOnes`) zmierzonych przez symulator. Jest on zwracany jako element ValueTuple w języku C#. Rozdzielamy krotkę, aby uzyskać dwa pola, drukujemy wyniki i czekamy na naciśnięcie klawisza.

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>Kompilowanie i uruchamianie

#### <a name="pythontabtabid-python"></a>[Python](#tab/tabid-python)

1. Uruchom następujące polecenie w terminalu:

    ```
    python host.py
    ```

    To polecenie uruchamia aplikację hosta, która symuluje operację języka Q#.

Wyniki powinny być następujące:

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-codetabtabid-csharp"></a>[Wiersz polecenia/program Visual Studio Code](#tab/tabid-csharp)

1. Uruchom następujące polecenie w terminalu:

    ```bash
    dotnet run
    ```

    To polecenie spowoduje automatyczne pobranie wszystkich wymaganych pakietów, skompilowanie aplikacji, a następnie uruchomienie jej w wierszu polecenia.

1. Alternatywnie naciśnij klawisz **F1**, aby otworzyć paletę poleceń, i wybierz polecenie **Debuguj: Uruchom bez debugowania**.
Może zostać wyświetlony monit o utworzenie nowego pliku ``launch.json`` opisującego sposób uruchamiania programu.
Domyślny plik ``launch.json`` powinien wystarczyć dla większości aplikacji.

Wyniki powinny być następujące:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studiotabtabid-vs2019"></a>[Program Visual Studio](#tab/tabid-vs2019)

1. Po prostu naciśnij klawisz `F5`, a program powinien zostać skompilowany i uruchomiony.

Wyniki powinny być następujące:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

Program zostanie zakończony po naciśnięciu klawisza.

* * *

## <a name="prepare-superposition"></a>Przygotowanie superpozycji

**Przegląd** Teraz przyjrzyjmy się, jak w języku Q# można wyrazić wprowadzanie kubitów w stan superpozycji.  Przypomnijmy, że kubit może być w stanie superpozycji wartości 0 i 1.  Użyjemy operacji `Hadamard`, aby go uzyskać. Jeśli kubit znajduje się w dowolnym ze stanów klasycznych (gdy pomiar zwraca zawsze wartość `Zero` lub zawsze wartość `One`), operacja `Hadamard` lub `H` wprowadzi kubit w stan, w którym pomiar kubitu będzie zwracać wartość `Zero` przez 50% czasu i zwracać wartość `One` przez 50% czasu.  Koncepcyjnie kubit można uważać za będący w połowie między wartościami `Zero` i `One`.  Gdy teraz zasymulujemy operację `TestBellState`, zwracane wyniki będą zawierać w przybliżeniu równą liczbę wartości `Zero` i `One` po pomiarze.  

Najpierw spróbujemy przerzucić kubit (jeśli kubit jest w stanie `Zero`, przerzucimy go do stanu `One` i na odwrót). Wykonuje się to za pomocą operacji `X` przed wykonaniem pomiaru w operacji `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

Teraz wyniki (po naciśnięciu klawisza `F5`) są odwrócone:

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

Jednak wszystko, co zobaczyliśmy dotychczas, jest „klasyczne”. Uzyskajmy wynik kwantowy. Wszystko, co należy zrobić, to zastąpić operację `X` w poprzednim uruchomieniu operacją Hadamarda `H`. Zamiast przerzucać kubit całkowicie z wartości 0 do wartości 1, przerzucimy go tylko w połowie. Zastąpione wiersze w operacji `TestBellState` teraz wyglądają następująco:

```qsharp
H(qubit);
let res = M(qubit);
```

Nowe wyniki są bardziej interesujące:

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

Przy każdym wykonaniu pomiaru żądamy wartości klasycznej, lecz kubit jest w stanie przejściowym między wartościami 0 i 1, więc otrzymamy (statystycznie) wartość 0 w połowie przypadków i wartość 1 w pozostałych przypadkach. Jest to zjawisko __superpozycji__, które daje nam po raz pierwszy wgląd w rzeczywisty stan kwantowy.

## <a name="prepare-entanglement"></a>Przygotowanie splątania

**Omówienie:**  Teraz zobaczmy, jak można wyrażać splątanie w języku Q#.  Najpierw ustawiamy pierwszy kubit w stanie początkowym, a następnie wprowadzamy go w stan superpozycji za pomocą operacji `H`.  Następnie, przed pomiarem pierwszego kubitu, używamy nowej operacji (`CNOT`), czyli Controlled-Not.  Wynikiem wykonania tej operacji na dwóch kubitach jest przerzucenie drugiego kubitu, jeśli pierwszy kubit ma wartość `One`.  Teraz oba kubity są splątane.  Nasze dane statystyczne dotyczące pierwszego kubitu nie uległy zmianie (szansa 50%-50% dla wartości `Zero` i `One` po pomiarze), ale teraz pomiar drugiego kubitu jest __zawsze__ taki sam jak pierwszego kubitu. Bramka `CNOT` splątała dwa kubity — cokolwiek dzieje się z jednym z nich, to samo dzieje się z drugim. W przypadku odwrócenia pomiarów (drugi kubit przed pierwszym) będzie dziać się to samo. Pierwsza miara będzie losowa, a druga zablokowana na wartości pierwszej.

Pierwsza rzecz do zrobienia to przydzielenie 2 kubitów zamiast jednego w operacji `TestBellState`:

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Pozwoli to dodać nową operację (`CNOT`) przed wykonaniem pomiaru (`M`) w operacji `TestBellState`:

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Dodaliśmy kolejną operację `Set`, aby zainicjować pierwszy kubit w celu zapewnienia, że jest zawsze w stanie `Zero` podczas uruchamiania.

Musimy też zresetować drugi kubit przed jego zwolnieniem.

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

Pełna procedura wygląda teraz następująco:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

Jeśli ją uruchomimy, uzyskamy dokładnie taki sam wynik 50%-50% jak poprzednio. Jednak teraz interesuje nas, jak drugi kubit reaguje na pomiar pierwszego. Dodamy tę statystykę do nowej wersji operacji `TestBellState`:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

Nowa wartość zwracana (`agree`) śledzi przypadki, gdy pomiar pierwszego kubitu jest zgodny z pomiarem drugiego kubitu. Należy także odpowiednio zaktualizować aplikację hosta:

#### <a name="pythontabtabid-python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="ctabtabid-csharp"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

Teraz po uruchomieniu otrzymujemy coś zdumiewającego:

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

Jak podano w omówieniu, nasze dane statystyczne dotyczące pierwszego kubitu nie uległy zmianie (szansa 50%-50% dla wartości 0 i 1), ale teraz pomiar drugiego kubitu jest __zawsze__ taki sam jak pierwszego kubitu, ponieważ są one splątane!

Gratulacje, udało Ci się napisać swój pierwszy program kwantowy!

## <a name="whats-next"></a>Co dalej?

W przewodniku Szybki start [Wyszukiwanie Grovera](xref:microsoft.quantum.quickstarts.search) przedstawiono tworzenie i uruchamianie wyszukiwania Grovera — jednego z najpopularniejszych algorytmów obliczeń kwantowych — oraz podano ciekawy przykład programu języka Q#, którego można użyć do rozwiązywania rzeczywistych problemów obliczeń kwantowych.  

Artykuł [Wprowadzenie do zestawu Quantum Development Kit](xref:microsoft.quantum.welcome) zawiera więcej zalecanych sposobów uczenia się języka Q# i programowania kwantowego.


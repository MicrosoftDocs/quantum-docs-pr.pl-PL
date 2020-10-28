---
title: Eksploruj Entanglement z Q#
description: Dowiedz się, jak napisać program Quantum w Q# . Opracowywanie aplikacji stanu Bella za pomocą zestawu QDK (Quantum Development Kit)
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7a1a49e18ac9330ca6e3cc89b3e58c96eccb91db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691675"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Samouczek: Eksplorowanie splątania przy użyciu języka Q\#

W tym samouczku pokazano, jak napisać Q# program, który manipuluje i mierzy qubits i pokazuje efekty nakładania się i Entanglement.

Napiszesz aplikację o nazwie Bell, aby zademonstrować splątanie kwantowe.
Nazwisko Bell odnosi się do stanów Bella — specyficznych stanów kwantowych dwóch kubitów, które są używane do reprezentowania najprostszych przykładów superpozycji i splątania kwantowego.

## <a name="pre-requisites"></a>Wymagania wstępne

Gdy wszystko będzie gotowe do rozpoczęcia kodowania, wykonaj następujące kroki przed kontynuowaniem: 

* [Zainstaluj](xref:microsoft.quantum.install) zestaw Quantum Development Kit przy użyciu preferowanego języka i środowiska programistycznego.
* Jeśli masz już zainstalowany zestaw QDK, upewnij się, że [zaktualizowano](xref:microsoft.quantum.update) go do najnowszej wersji.

Możesz również wykonać czynności opisane w opisie, nie instalując QDK, przeglądając omówienia Q# języka programowania i pierwsze koncepcje przetwarzania Quantum.

## <a name="in-this-tutorial-youll-learn-how-to"></a>Z tego samouczka dowiesz się, jak wykonywać następujące czynności:

> [!div class="checklist"]
> * Tworzenie i łączenie operacji w p\#
> * Twórz operacje w celu umieszczenia qubits w położeniu, entangle i mierzenia ich.
> * Zademonstrowanie Entanglement Quantum przy użyciu Q# programu uruchamianego w symulatorze. 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>Prezentowanie zachowania qubit z QDK

Bity klasyczne przechowują jedną wartość binarną, taką jak 0 lub 1, natomiast [kubit](xref:microsoft.quantum.glossary#qubit) może być w stanie **superpozycji** wartości 0 i 1.  Koncepcyjnie, stan qubit można traktować jako kierunek w przestrzeni abstrakcyjnej (znanej również jako wektor).  Stan qubit może być w dowolnym z możliwych instrukcji. Dwa **stany klasyczne** są dwoma określonymi kierunkami — reprezentującymi stuprocentową szansę zmierzenia wartości 0 i stuprocentową szansę zmierzenia wartości 1.

Pomiar pozwala uzyskać wynik binarny i zmienia stan kubitu.
Pomiar tworzy wartość binarną, 0 lub 1.  Kubit przechodzi z superpozycji (dowolny kierunek) do jednego ze stanów klasycznych.  Następne powtórzenia tego samego pomiaru bez wykonywania żadnych pośrednich interwencji dają taki sam wynik binarny.  

Wiele kubitów może być [**splątanych**](xref:microsoft.quantum.glossary#entanglement).  Gdy mierzymy jeden ze splątanych kubitów, powoduje to również aktualizację naszej wiedzy o stanie pozostałych kubitów.

Teraz jesteśmy gotowi do zademonstrowania Q# tego zachowania.  Rozpoczniesz od najprostszego możliwego programu i rozbudujesz go w celu zademonstrowania zjawisk superpozycji kwantowej i splątania kwantowego.

## <a name="creating-a-no-locq-project"></a>Tworzenie Q# projektu

Pierwszą czynnością, którą należy wykonać, jest utworzenie nowego Q# projektu. W tym samouczku zamierzamy używać środowiska na podstawie [ Q# aplikacji z vs Code](xref:microsoft.quantum.install.standalone).

Aby utworzyć nowy projekt, w VS Code: 

1. Kliknij pozycję **View** -> **Command Palette** (Widok -> Paleta poleceń), a następnie wybierz polecenie **Q#: Create New Project** (Q#: utwórz nowy projekt).
2. Kliknij pozycję **Standalone console application** (Autonomiczna aplikacja konsolowa).
3. Przejdź do lokalizacji, w której chcesz zapisać projekt, a następnie kliknij pozycję **Create project** (Utwórz projekt).
4. Po pomyślnym utworzeniu projektu kliknij pozycję **Open new project...** (Otwórz nowy projekt) w prawym dolnym rogu.

W takim przypadku nazywamy projektem `Bell` . Spowoduje to wygenerowanie dwóch plików: `Bell.csproj` , pliku projektu i `Program.qs` szablonu Q# aplikacji, która zostanie użyta do zapisania naszej aplikacji. Zawartość `Program.qs` powinna być:

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a>Napisz aplikację Q \#
 
Naszym celem jest przygotowanie dwóch qubits w konkretnym stanie Quantum, pokazując, jak pracować na qubits z programem w Q# celu zmiany ich stanu i zademonstrować efekty nakładania się i Entanglement. Utworzymy ten element, aby wprowadzić qubit Stany, operacje i pomiary.

### <a name="initialize-qubit-using-measurement"></a>Inicjowanie qubit przy użyciu miary

W pierwszym fragmencie kodu poniżej pokazano, jak korzystać z qubits w programie Q# .  Wprowadzimy dwie operacje [`M`](xref:Microsoft.Quantum.Intrinsic.m) i [`X`](xref:Microsoft.Quantum.Intrinsic.X) przekształciją stan qubit. W tym fragmencie kodu jest definiowana operacja `SetQubitState`, która przyjmuje parametr w postaci kubitu i kolejny parametr `desired`, reprezentujący stan, w który należy wprowadzić kubit.  Operacja `SetQubitState` wykonuje pomiar kubitu za pomocą operacji `M`.  W programie Q# pomiar qubit zawsze zwraca albo `Zero` `One` .  Jeśli pomiar zwraca wartość, która nie jest równa żądanej wartości, `SetQubitState` "przerzuca" qubit; oznacza to, że wykonuje `X` operację, która zmienia stan qubit na nowy stan, w którym prawdopodobieństwa zwrócenia pomiaru `Zero` i `One` jest odwrócona. W ten sposób `SetQubitState` zawsze umieszcza docelowy qubit w żądanym stanie.

Zastąp zawartość `Program.qs` następującym kodem:


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

Można teraz wywołać tę operację, aby ustawić dla kubitu stan klasyczny, powodujący zwracanie wartości `Zero` przez 100% czasu lub zwracanie wartości `One` przez 100% czasu.
Wartości `Zero` i `One` są stałymi, które reprezentują dwa możliwe wyniki pomiaru kubitu.

Operacja `SetQubitState` mierzy kubit. Jeśli qubit jest w stanie, który chcemy, `SetQubitState` pozostawi to samo. w przeciwnym razie, uruchamiając `X` operację, zmienimy stan qubit na żądany stan.

#### <a name="about-no-locq-operations"></a>Informacje o Q# operacjach

Q#Operacja jest podprocedurą Quantum. Oznacza to, że jest to wywoływana procedura, która zawiera wywołania innych operacji Quantum.

Argumenty operacji są przekazywane za pomocą krotki (w nawiasach).

Zwracany typ operacji jest określony po dwukropku. W tym przypadku operacja nie `SetQubitState` ma zwracanego typu, więc jest oznaczona jako zwracana `Unit` . Jest to Q# odpowiednik w języku `unit` F #, który jest w przybliżeniu analogiczny do `void` języka C#, i pustą krotką w języku Python ( `()` , reprezentowane przez wskazówkę typu `Tuple[()]` ).

W pierwszej operacji użyto dwóch operacji Quantum Q# :

* [`M`](xref:Microsoft.Quantum.Intrinsic.m)Operacja, która mierzy stan qubit
* [`X`](xref:Microsoft.Quantum.Intrinsic.X)Operacja, która przerzuca stan qubit

Operacja kwantowa przekształca stan kubitu. Czasami mówi się o bramkach kwantowych zamiast operacji, analogicznie do klasycznych bramek logicznych. Bierze się to z wczesnej epoki obliczeń kwantowych, gdy algorytmy stanowiły tylko konstrukcje teoretyczne i były wizualizowane jako diagramy, podobnie do diagramów obwodów w obliczeniach klasycznych.

### <a name="counting-measurement-outcomes"></a>Obliczanie wyników pomiaru

Aby zademonstrować efekt operacji `SetQubitState`, dodawana jest następnie operacja `TestBellState`. Ta operacja przyjmuje jako dane wejściowe wartość `Zero` lub `One` i wywołuje operację `SetQubitState` pewną liczbę razy z tymi danymi wejściowymi, a także oblicza, ile razy została zwrócona wartość `Zero` z pomiaru kubitu i ile razy została zwrócona wartość `One`. Oczywiście w tej pierwszej symulacji operacji `TestBellState` oczekujemy, że dane wyjściowe będą wskazywać, iż wszystkie pomiary kubitu z ustawionym parametrem wejściowym `Zero` będą zwracać wartość `Zero`, a wszystkie pomiary kubitu z ustawionym parametrem wejściowym `One` będą zwracać wartość `One`. Dodatkowo dodamy kod do `TestBellState` przedstawienia do przedłożenia i Entanglement.

Dodaj następującą operację do pliku `Program.qs` wewnątrz przestrzeni nazw po operacji `SetQubitState`:

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
Należy pamiętać, że dodaliśmy wiersz przed przystąpieniem `return` do drukowania komunikatu wyjaśniającego w konsoli programu za pomocą funkcji ( `Message` ) [Microsoft. Quantum. wewnętrzna. Message]

Ta operacja (`TestBellState`) wykona `count` iteracji pętli, ustawi określoną wartość `initial` dla kubitu, a następnie zmierzy (`M`) wynik. Zbierze ona dane statystyczne dotyczące zmierzonej liczby zer i jedynek oraz zwróci je do obiektu wywołującego. Wykona także jedną inną wymaganą operację. Zresetuje kubit do znanego stanu (`Zero`) przed jego zwróceniem, co umożliwi innym przydzielenie tego kubitu w znanym stanie. Jest to wymagane przez instrukcję `using`.

#### <a name="about-variables-in-q"></a>Informacje o zmiennych w Q\#

Domyślnie zmienne w Q# są niezmienne; ich wartości nie można zmienić po ich powiązaniu. Słowo kluczowe `let` jest używane do wskazania powiązania zmiennej niezmienialnej. Argumenty operacji są zawsze niezmienialne.

Jeśli potrzebujesz zmiennej, której wartość można zmienić, takiej jak `numOnes` w przykładzie, możesz zadeklarować zmienną za pomocą słowa kluczowego `mutable`. Wartość zmiennej modyfikowalnej zmienia się przy użyciu instrukcji `set`.

W obu przypadkach typ zmiennej jest wnioskowany przez kompilator. Q# nie wymaga żadnych adnotacji typu dla zmiennych.

#### <a name="about-using-statements-in-q"></a>`using`Instrukcje w temacie Q\#

`using`Instrukcja jest również specjalna dla Q# . Służy do przydzielania kubitów do użycia w bloku kodu. W programie Q# wszystkie qubits są przydzielane i wydawane, a nie stałymi zasobami w całym okresie istnienia złożonego algorytmu. Instrukcja `using` przydziela zestaw kubitów na początku bloku i zwalnia te kubity na jego końcu.

## <a name="run-the-code-from-the-command-prompt"></a>Uruchamianie kodu z wiersza polecenia

Aby uruchomić kod, musimy poinformować kompilator, *który* jest możliwy do uruchomienia, gdy podamy `dotnet run` polecenie. Jest to wykonywane z prostą zmianą w Q# pliku, dodając wiersz `@EntryPoint()` bezpośrednio poprzedzający możliwy do `TestBellState` przeprowadzenia: operację w tym przypadku. Pełny kod powinien:

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

Aby uruchomić program, musimy określić `count` argumenty i `initial` z wiersza polecenia. Wybierzmy na przykład `count = 1000` i `initial = One` . Wprowadź następujące polecenie:

```dotnetcli
dotnet run --count 1000 --initial One
```

I należy obserwować następujące dane wyjściowe:

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Jeśli spróbujesz `initial = Zero` :

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>Przygotowanie superpozycji

Teraz przyjrzyjmy się sposobom, w jaki Q# wyrażamy, jak można dołączać qubits.  Przypomnijmy, że kubit może być w stanie superpozycji wartości 0 i 1.  Użyjemy operacji `Hadamard`, aby go uzyskać. Jeśli kubit znajduje się w dowolnym ze stanów klasycznych (gdy pomiar zwraca zawsze wartość `Zero` lub zawsze wartość `One`), operacja `Hadamard` lub `H` wprowadzi kubit w stan, w którym pomiar kubitu będzie zwracać wartość `Zero` przez 50% czasu i zwracać wartość `One` przez 50% czasu.  Koncepcyjnie kubit można uważać za będący w połowie między wartościami `Zero` i `One`.  Gdy teraz zasymulujemy operację `TestBellState`, zwracane wyniki będą zawierać w przybliżeniu równą liczbę wartości `Zero` i `One` po pomiarze.  

### <a name="x-flips-qubit-state"></a>`X` Przerzucanie stanu qubit

Najpierw spróbujemy przerzucić qubit (jeśli qubit jest w `Zero` stanie, zostanie on przerzucony do i na `One` odwrót). Wykonuje się to za pomocą operacji `X` przed wykonaniem pomiaru w operacji `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

Teraz wyniki są wycofane:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Teraz przyjrzyjmy się właściwościom Quantum klasy qubits.

### <a name="h-prepares-superposition"></a>`H` przygotowuje nałożenie

Wszystko, co należy zrobić, to zastąpić operację `X` w poprzednim uruchomieniu operacją Hadamarda `H`. Zamiast przerzucać kubit całkowicie z wartości 0 do wartości 1, przerzucimy go tylko w połowie. Zastąpione wiersze w operacji `TestBellState` teraz wyglądają następująco:

```qsharp
H(qubit);
let res = M(qubit);
```

Nowe wyniki są bardziej interesujące:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

Przy każdym wykonaniu pomiaru żądamy wartości klasycznej, lecz kubit jest w stanie przejściowym między wartościami 0 i 1, więc otrzymamy (statystycznie) wartość 0 w połowie przypadków i wartość 1 w pozostałych przypadkach.
Jest to zjawisko **superpozycji** , które daje nam po raz pierwszy wgląd w rzeczywisty stan kwantowy.

## <a name="prepare-entanglement"></a>Przygotowanie splątania

Teraz przyjrzyjmy się sposobom, w jaki Q# wyrażamy możliwości entangle qubits.
Najpierw ustawiamy pierwszy kubit w stanie początkowym, a następnie wprowadzamy go w stan superpozycji za pomocą operacji `H`.  Następnie przed pomiarem pierwszego qubit używamy nowej operacji ( `CNOT` ), która oznacza, że nie jest to *kontrolowane* .  Wynikiem uruchomienia tej operacji na dwóch qubits jest przerzucenie drugiej qubit, jeśli pierwszy qubit jest `One` .  Teraz oba kubity są splątane.  Nasze dane statystyczne dotyczące pierwszego kubitu nie uległy zmianie (szansa 50%-50% dla wartości `Zero` i `One` po pomiarze), ale teraz pomiar drugiego kubitu jest __zawsze__ taki sam jak pierwszego kubitu. Bramka `CNOT` splątała dwa kubity — cokolwiek dzieje się z jednym z nich, to samo dzieje się z drugim. W przypadku odwrócenia pomiarów (drugi kubit przed pierwszym) będzie dziać się to samo. Pierwsza miara będzie losowa, a druga zablokowana na wartości pierwszej.

Najpierw należy przydzielić dwie qubits zamiast jednego w `TestBellState` :

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Pozwoli to dodać nową operację (`CNOT`) przed wykonaniem pomiaru (`M`) w operacji `TestBellState`:

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Dodaliśmy kolejną operację `SetQubitState`, aby zainicjować pierwszy kubit w celu zapewnienia, że jest zawsze w stanie `Zero` podczas uruchamiania.

Musimy też zresetować drugi kubit przed jego zwolnieniem.

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

Pełna procedura wygląda teraz następująco:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
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
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

Nowa wartość zwracana (`agree`) śledzi przypadki, gdy pomiar pierwszego kubitu jest zgodny z pomiarem drugiego kubitu.

Uruchamianie kodu, który uzyskamy:

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

Jak podano w omówieniu, nasze dane statystyczne dotyczące pierwszego kubitu nie uległy zmianie (szansa 50%-50% dla wartości 0 i 1), ale teraz pomiar drugiego kubitu jest __zawsze__ taki sam jak pierwszego kubitu, ponieważ są one splątane!

## <a name="next-steps"></a>Następne kroki

W [poszukiwanym](xref:microsoft.quantum.quickstarts.search) samouczku Grover przedstawiono sposób kompilowania i uruchamiania wyszukiwania Grover, jednego z najpopularniejszych algorytmów przetwarzania Quantum i oferowania przykładowego Q# programu, który może służyć do rozwiązywania rzeczywistych problemów z przetwarzaniem Quantum.  

[Wprowadzenie do zestawu Quantum Development Kit](xref:microsoft.quantum.welcome) zaleca więcej sposobów uczenia się Q# i programowania Quantum.

---
title: 'Zapisuj i Symuluj programy qubit na poziomie na platformie Q #'
description: Samouczek krok po kroku dotyczący pisania i symulowania programu Quantum, który działa na indywidualnym poziomie qubit
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: e7ebdec4cd1aa201030d82759a3aa56473b26417
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275349"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>Samouczek: pisanie i symulowanie programów qubit na poziomie w funkcji Q\#

Witamy w samouczku zestawu Quantum Development Kit na temat pisania i symulowania podstawowego programu Quantum, który działa na poszczególnych qubitsach. 

Mimo że funkcja Q # została przed chwilą utworzona jako język programowania wysokiego poziomu dla programów Quantum w dużej skali, można ją łatwo wykorzystać do eksplorowania niższych poziomów programów Quantum: bezpośrednio adresowanie konkretnych qubits.
Elastyczność Q # umożliwia użytkownikom podejście do systemów Quantum z dowolnego takiego poziomu abstrakcji, a w tym samouczku szczegółowe się w qubits.
W odróżnieniu od wyciągu [transformacji Fouriera Quantum](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), podprocedury, która jest całką dla wielu większych algorytmów Quantum.

Należy zauważyć, że ten widok niskiego poziomu przetwarzania informacji Quantum jest często opisany w temacie "[obwody Quantum](xref:microsoft.quantum.concepts.circuits)", które reprezentują sekwencyjne stosowanie bram do określonych qubits systemu.

W ten sposób sekwencyjne i wieloqubite operacje, które z kolei stosują się, można łatwo przedstawić na "diagramie obwodu".
W naszym przypadku zdefiniujemy operację Q #, aby wykonać pełną qubitą transformację Quantum Fouriera, która ma następującą reprezentację jako obwód:

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Wymagania wstępne

* [Zainstaluj](xref:microsoft.quantum.install) zestaw Quantum Development Kit przy użyciu preferowanego języka i środowiska programistycznego.
* Jeśli masz już zainstalowany zestaw QDK, upewnij się, że [zaktualizowano](xref:microsoft.quantum.update) go do najnowszej wersji.


## <a name="in-this-tutorial-youll-learn-how-to"></a>Z tego samouczka dowiesz się, jak wykonywać następujące czynności:

> [!div class="checklist"]
> * Definiowanie operacji Quantum w Q #
> * Wywoływanie operacji Q # bezpośrednio z wiersza polecenia lub przy użyciu klasycznego programu hosta
> * Symuluj operację Quantum z alokacji qubit do danych wyjściowych pomiaru
> * Obserwuj symulowane wavefunction systemu Quantum w całej operacji

Uruchamianie programu Quantum z zestawem Quantum Development Kit firmy Microsoft zwykle składa się z dwóch części:
1. Sam program, który jest implementowany przy użyciu języka programowania Q # Quantum, a następnie wywoływany do uruchamiania na komputerze Quantum lub symulatorze Quantum. Składają się one z 
    - Operacje Q #: procedury podrzędne działające w rejestrach Quantum i 
    - Funkcje Q #: klasyczne procedury podrzędne używane w algorytmie Quantum.
2. Punkt wejścia służący do wywoływania programu Quantum i określania komputera docelowego, na którym ma być uruchamiany.
    Można to zrobić bezpośrednio z wiersza polecenia lub za pośrednictwem programu hosta zapisaną w klasycznym języku programowania, takim jak Python lub C#.
    Ten samouczek zawiera instrukcje dla dowolnej metody, której wolisz.

## <a name="allocate-qubits-and-define-quantum-operations"></a>Alokuj qubits i Definiuj operacje Quantum

Pierwsza część tego samouczka składa się z definiowania operacji Q # `Perform3qubitQFT` , która wykonuje transformację Quantum Fouriera na trzech qubits. 

Dodatkowo będziemy używać [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) funkcji, aby obserwować symulowane wavefunction naszych trzech systemów qubit w całej operacji.

Pierwszym krokiem jest utworzenie projektu i pliku Q #.
Te kroki zależą od środowiska, którego będziesz używać do wywoływania programu, i można znaleźć szczegółowe informacje w odpowiednich [przewodnikach instalacji](xref:microsoft.quantum.install).

Przeprowadzimy Cię przez składniki tego pliku krok po kroku, ale kod jest również dostępny jako pełny blok poniżej.

### <a name="namespaces-to-access-other-q-operations"></a>Przestrzenie nazw umożliwiające dostęp do innych operacji Q #
Wewnątrz pliku najpierw definiujemy przestrzeń nazw, do `NamespaceQFT` której będą uzyskiwać dostęp kompilator.
W przypadku naszej operacji, aby korzystać z istniejących operacji Q #, otwieramy odpowiednie `Microsoft.Quantum.<>` przestrzenie nazw.

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>Zdefiniuj operacje z argumentami i zwraca
Następnie zdefiniujemy `Perform3qubitQFT` operację:

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

Na razie operacja nie przyjmuje żadnych argumentów i nie zwraca żadnych---w tym przypadku napisze, że zwraca `Unit` obiekt, który jest zbliżone `void` w języku C# lub w pustej kolekcji, `Tuple[()]` w Python.
Później zmodyfikujemy ją, aby zwracała tablicę wyników pomiarów, w której punkt `Unit` zostanie zastąpiony przez `Result[]` . 

### <a name="allocate-qubits-with-using"></a>Alokuj qubits z`using`
W ramach naszej operacji Q # najpierw przydzielmy rejestr trzech qubits z `using` instrukcją:

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

W programie `using` qubits są automatycznie przypisywane w stanie $ \ket {0} $. Można to sprawdzić za pomocą [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) i [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , co spowoduje wydrukowanie ciągu i bieżącego stanu systemu w konsoli programu.

> [!NOTE]
> `Message(<string>)`Funkcje i `DumpMachine()` ( [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) odpowiednio) są drukowane bezpośrednio w konsoli programu. Podobnie jak w przypadku rzeczywistego obliczenia Quantum, polecenie Q # nie zezwala nam na bezpośredni dostęp do Stanów qubit.
> Jednak jako `DumpMachine` że program Drukuje bieżący stan maszyny docelowej, może zapewnić cenne informacje dotyczące debugowania i uczenia się, gdy jest używany w połączeniu z symulatorem pełnego stanu.


### <a name="applying-single-qubit-and-controlled-gates"></a>Stosowanie bram o pojedynczej qubit i kontrolowanej

Następnie stosujemy bramy, które składają się na samą operację.
Polecenie Q # zawiera już wiele podstawowych bram Quantum jako operacje w [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) przestrzeni nazw i nie są one wyjątkiem. 

W ramach operacji Q # instrukcje wywoływania wywołania będą wykonywane w kolejności sekwencyjnej.
W związku z tym pierwsza brama do zastosowania to [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) do pierwszej qubit:

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

Aby zastosować operację do określonego qubit z rejestru (tj. pojedynczej `Qubit` z tablicy `Qubit[]` ), używamy standardowego zapisu indeksu.
Dlatego zastosowanie [`H`](xref:microsoft.quantum.intrinsic.h) do pierwszej qubit naszego rejestru `qs` przyjmuje formę:

```qsharp
            H(qs[0]);
```

Oprócz zastosowania `H` bramy (Hadamard) do poszczególnych qubits obwód QFT składa się głównie z kontrolowanych [`R1`](xref:microsoft.quantum.intrinsic.r1) rotacji.
`R1(θ, <qubit>)`Operacja ogólnie pozostawia składnik $ \ket {0} $ niezmienionej qubit, podczas gdy stosowana jest rotacja $e ^ {i\theta} $ do składnika $ \ket {1} $.

#### <a name="controlled-operations"></a>Kontrolowane operacje

Q # upraszcza wykonywanie operacji na jednym lub wielu qubits kontroli.
Ogólnie rzecz biorąc, należy jedynie przeddzwonić wywołanie z `Controlled` , a argumenty operacji zmieniają się w taki sposób:

 `Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` .

Należy zauważyć, że kontrolka qubits musi być określona jako tablica, nawet jeśli jest to pojedynczy qubit.

Po dojściu do programu `H` zobaczymy, że następną bramą są `R1` bramy działające na pierwszej qubit (i kontrolowane przez drugą/trzeci):

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

Nazywamy je

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

Zwróć uwagę, że używamy [`PI()`](xref:microsoft.quantum.math.pi) funkcji z [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) przestrzeni nazw, aby zdefiniować rotacje w zakresie pi radianów.
Ponadto dzieli się na `Double` (np. `2.0` ), ponieważ podział przez liczbę całkowitą `2` spowoduje zgłoszenie błędu typu. 

> [!TIP]
> `R1(π/2)`i `R1(π/4)` są równoważne `S` `T` operacje i (również w programie `Microsoft.Quantum.Intrinsic` ).


Po zastosowaniu odpowiednich `H` operacji i kontrolowanych rotacji do drugiego i trzeciego qubits:

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

potrzebujemy tylko [`SWAP`](xref:microsoft.quantum.intrinsic.swap) bramy do ukończenia obwodu:

```qsharp
            SWAP(qs[2], qs[0]);
```

Jest to konieczne, ponieważ charakter przekształcenia Quantum Fouriera wyprowadza qubits w odwrotnej kolejności, dzięki czemu zamiany umożliwiają bezproblemowe integrację procedury podrzędnej z większymi algorytmami.

W związku z tym zakończono zapisywanie operacji na poziomie qubit w ramach transformacji Quantum Fouriera w naszej operacji Q #:

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

Nie możemy jednak już wywoływać tego dnia.
Nasze qubits były w stanie $ \ket {0} $ po przydzieleniu ich przez nas i podobnie jak w życiu, w odpowiedzi Q # firma Microsoft powinna pozostawać w ten sam sposób, w jaki znaleźliśmy (lub lepiej).

### <a name="deallocate-qubits"></a>Cofnij przydział qubits

Ponownie dzwonimy [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , aby zobaczyć stan po operacji, a wreszcie Zastosuj [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) do rejestru qubit, aby zresetować nasze qubits do $ \ket {0} $ przed ukończeniem operacji:

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

Wymaganie, aby wszystkie cofnięte alokacje qubits były jawnie ustawione na wartość $ \ket {0} $, jest podstawową funkcją Q #, ponieważ umożliwia ona innym operacjom precyzyjne znać ich stan, gdy zaczynają korzystać z tych samych qubits (ograniczonych zasobów).
Ponadto gwarantuje to, że nie są one Entangled z jakimkolwiek innym qubits w systemie.
Jeśli reset nie zostanie wykonany na końcu `using` bloku alokacji, zostanie zgłoszony błąd czasu wykonywania.

Pełny plik Q # powinien teraz wyglądać następująco:

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


Dzięki plikowi Q # i zakończeniu operacji, nasz program Quantum jest gotowy do wywołania i symulowania.

## <a name="execute-the-program"></a>Wykonaj program

Po zdefiniowaniu naszej operacji Q # w `.qs` pliku musimy teraz wywołać tę operację i obserwować wszystkie zwrócone dane klasyczne.
Na razie nie ma niczego żadnego błędu (należy odwołać, że nasze operacje zdefiniowane powyżej są zwracane `Unit` ), ale w przypadku późniejszej modyfikacji operacji Q # w celu zwrócenia tablicy wyników pomiaru ( `Result[]` ) będziemy rozwiązać ten problem.

Mimo że program Q # jest powszechny w środowisku używanym do wywoływania go, sposób postępowania będzie się różnić. W związku z tym po prostu postępuj zgodnie z instrukcjami wyświetlanymi na karcie odpowiadającej Instalatorowi: Praca z aplikacji wiersza polecenia Q # lub użycie programu hosta w języku Python lub C#.

#### <a name="command-line"></a>[Wiersz polecenia](#tab/tabid-cmdline)

Uruchomienie programu Q # z wiersza polecenia wymaga jedynie niewielkiej zmiany pliku Q #.

Po prostu Dodaj `@EntryPoint()` do wiersza poprzedzającego definicję operacji:

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

Aby uruchomić program, Otwórz terminal w folderze projektu i wprowadź

```dotnetcli
dotnet run
```

Po wykonaniu tych czynności powinny zostać `Message` wyświetlone `DumpMachine` poniższe dane wyjściowe w konsoli programu.


#### <a name="python"></a>[Python](#tab/tabid-python)

Utwórz plik hosta języka Python: `host.py` .

Plik hosta został skonstruowany w następujący sposób: 
1. Najpierw zaimportuje `qsharp` moduł, który rejestruje moduł ładujący modułów pod kątem współdziałania Q. 
    Dzięki temu obszary nazw Q # (np. `NamespaceQFT` zdefiniowane w naszym pliku Q #) są wyświetlane jako moduły języka Python, z których możemy zaimportować operacje pytań i odpowiedzi.
2. Następnie należy zaimportować operacje Q #, które zostaną bezpośrednio wywołane---w tym przypadku `Perform3qubitQFT` .
    Potrzebujemy tylko zaimportować punkt wejścia do programu Q # (tj. _nie_ operacje takie jak `H` i `R1` , które są wywoływane przez inne operacje Q #, ale nigdy nie przez klasycznego hosta).
3. W symulowaniu operacji Q # lub funkcji, użyj formularza, `<Q#callable>.simulate(<args>)` Aby uruchomić je na `QuantumSimulator()` komputerze docelowym. 

> [!NOTE]
> Jeśli chcemy wywołać operację na innym komputerze, na przykład `ResourceEstimator()` po prostu użyjemy `<Q#callable>.estimate_resources(<args>)` .
> Ogólnie rzecz biorąc, operacje Q # są niezależny od na maszynach, na których są uruchamiane, ale niektóre funkcje, takie jak `DumpMachine` mogą zachowywać się inaczej.

4. Podczas wykonywania symulacji wywołanie operacji zwróci wartości zgodnie z definicją w pliku Q #.
    Obecnie nie ma żadnych zwróconych elementów, ale w dalszej części zobaczymy przykład przypisywania i przetwarzania tych wartości.
    Dzięki wykorzystaniu danych z naszych rąk i całkowicie klasycznym, możemy zrobić to niezależnie od tego, co chcemy.

Pełny `host.py` plik powinien być następujący:

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

Uruchom plik języka Python i wydrukowanie w konsoli powinny być widoczne poniższe dane `Message` `DumpMachine` wyjściowe. 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

Postępując zgodnie z tymi samymi instrukcjami w [przewodniku instalacji](xref:microsoft.quantum.install.cs), Utwórz plik hosta C# i zmień jego nazwę na `host.cs` .

Host języka C# ma cztery części:
1. Konstruuje symulator kwantowy.
    W poniższym kodzie jest to zmienna `qsim` .
2. Oblicza wszystkie argumenty wymagane dla algorytmu kwantowego.
    Brak w tym przykładzie.
3. Uruchamia algorytm kwantowy. 
    Każda operacja języka Q# generuje klasę języka C# o tej samej nazwie. 
    Ta klasa ma metodę `Run`, która **asynchronicznie** wykonuje operację.
    Wykonanie jest asynchroniczne, ponieważ wykonanie na rzeczywistym sprzęcie będzie asynchroniczne. 
    Ponieważ `Run` Metoda jest asynchroniczna, wywoływana jest `Wait()` Metoda; ta funkcja blokuje wykonywanie do momentu zakończenia zadania i zwraca wynik synchronicznie. 
4. Przetwarza zwrócony wynik operacji.
    Na razie operacja nie zwraca żadnej wartości.


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
Uruchom aplikację, a dane wyjściowe powinny być zgodne z poniższymi.
Program zostanie zakończony po naciśnięciu klawisza.
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

Gdy jest wywoływana w symulatorze pełnego stanu, program `DumpMachine()` udostępnia te mutliple reprezentacje wavefunction stanu Quantum. Możliwe stany $ngo systemu $-qubit mogą być reprezentowane przez $2 ^ n $ Stany obliczeniowe, z których każdy ma odpowiedni współczynnik złożony (po prostu amplituda i faza).
Podstawowe Stany są zgodne ze wszystkimi możliwymi binarnymi ciągami o długości $n $---, czyli wszystkie możliwe kombinacje qubit Stanów $ \ket {0} $ i $ \ket {1} $, gdzie każda cyfra binarna odnosi się do poszczególnych qubit.

Pierwszy wiersz zawiera komentarz z identyfikatorami odpowiednich qubits w ich znaczącej kolejności.
Qubit `2` "najbardziej znaczący" oznacza, że w binarnej reprezentacji wektora stanu podstawy $ \ket{i} $ stan qubit `2` odpowiada cyfrom z lewej strony. Na przykład $ \ket {6} = \ket {110} $ składa się qubits `2` i `1` oba w $ \ket {1} $ i qubit `0` w $ \ket {0} $.


Pozostała część wierszy zawiera opis amplitudy prawdopodobieństwa pomiaru wektora stanu \ket{i} $ w obu formatach kartezjańskiego i biegunowych.
Szczegółowo dla pierwszego wiersza naszego stanu danych wejściowych $ \ket {000} $:
* **`|0>:`** Ten wiersz odnosi się do `0` stanu podstawowego obliczenia (w związku z tym, że nasza początkowa alokacja stanu początkowego to $ \ket {000} $, oczekujemy, że będzie to jedyny stan z amplitudą prawdopodobieństwa w tym punkcie).
* **`1.000000 +  0.000000 i`**: amplituda prawdopodobieństwa w formacie kartezjańskiego.
* **` == `**: `equal` znak oddziela obie równoważne reprezentacje.
* **`********************`**: Graficzna reprezentacja rozmiaru, liczba `*` jest proporcjonalna do prawdopodobieństwa mierzenia tego wektora stanu. 
* **`[ 1.000000 ]`**: wartość liczbowa wielkości
* **`    ---`**: Graficzna reprezentacja fazy amplitudy.
* **`[ 0.0000 rad ]`**: wartość liczbowa fazy (w radianach).

Obie wartości i fazy są wyświetlane ze graficzną reprezentacją. Reprezentacja wielkości jest prosta: pokazuje pasek `*` , a im wyższe prawdopodobieństwo, tym większy jest pasek. W przypadku fazy należy zapoznać się z tematem [testowanie i debugowanie: funkcje zrzutu](xref:microsoft.quantum.guide.testingdebugging#dump-functions) dla możliwych reprezentacji symboli w oparciu o zakresy kątów.


W wyniku tego drukowane dane wyjściowe pokazują, że nasze bramy zaprogramowane są przekształcone w nasz stan z

$ $ \ket{\psi} \_ {Initial} = \ket {000} $ $

na 

$ $ \begin{align} \ket{\psi} \_ {Final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $

Co to jest dokładne zachowanie transformacji Fouriera 3-qubit. 

Jeśli chcesz wiedzieć się na to, w jaki sposób mają wpływ inne Stany wejścia, zachęcamy do rozwinięcia z zastosowaniem operacji qubit przed przekształceniem.

## <a name="adding-measurements"></a>Dodawanie pomiarów

Niestety, kamień Quantum Mechanics informuje nas, że prawdziwy system Quantum nie może mieć takiej `DumpMachine` funkcji. Zamiast tego należy wymusić Wyodrębnienie informacji poprzez pomiary, które generalnie nie tylko kończą się niepowodzeniem, aby zapewnić nam pełny stan Quantum, ale może też znacząco zmienić sam system.
Istnieje wiele różnych pomiarów jednostek Quantum, ale będziemy skupić się na najważniejszych pomiarach na jednym qubits.
W przypadku pomiaru w danej lokalizacji (np. obliczenia obliczanej na podstawie $ \{ \ket {0} , \ket {1} \} $) stan qubit jest przewidywany w zależności od stanu,---w związku z tym zniszczenia wszystkich nadmiaru między nimi.

Aby zaimplementować pomiary w ramach programu Q #, używamy `M` operacji (z `Microsoft.Quantum.Intrinsic` ), która zwraca `Result` Typ.

Najpierw zmodyfikujemy naszą `Perform3QubitQFT` operację, aby zwrócić tablicę wyników pomiarów, `Result[]` zamiast `Unit` .

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>Zdefiniuj i zainicjuj `Result[]` tablicę

Przed przystąpieniem do przydzielenia qubits (tj. przed `using` instrukcją) deklarujemy i powiążemy tę tablicę o długości-3 (jedną `Result` dla każdej qubit): 

```qsharp
        mutable resultArray = new Result[3];
```

Słowo kluczowe "wychodzące" `mutable` `resultArray` pozwala na przykład, aby zmienna była ponownie powiązana w---kodu, podczas dodawania wyników pomiarów.

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>Wykonaj pomiary w `for` pętli i Dodaj wyniki do tablicy

Po wykonaniu operacji transformacji Fouriera wewnątrz `using` bloku Wstaw następujący kod:

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)Funkcja wywołana na tablicy (np. Nasza Tablica elementów qubits `qs` ) zwraca zakres przez indeksy tablicy. W tym miejscu używamy jej w `for` pętli do sekwencyjnego mierzenia poszczególnych qubit przy użyciu `M(qs[i])` instrukcji.
Każdy `Result` Typ mierzony (albo `Zero` `One` ) jest następnie dodawany do odpowiedniej pozycji indeksu w `resultArray` instrukcji Update-and-Reassign.

> [!NOTE]
> Składnia tej instrukcji jest unikatowa dla Q #, ale odpowiada podobnemu ponownemu przypisaniu zmiennej, która jest `resultArray[i] <- M(qs[i])` widoczna w innych językach, takich jak F # i R.

Słowo kluczowe `set` jest zawsze używane do ponownego przypisania zmiennych powiązanych przy użyciu `mutable` .

#### <a name="return-resultarray"></a>Przesłać`resultArray`

Ze względu na wszystkie trzy qubits i wyniki dodane do `resultArray` , firma Microsoft bezpiecznie resetuje i cofa alokację qubits.
Po `using` zamknięciu bloku Wstaw

```qsharp
        return resultArray;
```
Aby ostatecznie zwrócić dane wyjściowe naszej operacji. 

### <a name="understanding-the-effects-of-measurement"></a>Zrozumienie efektów pomiaru

Zmieńmy położenie naszych `DumpMachine` funkcji w celu wygenerowania stanu przed pomiarami i po nich.
Kod operacji końcowej powinien wyglądać następująco: 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

Jeśli pracujesz z wiersza polecenia, zwracana tablica zostanie po prostu wydrukowana bezpośrednio do konsoli na końcu wykonywania.
W przeciwnym razie zaktualizuj program hosta, aby przetworzyć zwróconą tablicę.

#### <a name="command-line"></a>[Wiersz polecenia](#tab/tabid-cmdline)

Aby lepiej zrozumieć zwracaną tablicę, która zostanie wydrukowana w konsoli programu, możemy dodać kolejną `Message` w pliku Q # tuż przed `return` instrukcją:

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

Uruchom projekt, a dane wyjściowe powinny wyglądać podobnie do następujących:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

Zaktualizuj program Python do poniższego:

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

Uruchom plik, a dane wyjściowe powinny wyglądać podobnie do następujących:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

Teraz, gdy nasza operacja zwraca wynik, Zastąp wywołanie metody `Wait()` pobraniem `Result` właściwości. Nadal wykonuje to samo Synchronicity omówione wcześniej i można bezpośrednio powiązać tę wartość ze zmienną `measurementResult` .

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

Uruchom projekt, a dane wyjściowe powinny wyglądać podobnie do następujących:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

To wyjście ilustruje kilka różnych rzeczy:
1. Porównanie zwróconego wyniku do wstępnego pomiaru `DumpMachine` nie oznacza, że _nie_ zilustrowano w nim położeniu QFT.
    Pomiar zwraca tylko jeden stan podstawy, z prawdopodobieństwem określonym przez amplitudę tego stanu w wavefunction systemu.
2. Na podstawie miary po pomiarach `DumpMachine` zobaczymy, że pomiar _zmienia_ sam stan, umieszczając go od początkowego nadpozycji względem stanów w pojedynczym stanie, który odnosi się do zmierzonej wartości.

Jeśli udało nam się powtórzyć tę operację wiele razy, zobaczymy statystyki wynikowe, aby zilustrować równomiernie ważoną w stanie QFT, który umożliwia uzyskanie losowego wyniku dla każdego zrzutu.
_Jednak_oprócz są niewydajne i nadal nieidealne, może to jednak jedynie odtworzyć względne amplitudy Stanów bazowych, a nie względne fazy między nimi.
Ten ostatni nie jest problemem w tym przykładzie, ale zobaczysz względne fazy, jeśli podano bardziej złożone dane wejściowe QFT niż $ \ket {000} $.

#### <a name="partial-measurements"></a>Pomiary częściowe 
Aby dowiedzieć się, jak pomiary tylko niektóre qubits rejestru mogą mieć wpływ na stan systemu, spróbuj dodać następujące elementy wewnątrz `for` pętli, po linii pomiaru:
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

Należy pamiętać, że w celu uzyskania dostępu do `IntAsString` funkcji należy dodać 
```qsharp
    open Microsoft.Quantum.Convert;
```
z resztą instrukcji przestrzeni nazw `open` .

W wynikowym wyjściu zobaczysz stopniowe rzutowanie do podobszarów w miarę mierzenia qubit.


## <a name="use-the-q-libraries"></a>Korzystanie z bibliotek Q #
Jak już wspomniano w wprowadzeniu, większość siły Q nie działa w ten sam sposób, że pozwala to na streszczenie martw z poszczególnymi qubitsami.
W rzeczywistości, jeśli chcesz opracowywać kompletne, odpowiednie programy Quantum, martw się o to, czy `H` operacja przejdzie przed lub po określonej rotacji, spowoduje spowolnienie pracy. 

Biblioteki Q # zawierają operację [QFT](xref:microsoft.quantum.canon.qft) , którą można po prostu wykonać i zastosować do dowolnej liczby qubits.
Aby wymusić to próbkę, zdefiniuj nową operację w pliku Q # o tej samej zawartości `Perform3QubitQFT` , ale z wszystko od pierwszego `H` do `SWAP` zastąpione przez dwie proste elementy:
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
Pierwszy wiersz po prostu tworzy [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) wyrażenie przydzieloną tablicę qubits, czyli to `qs` , co operacja [QFT](xref:microsoft.quantum.canon.qft) jest wykonywana jako argument.
Odnosi się to do kolejności indeksu qubits w rejestrze.

Aby mieć dostęp do tych operacji, należy dodać `open` instrukcje dla odpowiednich przestrzeni nazw na początku pliku Q #:
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

Teraz Dostosuj program hosta, aby wywoływać nazwę nowej operacji (np. `PerformIntrinsicQFT` ) i nadaj jej Whirl.

Aby zobaczyć prawdziwą korzyść z używania operacji Q # Library, Zmień liczbę qubits na coś innego niż `3` :
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
Z tego względu można zastosować odpowiednie QFT dla dowolnej liczby qubits, bez konieczności zajmowania się komunikatami o wykorzystaniu nowych `H` operacji i obrotów na każdym qubit.

Należy pamiętać, że symulator usługi Quantum trwa wykładniczo więcej czasu, gdy zwiększasz liczbę qubits---dokładniej, dlaczego przejdziemy do prawdziwego sprzętu Quantum.














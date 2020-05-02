---
title: 'Wyrażenia Q #'
description: 'Dowiedz się, jak określać, odwoływać i łączyć stałe, zmienne, operatory, operacje i funkcje jako wyrażenia w Q #.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683925"
---
# <a name="expressions"></a>Wyrażenia

## <a name="grouping"></a>Grupowanie

Uwzględniając dowolne wyrażenie, to samo wyrażenie ujęte w nawiasy jest wyrażeniem tego samego typu.
Na przykład, `(7)` jest `Int` wyrażeniem, `([1,2,3])` jest wyrażeniem typu Array `Int`-s i `((1,2))` jest wyrażeniem typu. `(Int, Int)`

Równoważność między wartościami prostymi a krotkami jednoelementowymi opisanymi w [modelu typu](xref:microsoft.quantum.language.type-model#tuple-types) usuwa niejednoznaczność między `(6)` grupami i `(6)` jako spójną krotką.

## <a name="symbols"></a>Symbole

Nazwa symbolu powiązanego lub przypisana do wartości typu `'T` jest wyrażeniem typu. `'T`
Na przykład, jeśli symbol `count` jest powiązany z wartością `5`całkowitą, `count` jest wyrażeniem liczby całkowitej.

## <a name="numeric-expressions"></a>Wyrażenia liczbowe

Wyrażenia liczbowe są wyrażeniami typu `Int`, `BigInt`, lub `Double`.
Oznacza to, że są to liczby całkowite lub zmiennoprzecinkowe.

`Int`literały w Q # są identyczne z literałami całkowitymi w języku C#, z tą różnicą, że nie są wymagane żadne końcowe litery "l" lub "L" (lub dozwolone).
Liczby całkowite szesnastkowe i binarne są obsługiwane odpowiednio prefiksem "0x" i "0b".

`BigInt`literały w Q # są identyczne z ciągami Big Integer w programie .NET, z końcowym "l" lub "L".
Szesnastkowe duże liczby całkowite są obsługiwane z prefiksem "0x".
W ten sposób wszystkie prawidłowe zastosowania `BigInt` literałów są następujące:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`literały w Q # są takie same jak literały podwójne w języku C#, z tą różnicą, że nie jest wymagane końcowe "d" lub "D" (lub dozwolone).

Jeśli wyrażenie tablicy dowolnego `Int` typu elementu, wyrażenie może być utworzone przy użyciu `Length` wbudowanej funkcji, z wyrażeniem tablicy ujętym w nawiasy `(` i. `)`
Na przykład, jeśli `a` jest powiązany z tablicą, `Length(a)` jest wyrażeniem liczby całkowitej.
Jeśli `b` jest tablicą tablic liczb całkowitych, `Int[][]`, a następnie `Length(b)` jest liczbą tablic `b`w, i `Length(b[1])` jest liczbą liczb całkowitych w drugiej tablicy podrzędnej w. `b`

Uwzględniając dwa `+`wyrażenia liczbowe tego samego typu, operatory binarne, `-` `*`, i `/` mogą być używane do tworzenia nowego wyrażenia liczbowego.
Typ nowego wyrażenia będzie taki sam jak typy wyrażeń składowych.

W przypadku dwóch wyrażeń całkowitych operator `^` binarny (potęga) może służyć do tworzenia nowego wyrażenia liczb całkowitych.
Podobnie, `^` można użyć z dwoma wyrażeniami podwójnymi, aby utworzyć nowe wyrażenie podwójne.
Na koniec `^` , może być używany z dużą liczbą całkowitą z lewej strony i liczbą całkowitą z prawej strony, aby utworzyć nowe wyrażenie Big Integer.
W takim przypadku drugi parametr musi pasować do 32 bitów; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.

W przypadku dwóch wyrażeń całkowitych lub dużych liczb całkowitych można utworzyć nowe wyrażenie typu Integer lub Big Integer `%` przy użyciu operatorów ( `&&&` moduł), (bitowe `|||` and), (BITOWEGO or `^^^` ) lub (bitowe XOR).

W przypadku wyrażenia typu Integer lub Big Integer po lewej stronie i wyrażenia liczb całkowitych po prawej stronie operatory `<<<` (arytmetyczne przesunięcie w lewo) `>>>` lub (arytmetyczne przesunięcie w prawo) mogą być używane do tworzenia nowego wyrażenia z tym samym typem co lewe wyrażenie.

Drugi parametr (wartość przesunięcia) dla operacji Shift musi być większy lub równy zero; zachowanie dla ujemnych kwot przesunięcia jest niezdefiniowane.
Wartość przesunięcia dla operacji przesunięcia musi być również zgodna z 32 bitowymi; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.
Jeśli liczba, która ma zostać przesunięta jest liczbą całkowitą, jest interpretowana `mod 64`wartość przesunięcia. oznacza to, że przesunięcie 1 i przesunięcie 65 mają ten sam efekt.

W przypadku wartości liczb całkowitych i dużych liczb całkowitych przesunięcia są arytmetyczne.
Przesunięcie wartości ujemnej w lewo lub w prawo spowoduje powstanie liczby ujemnej.
Oznacza to, że przesunięcie jeden krok w lewo lub w prawo jest dokładnie takie samo jak mnożenie lub dzielenie odpowiednio przez 2.

Dzielenie liczb całkowitych i moduł całkowity są zgodne z tym samym zachowaniem dla liczb ujemnych w języku C#.
Oznacza to, `a % b` że będzie zawsze mieć ten sam znak `a`jako i `b * (a / b) + a % b` zawsze będzie równa `a`się.
Przykład:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Dzielenie z dużymi liczbami całkowitymi i moduł działa w taki sam sposób.

Mając każde wyrażenie liczbowe, nowe wyrażenie może być utworzone za pomocą operatora `-` jednoargumentowego.
Nowe wyrażenie będzie tego samego typu co wyrażenie elementu.

W przypadku dowolnego wyrażenia typu Integer lub Big Integer nowe wyrażenie tego samego typu może być sformułowane przy użyciu `~~~` operatora jednoargumentowego (dopełnienie bitowe).

## <a name="boolean-expressions"></a>Wyrażenia logiczne

Dwie `Bool` wartości literału są `true` i `false`.

Uwzględniając wszystkie dwa wyrażenia tego samego typu pierwotnego, operatory `==` i `!=` mogą być używane do konstruowania `Bool` wyrażenia.
Wyrażenie będzie prawdziwe, jeśli dwa wyrażenia są równe, i wartość false, jeśli nie.

Wartości typów zdefiniowanych przez użytkownika mogą nie być porównywane. można porównać tylko ich nieopakowane wartości. Na przykład przy użyciu operatora `!` "unotocz" (wyjaśnione na [stronie modelu typu Q #](xref:microsoft.quantum.language.type-model#user-defined-types)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Porównywanie równości `Qubit` dla wartości jest równość tożsamości; oznacza to, czy dwa wyrażenia identyfikują ten sam qubit.
Stan dwóch qubits nie jest porównywany, dostępny, mierzony ani modyfikowany przez to porównanie.

Porównywanie równości `Double` dla wartości może być mylące ze względu na efekt zaokrąglenia.
Na przykład `49.0 * (1.0/49.0) != 1.0`.

Uwzględniając wszystkie `>`dwa wyrażenia liczbowe, operatory binarne, `<` `>=`, i `<=` mogą być używane do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli pierwsze wyrażenie jest odpowiednio większe niż, mniejsze niż, większe niż lub równe lub mniejsze lub równe drugiemu wyrażeniu.

W przypadku wszystkich dwóch wyrażeń logicznych operatory `and` i `or` mogą być używane do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli oba wyrażenia (komp. or lub Both) mają wartość true.

Mając każde wyrażenie logiczne, operator `not` jednoargumentowy może służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli wyrażenie elementu składowego ma wartość false.

## <a name="string-expressions"></a>Wyrażenia ciągów

Funkcja Q # umożliwia używanie ciągów w `fail` instrukcji i funkcji `Log` standardowej.

Ciągi w Q # są literałami lub interpolowanymi ciągami.
Literały ciągu są podobne do prostych literałów ciągu w większości języków: sekwencji znaków Unicode ujętych w podwójne cudzysłowy `"`.
Wewnątrz `\` ciągu znak ukośnika odwrotnego może być używany do ucieczki podwójnego znaku cudzysłowu i do wstawiania nowej linii `\n`jako, powrotu karetki jako `\r`i karty jako. `\t`
Przykład:

```qsharp
"\"Hello world!\", she said.\n"
```

Składnia Q # dla interpolacji ciągów jest podzbiorem składni języka C# 7,0; Usługa Q # nie obsługuje ciągów interpolowanych Verbatim (wiele wierszy).
Zobacz [*interpolowane ciągi*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) dla składni języka C#.

Wyrażenia wewnątrz ciągu interpolowanego są zgodne z składnią Q #, a nie składnią języka C#.
Dowolne prawidłowe wyrażenie Q # może pojawić się w ciągu interpolowanym.

## <a name="qubit-expressions"></a>Wyrażenia qubit

Jedyne `Qubit` wyrażenia to symbole, które są powiązane `Qubit` z wartościami lub tablicami `Qubit` elementów tablic.
Brak `Qubit` literałów.

## <a name="pauli-expressions"></a>Wyrażenia Pauli

Cztery `Pauli` wartości `PauliI`,, `PauliX` `PauliY`, i `PauliZ`, są prawidłowymi `Pauli` wyrażeniami.

Inaczej niż to, jedyne `Pauli` wyrażenia to symbole, które są powiązane `Pauli` z wartościami lub tablicami `Pauli` elementów tablic.

## <a name="result-expressions"></a>Wyrażenia wynikowe

Dwie `Result` wartości `One` i `Zero`są prawidłowymi `Result` wyrażeniami.

Inaczej niż to, jedyne `Result` wyrażenia to symbole, które są powiązane `Result` z wartościami lub tablicami `Result` elementów tablic.
W szczególności należy zauważyć, `One` że nie jest taka sama jak liczba `1`całkowita i nie ma żadnej bezpośredniej konwersji między nimi.
Ta sama wartość dotyczy `Zero` i. `0`

## <a name="range-expressions"></a>Wyrażenia zakresu

Każde trzy `Int` `start`wyrażenie, `step`, i `stop`, `start .. step .. stop` jest wyrażeniem zakresu, którego pierwszy element jest `start`, drugi element jest `start+step`, trzeci element jest `start+step+step`itp., do do `stop` .
Zakres może być pusty, jeśli na przykład `step` jest wartością dodatnią i `stop < start`.
`stop` Ostatnim elementem zakresu będzie, jeśli różnica między `start` i `stop` jest całkowitą wielokrotnością; `step` oznacza to, że zakres jest włącznie na obu końcach.

Uwzględniając wszystkie dwa `Int` wyrażenia `start` i `stop`, `start .. stop` jest wyrażenie zakresu, które jest równe `start .. 1 .. stop`.
Należy zauważyć, że implikowana `step` wartość to + 1 `stop` , nawet jeśli `start`jest mniejsza niż; w takim przypadku zakres jest pusty.

Oto kilka przykładowych zakresów:

- `1..3`jest zakresem 1, 2, 3.
- `2..2..5`jest zakresem od 2 do 4.
- `2..2..6`jest zakresem 2, 4, 6.
- `6..-2..2`jest zakresem 6, 4, 2.
- `2..1`jest pustym zakresem.
- `2..6..7`jest zakresem 2.
- `2..2..1`jest pustym zakresem.
- `1..-1..2`jest pustym zakresem.

## <a name="callable-expressions"></a>Możliwe do przewyrażenia

Możliwy do przeprowadzenia literał jest nazwą operacji lub funkcji zdefiniowanej w zakresie kompilacji.
Na przykład, `X` to literał operacji odwołujący się do standardowej operacji `X` biblioteki i `Message` jest literalną funkcją, która odwołuje się do standardowej `Message` funkcji biblioteki.

Jeśli operacja obsługuje `Adjoint` Funktor, `Adjoint op` to wyrażenie operacji.
Podobnie, jeśli operacja obsługuje `Controlled` Funktor, a następnie `Controlled op` jest wyrażeniem operacji.
Typy tych wyrażeń są określone w [funktory](xref:microsoft.quantum.language.type-model#functors).

Funktory (`Adjoint` i `Controlled`) wiąże się bardziej ściśle niż wszystkie inne operatory, z wyjątkiem operatora `!` rozwinięcia i indeksowania tablicy `[]`przy użyciu.
W ten sposób obowiązują wszystkie kwestie prawne, przy założeniu, że operacje obsługują użycie funktory:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

Możliwy do oddzielenia literału można użyć jako wartości, powiedzmy, aby przypisać do zmiennej lub przekazać do innego elementu.
W takim przypadku, jeśli wywoływany ma parametry typu, muszą one być podane jako część wartości możliwej do napisania.
Wartość możliwej do odwoływać nie może mieć żadnych nieokreślonych parametrów typu.

Na przykład jeśli `Fun` jest funkcją z podpisem `'T1->Unit`:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Wywoływanie wyrażeń wywołania

Dane wyrażenie możliwego do wywołania (operacji lub funkcji) i wyrażenie spójnej kolekcji typu wejściowego w podpisie, wyrażenie wywoływania może być sformułowane przez dołączenie wyrażenia krotki do możliwego do wywołania wyrażenia.
Typ wyrażenia wywołania jest typem wyjściowym podpisu, który ma zostać wywołany.

Na `Op` przykład jeśli jest operacją z podpisem `((Int, Qubit) => Double)`, `Op(3, qubit1)` jest wyrażeniem typu `Double`.
Podobnie, jeśli `Sin` jest funkcją z podpisem `(Double -> Double)`, `Sin(0.1)` jest wyrażeniem typu `Double`.
Na koniec, `Builder` jeśli jest funkcją z podpisem `(Int -> (Int -> Int))`, `Builder(3)` to funkcja od do int.

Wywołanie wyniku wyrażenia z wartościami możliwymi do wywołania wymaga dodatkowej pary nawiasów wokół wartościowego wyrażenia.
W związku z tym, aby wywołać wynik `Builder` wywołania z poprzedniego akapitu, poprawna składnia to:

```qsharp
(Builder(3))(2)
```

W przypadku wywołania sparametryzowanego typu, rzeczywiste parametry typu można określić w nawiasach `<` kątowych i `>` po wyrażeniu możliwym do wywołania.
Zwykle nie jest to konieczne, ponieważ kompilator Q # wykryje rzeczywiste typy.
Jest to wymagane w przypadku częściowej aplikacji (patrz poniżej), jeśli argument z parametrem sparametryzowanym nie został określony.
Jest to również czasami przydatne, gdy przekazywanie operacji z różnymi Funktor obsługuje do możliwego do odwoływać.

Na przykład, jeśli `Func` ma `('T1, 'T2, 'T1) -> 'T2`sygnaturę `Op1` i `Op2` `(Qubit[] => Unit is Adj)`ma sygnaturę i `Op3` ma sygnaturę `(Qubit[] => Unit)`, do `Func` wywołania `Op1` jako pierwszy argument, `Op2` jako drugi i `Op3` jako trzeci:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Specyfikacja typu jest wymagana, ponieważ `Op3` i `Op1` ma różne typy, więc kompilator będzie traktować ten sposób jako niejednoznaczny bez specyfikacji.

### <a name="partial-application"></a>Aplikacja częściowa

Po otrzymaniu możliwego do przetworzenia wyrażenia można utworzyć nowe wywoływanie, dostarczając podzestaw argumentów do obiektu.
Jest to nazywane _częściową aplikacją_.

W Q #, częściowo zastosowane wywołanie jest wyrażane przez zapisanie wyrażenia zwykłego wywołania, ale przy użyciu znaku podkreślenia `_`, dla nieokreślonych argumentów.
Wynikowe wywoływanie ma ten sam typ wyniku co podstawowy możliwy do przetworzenie i te same specjalizacje dla operacji.
Typ danych wejściowych częściowej aplikacji jest po prostu oryginalnym typem z określonymi argumentami.

Jeśli zmienna modyfikowalna jest przenoszona jako określony argument podczas tworzenia częściowej aplikacji, używana jest bieżąca wartość zmiennej.
Późniejsze zmiany wartości zmiennej nie wpłyną na częściową aplikację.

Na przykład, jeśli `Op` ma typ `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))`ma typ `(((Qubit,Qubit), Double) => Unit is Adj)`, a więc ma `Op(5,_)`.
- `Op(_,(_,1.0))`ma typ `((Int, (Qubit,Qubit)) => Unit is Adj)`.
- `Op(_,((q1,q2),_))`ma typ `((Int,Double) => Unit is Adj)`.
   Należy zauważyć, że w tym miejscu zastosowano jednokrotną równoważność krotki.

Jeśli częściowo zastosowane wywołanie ma parametry typu, których nie można wywnioskować przez kompilator, muszą one być dostarczone w lokacji wywołania.
Częściowa aplikacja nie może mieć żadnych nieokreślonych parametrów typu.

Na przykład, jeśli `Op` ma typ `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>Rekursja

Liczba wywoływanych Q może być bezpośrednio lub pośrednio cykliczna.
Oznacza to, że operacja lub funkcja może wywołać się sama lub wywołać inne wywołanie, które bezpośrednio lub pośrednio wywołuje operację, którą można wywołać.

Istnieją jednak dwa ważne komentarze dotyczące korzystania z rekursji:

- Użycie rekursji w operacjach może zakłócać pewne optymalizacje.
  Może to mieć znaczny wpływ na czas wykonywania algorytmu.
- W przypadku wykonywania na rzeczywistym urządzeniu Quantum przestrzeń stosu może być ograniczona, a więc Szczegółowa rekursja może prowadzić do błędu czasu wykonywania.
  W szczególności kompilator Q # i środowisko wykonawcze nie identyfikują i nie optymalizują rekursji końcowego.

## <a name="tuple-expressions"></a>Wyrażenia krotki

Literał krotki to sekwencja wyrażeń elementu odpowiedniego typu, rozdzielona przecinkami, ujęta w `(` i. `)`
Na przykład `(1, One)` jest `(Int, Result)` wyrażeniem.

W przypadku innych niż literały jedynymi wyrażeniami krotek są symbole, które są powiązane z wartościami krotki, elementami tablicy tablic krotek i wywoływanie wywołań, które zwracają krotki.

## <a name="user-defined-type-expressions"></a>Wyrażenia typu zdefiniowanego przez użytkownika

Literał typu zdefiniowanego przez użytkownika składa się z nazwy typu, a następnie literału krotki typu krotki podstawowej typu.
Na przykład, jeśli `IntPair` jest typem zdefiniowanym przez użytkownika na `(Int, Int)`podstawie, `IntPair(2,3)` byłby on prawidłowym literałem tego typu.

Oprócz literałów jedynymi wyrażeniami typu zdefiniowanego przez użytkownika są symbole, które są powiązane z wartościami tego typu, elementy tablicy tablic tego typu i wywoływanie wywołań, które zwracają ten typ.

## <a name="unwrap-expressions"></a>Odpakowywanie wyrażeń

W Q # operator rozwinięcia jest końcowym wykrzyknikiem `!`.
Na przykład, jeśli `IntPair` jest typem zdefiniowanym przez użytkownika z typem `(Int, Int)`źródłowym i `s` była zmienną z wartością `IntPair(2,3)`, wówczas `s!` zostałby. `(2,3)`

Dla typów zdefiniowanych przez użytkownika, zdefiniowanych w warunkach innych typów zdefiniowanych przez użytkownika. operatora rozwinięcia można powtórzyć; na przykład `s!!` wskazuje podwójnie nieopakowaną wartość `s`.
W takim przypadku `WrappedPair` , jeśli jest typem zdefiniowanym przez użytkownika z `IntPair`typem źródłowym `t` i jest zmienną z wartością `WrappedPair(IntPair(1,2))`, wówczas `t!!` zostałby `(1,2)`.

`!` Operator ma wyższy priorytet niż wszystkie inne operatory inne niż `[]` dla indeksowania tablicy i dzielenia.
`!`i `[]` Powiązywanie pozycyjne; oznacza to, `a[i]![3]` że powinna być odczytana `((a[i])!)[3]`jako `i`: Weź element " `a`th", Odpakuj go, a następnie Pobierz trzeci element nieopakowanej wartości (która musi być tablicą).

Pierwszeństwo `!` operatora ma jeden wpływ, który może nie być oczywisty.
Jeśli funkcja lub operacja zwraca wartość, która staje się nieopakowana, wywołanie funkcji lub operacji musi być ujęte w nawiasy, tak aby krotka argumentu była powiązana z wywołaniem, a nie z odwinięciem.
Przykład:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Wyrażenia tablic

Literał tablicowy jest sekwencją co najmniej jednego wyrażenia elementu, rozdzielonych przecinkami, ujęty w `[` i `]`.
Wszystkie elementy muszą być zgodne z tym samym typem.

Jeśli wspólny typ elementu jest operacją lub typem funkcji, wszystkie elementy muszą mieć te same typy danych wejściowych i wyjściowych.
Typ elementu tablicy będzie obsługiwał wszystkie funktory, które są obsługiwane przez wszystkie elementy.
Na przykład jeśli `Op1` `Op2`,, i `Op3` wszystkie są `Qubit[] => Unit`, ale `Op1` obsługuje `Adjoint`, `Op2` obsługuje `Controlled`i `Op3` obsługuje obie:

- `[Op1, Op2]`jest tablicą `(Qubit[] => Unit)` operacji.
- `[Op1, Op3]`jest tablicą `(Qubit[] => Unit is Adj)` operacji.
- `[Op2, Op3]`jest tablicą `(Qubit[] => Unit is Ctl)` operacji.

Puste literały tablicowe `[]`,, są niedozwolone.
Zamiast używać `new ★[0]`, gdzie `★` jest jako symbol zastępczy dla odpowiedniego typu, umożliwia utworzenie odpowiedniej tablicy o długości zero.

Mając daną dwie tablice tego samego typu, operator binarny `+` może służyć do tworzenia nowej tablicy, która jest połączeniem dwóch tablic.
Na przykład `[1,2,3] + [4,5,6]` ma `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Tworzenie tablicy

Uwzględniając typ i `Int` wyrażenie, `new` operator może służyć do przydzielenia nowej tablicy o danym rozmiarze.
Na przykład `new Int[i+1]` przydzieli nową `Int` tablicę z `i+1` elementami.

Elementy nowej tablicy są inicjowane z wartością domyślną zależną od typu.
W większości przypadków jest to pewna odmiana zero.

W przypadku qubits i elementów, które są odwołaniami do jednostek, nie ma żadnej rozsądnej wartości domyślnej.
W tym przypadku dla tych typów wartość domyślna to nieprawidłowe odwołanie, którego nie można użyć bez powodowania błędu czasu wykonywania.
Jest to podobne do odwołania o wartości null w językach, takich jak C# lub Java.
Tablice zawierające qubits lub elementy wywoływane muszą zostać prawidłowo zainicjowane przy użyciu wartości innych niż domyślne, zanim ich elementy mogą być bezpiecznie używane. Odpowiednie procedury inicjowania można znaleźć w <xref:microsoft.quantum.arrays>temacie.

Wartości domyślne dla każdego typu są następujące:

Typ | Domyślny
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _Nieprawidłowy qubit_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | Pusty zakres,`1..1..0`
 `Callable` | _nieprawidłowe wywoływanie_
 `Array['T]` | `'T[0]`

Typy krotek są inicjowane element po elemencie.


### <a name="jagged-arrays"></a>Tablice nieregularne

Tablica nieregularna, czasami nazywana "tablicą tablicową", jest tablicą, której elementy są tablicami. Elementy tablicy nieregularnej mogą mieć różne rozmiary. Poniższy przykład pokazuje, jak zadeklarować i zainicjować tablicę nieregularną reprezentującą tabelę mnożenia.

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {

    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```


### <a name="array-slices"></a>Wycinki tablicy

Jeśli wyrażenie tablicowe i `Range` wyrażenie, nowe wyrażenie może być utworzone przy użyciu operatora wycinka Array `[` i. `]`
Nowe wyrażenie będzie tego samego typu co tablica i będzie zawierać elementy tablicy indeksowane przez elementy `Range`w kolejności zdefiniowanej przez. `Range`
Na przykład, jeśli `a` jest powiązany z tablicą `Double`s, a następnie `a[3..-1..0]` jest `Double[]` wyrażeniem zawierającym cztery pierwsze elementy z `a` , ale w odwrotnej kolejności, jak pojawiają `a`się w.

Jeśli wartość `Range` jest pusta, powstający wycink tablicy będzie zerem o zerowej długości.

Jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, musi być ujęte w nawiasy klamrowe w celu wycięcia.
Na przykład, jeśli `a` i `b` są obie tablice `Int`s, wycinek z łączenia będzie wyrażony jako:

```qsharp
(a+b)[1..2..7]
```

Wszystkie tablice w Q # są oparte na zero.
Oznacza to, że pierwszy element tablicy `a` jest zawsze. `a[0]`

Począwszy od naszego 0,8 wydania, obsługujemy kontekstowe wyrażenia dla dzielenia zakresów. W szczególności wartości początkowe i końcowe zakresu mogą zostać pominięte w kontekście wyrażenia wycinka zakresu. W takim przypadku kompilator zastosuje następujące reguły w celu wywnioskowania zamierzonych ograniczników dla zakresu. 

Na przykład, jeśli wartość początkowa zakresu zostanie pominięta, wywnioskowana wartość początkowa 
- ma wartość zero, jeśli nie określono żadnego kroku lub określony krok jest dodatni i 
- jest długością tablicy z wycinkami minus jeden, jeśli określony krok jest ujemny. 

W przypadku pominięcia wartości końcowej zakresu, wywnioskowana wartość końcowa 
- jest długością tablicy wycinka minus jeden, jeśli żaden krok nie jest określony lub określony krok jest dodatni i 
- ma wartość zero, jeśli określony krok jest ujemny. 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

## <a name="array-element-expressions"></a>Wyrażenia elementu tablicy

Jeśli wyrażenie tablicowe i `Int` wyrażenie, nowe wyrażenie może być utworzone przy użyciu operatora elementu `[` Array `]` i.
Nowe wyrażenie będzie tego samego typu co typ elementu tablicy.
Na przykład, jeśli `a` jest powiązany z tablicą `Double`s, a następnie `a[4]` jest `Double` wyrażeniem.

Jeśli wyrażenie tablicy nie jest prostym identyfikatorem, musi być ujęte w nawiasy klamrowe, aby można było wybrać element.
Na przykład, jeśli `a` i `b` są obie tablice `Int`s, element z łączenia zostałby wyrażony jako:

```qsharp
(a+b)[13]
```

Wszystkie tablice w Q # są oparte na zero.
Oznacza to, że pierwszy element tablicy `a` jest zawsze. `a[0]`


## <a name="copy-and-update-expressions"></a>Wyrażenia kopiowania i aktualizowania

Nowe tablice można tworzyć z istniejących za pośrednictwem wyrażeń kopiowania i aktualizowania.
Wyrażenie copy `expression1 w/ expression2 <- expression3`-and-Update jest wyrażeniem formularza, gdzie `expression1` musi być typu `T[]` dla pewnego typu. `T` Sekunda `expression2` definiuje indeksy elementów do zmodyfikowania w porównaniu do tablicy w `expression1` i musi być typu `Int` lub typu. `Range` Jeśli `expression2` jest typu `Int`, `expression3` musi być typu. `T` Jeśli `expression2` jest typu `Range`, `expression3` musi być typu. `T[]`

Wyrażenie `arr w/ idx <- value` Copy-and-Update konstruuje nową tablicę ze wszystkimi elementami ustawionymi na odpowiadający element `arr`w, z wyjątkiem elementów `idx`, które są ustawione na jeden z nich w. `value` Na przykład, jeśli `arr` zawiera tablicę `[0,1,2,3]`, 
- `arr w/ 0 <- 10`jest tablicą `[10,1,2,3]`.
- `arr w/ 2 <- 10`jest tablicą `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]`jest tablicą `[10,1,12,3]`.

Podobne wyrażenia istnieją dla nazwanych elementów w typach zdefiniowanych przez użytkownika. Rozważmy przykład typu 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Jeśli `c` `Complex(1.,-1.)`zawiera wartość typu `c w/ Re <- 0.` , jest wyrażeniem typu `Complex` , który jest obliczany. `Complex(0.,-1.)`

## <a name="conditional-expressions"></a>Wyrażenia warunkowe

Uwzględniając dwa inne wyrażenia tego samego typu i wyrażenie logiczne, wyrażenie warunkowe może być utworzone przy użyciu znaku `?` zapytania i pionowego paska. `|`
Na przykład `a==b ? c | d`.
W tym przykładzie wartość wyrażenia warunkowego będzie `c` `a==b` równa true, a `d` jeśli jest fałszywa.

Dwa wyrażenia mogą oszacować do operacji, które mają te same dane wejściowe i wyjściowe, ale obsługują różne funktory.
W tym przypadku typ wyrażenia warunkowego jest operacją z tymi danymi wejściowymi i wyjściowymi, które obsługują wszystkie funktory obsługiwane przez oba wyrażenia.
Na przykład jeśli `Op1` `Op2`,, i `Op3` wszystkie są `Qubit[]=>Unit`, ale `Op1` obsługuje `Adjoint`, `Op2` obsługuje `Controlled`i `Op3` obsługuje obie:

- `flag ? Op1 | Op2`jest `(Qubit[] => Unit)` operacją.
- `flag ? Op1 | Op3`jest `(Qubit[] => Unit is Adj)` operacją.
- `flag ? Op2 | Op3`jest `(Qubit[] => Unit is Ctl)` operacją.

Jeśli jedno z dwóch możliwych wyrażeń wynikowych zawiera wywołanie funkcji lub operacji, to wywołanie będzie odbywać się tylko wtedy, gdy ten wynik będzie wartością wywołania.
Na przykład `a==b ? C(qs) | D(qs)`w przypadku, gdy `a==b` ma wartość true, `C` operacja zostanie wywołana, a jeśli ma wartość false, tylko `D` zostanie wywołana.
Jest to podobne do krótkich obwodów w innych językach.


## <a name="operator-precedence"></a>Kolejność wykonywania działań

Wszystkie operatory binarne są z prawej strony skojarzenia, z wyjątkiem `^`.

Nawiasy `[` klamrowe i `]`, w przypadku dzielenia i indeksowania tablicy, należy powiązać przed dowolnym operatorem.

Funktory `Adjoint` i `Controlled` Powiąż po indeksowaniu tablicy, ale przed wszystkimi innymi operatorami.

Nawiasy dla wywołania operacji i funkcji są również powiązane przed dowolnym operatorem, ale po indeksowaniu tablicy i funktory.

Operatory według pierwszeństwa, od najwyższego do najniższego:

Operator | Większa | Opis | Typy operandów
---------|----------|---------|---------------
 końcowe`!` | Jednoargumentowy | Unwrap | Dowolny typ zdefiniowany przez użytkownika
 `-`, `~~~`, `not` | Jednoargumentowy | Cyfra ujemna, dopełnienie bitowe, Negacja logiczna | `Int`, `BigInt` lub `Double` dla `-`, `Int` `BigInt` dla `~~~` `Bool``not`
 `^` | plików binarnych | Moc całkowita | `Int`lub `BigInt` dla podstawy `Int` dla wykładnika
 `/`, `*`, `%` | plików binarnych | Dzielenie, mnożenie, moduł całkowity | `Int`, `BigInt` lub `Double` dla `/` i `*`, `Int` lub `BigInt` dla`%`
 `+`, `-` | plików binarnych | Dodawanie lub łączenie ciągów i tablic, odejmowanie | `Int`, `BigInt` or `Double`, dodatkowo `String` lub dowolnego typu tablicy dla`+`
 `<<<`, `>>>` | plików binarnych | Lewy Shift, prawy Shift | `Int` lub `BigInt`
 `<`, `<=`, `>`, `>=` | plików binarnych | Mniejsze niż, mniejsze niż lub równe, większe niż, większe niż lub równe | `Int``BigInt` lub`Double`
 `==`, `!=` | plików binarnych | porównania równe, nierówne | dowolny typ pierwotny
 `&&&` | plików binarnych | Bitowe ORAZ | `Int` lub `BigInt`
 `^^^` | plików binarnych | Bitowe XOR | `Int` lub `BigInt`
 <code>\|\|\|</code> | plików binarnych | Bitowe OR | `Int` lub `BigInt`
 `and` | plików binarnych | AND logiczne | `Bool`
 `or` | plików binarnych | OR logiczne | `Bool`
 `..` | Plik binarny/Trzyelementowy | Operator zakresu | `Int`
 `?` `|` | Trójargumentowy | Warunkowe | `Bool`po lewej stronie
`w/` `<-` | Trójargumentowy | Kopiuj i Aktualizuj | Zobacz [wyrażenia kopiowania i aktualizowania](#copy-and-update-expressions)

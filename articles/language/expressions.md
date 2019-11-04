---
title: Wyrażenia | Microsoft Docs
description: Wyrażenia
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 09d493df4e1178fee1f7a5946cfda2f411111006
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185209"
---
# <a name="expressions"></a>Wyrażenia

## <a name="grouping"></a>Grupie

Uwzględniając dowolne wyrażenie, to samo wyrażenie ujęte w nawiasy jest wyrażeniem tego samego typu.
Na przykład `(7)` jest wyrażeniem `Int`, `([1,2,3])` jest wyrażeniem typu Array `Int`s, a `((1,2))` jest wyrażeniem z typem `(Int, Int)`.

Równoważność między wartościami prostymi a krotkami jednoelementowymi opisanymi w [modelu typu](xref:microsoft.quantum.language.type-model#tuple-types) usuwa niejednoznaczność między `(6)` jako grupę i `(6)` jako spójną krotkę.

## <a name="symbols"></a>Symbole

Nazwa symbolu powiązanego lub przypisana do wartości typu `'T` jest wyrażeniem typu `'T`.
Na przykład jeśli symbol `count` jest powiązany z wartością całkowitą `5`, wówczas `count` jest wyrażeniem liczb całkowitych.

## <a name="numeric-expressions"></a>Wyrażenia liczbowe

Wyrażenia liczbowe są wyrażeniami typu `Int`, `BigInt`lub `Double`.
Oznacza to, że są to liczby całkowite lub zmiennoprzecinkowe.

literały `Int` w Q # są identyczne z literałami całkowitymi C#w, z tą różnicą, że nie są wymagane żadne końcowe litery "l" lub "l" (lub dozwolone).
Liczby całkowite szesnastkowe i binarne są obsługiwane odpowiednio prefiksem "0x" i "0b".

literały `BigInt` w Q # są identyczne z ciągami Big Integer w programie .NET, z końcowym "l" lub "L".
Szesnastkowe duże liczby całkowite są obsługiwane z prefiksem "0x".
W ten sposób wszystkie prawidłowe zastosowania literałów `BigInt` są następujące:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

literały `Double` w Q # są takie same jak literały podwójne C#w, z tą różnicą, że nie jest wymagane końcowe "d" lub "d" (lub dozwolone).

Uwzględniając wyrażenie tablicy dowolnego typu elementu, wyrażenie `Int` może być utworzone przy użyciu wbudowanej funkcji `Length`, z wyrażeniem tablicy ujętym w nawiasy, `(` i `)`.
Na przykład jeśli `a` jest powiązany z tablicą, wówczas `Length(a)` jest wyrażeniem liczb całkowitych.
Jeśli `b` jest tablicą tablic liczb całkowitych, `Int[][]`, wówczas `Length(b)` jest liczbą tablic podrzędnych w `b`, a `Length(b[1])` to liczba liczb całkowitych w drugiej podtabeli w `b`.

Uwzględniając dwa wyrażenia liczbowe tego samego typu, operatory binarne `+`, `-`, `*`i `/` mogą służyć do tworzenia nowego wyrażenia liczbowego.
Typ nowego wyrażenia będzie taki sam jak typy wyrażeń składowych.

W przypadku dwóch wyrażeń całkowitych `^` operatora binarnego (potęgi) można użyć do utworzenia nowego wyrażenia liczb całkowitych.
Podobnie `^` mogą być używane z dwoma wyrażeniami podwójnymi, aby utworzyć nowe wyrażenie podwójne.
Na koniec `^` mogą być używane z dużą liczbą całkowitą z lewej strony i liczbą całkowitą z prawej strony, aby utworzyć nowe wyrażenie Big Integer.
W takim przypadku drugi parametr musi pasować do 32 bitów; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.

W przypadku dwóch wyrażeń całkowitych lub dużych liczb całkowitych można utworzyć nowe wyrażenie typu Integer lub Big Integer przy użyciu operatorów `%` (moduł), `&&&` (bitowe AND), `|||` (bitowe OR) lub `^^^` (bitowe XOR).

W przypadku wyrażenia typu Integer lub Big Integer po lewej stronie i wyrażenia liczb całkowitych po prawej stronie operatory `<<<` (arytmetyczne przesunięcie w lewo) lub `>>>` (arytmetyczne przesunięcie w prawo) mogą być używane do tworzenia nowego wyrażenia z tym samym typem co lewa wyrażenia.

Drugi parametr (wartość przesunięcia) dla operacji Shift musi być większy lub równy zero; zachowanie dla ujemnych kwot przesunięcia jest niezdefiniowane.
Wartość przesunięcia dla operacji przesunięcia musi być również zgodna z 32 bitowymi; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.
Jeśli liczba, która ma zostać przesunięta jest liczbą całkowitą, wartość przesunięcia jest interpretowana `mod 64`; oznacza to, że przesunięcie 1 i przesunięcie 65 mają ten sam efekt.

W przypadku wartości liczb całkowitych i dużych liczb całkowitych przesunięcia są arytmetyczne.
Przesunięcie wartości ujemnej w lewo lub w prawo spowoduje powstanie liczby ujemnej.
Oznacza to, że przesunięcie jeden krok w lewo lub w prawo jest dokładnie takie samo jak mnożenie lub dzielenie odpowiednio przez 2.

Dzielenie liczb całkowitych i moduł całkowity są zgodne z tym samym zachowaniem dla liczb ujemnych jako C#.
Oznacza to, że `a % b` będzie zawsze mieć ten sam znak co `a`, a `b * (a / b) + a % b` zawsze będą równe `a`.
Na przykład:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Dzielenie z dużymi liczbami całkowitymi i moduł działa w taki sam sposób.

Mając każde wyrażenie liczbowe, nowe wyrażenie może być utworzone za pomocą operatora jednoargumentowego `-`.
Nowe wyrażenie będzie tego samego typu co wyrażenie elementu.

W przypadku dowolnego wyrażenia typu Integer lub Big Integer nowe wyrażenie tego samego typu może być sformułowane przy użyciu operatora jednoargumentowego `~~~` (dopełnienie bitowe).

## <a name="boolean-expressions"></a>Wyrażenia logiczne

Dwie `Bool` wartości literału są `true` i `false`.

Uwzględniając wszystkie dwa wyrażenia tego samego typu pierwotnego, operatory `==` i `!=` mogą służyć do konstruowania wyrażenia `Bool`.
Wyrażenie będzie prawdziwe, jeśli dwa wyrażenia są równe.

Wartości typów zdefiniowanych przez użytkownika mogą nie być porównywane. można porównać tylko ich wartości. Na przykład:

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Porównywanie równości dla wartości `Qubit` jest równość tożsamości; oznacza to, czy dwa wyrażenia identyfikują ten sam qubit.
Stan dwóch qubits nie jest porównywany, dostępny, mierzony ani modyfikowany przez to porównanie.

Porównanie równości dla wartości `Double` może być mylące ze względu na efekt zaokrąglenia.
Na przykład `49.0 * (1.0/49.0) != 1.0`.

Uwzględniając wszystkie dwa wyrażenia liczbowe, operatory binarne `>`, `<`, `>=`i `<=` mogą służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli pierwsze wyrażenie jest odpowiednio większe niż, mniejsze niż lub równe lub mniejsze lub równe drugiemu wyrażeniu.

Uwzględniając dowolne dwa wyrażenia logiczne, `and` i `or` operatory binarne mogą służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli oba wyrażenia (centr. or lub oba) są prawdziwe.

Podano dowolne wyrażenie logiczne `not` operator jednoargumentowy może służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli wyrażenie elementu składowego ma wartość false.

## <a name="string-expressions"></a>Wyrażenia ciągów

Funkcja Q # umożliwia używanie ciągów w instrukcji `fail` i funkcji standardowej `Log`.

Ciągi w Q # są literałami lub interpolowanymi ciągami.
Literały ciągu są podobne do prostych literałów ciągu w większości języków: sekwencji znaków Unicode ujętych w podwójne cudzysłowy `"`.
Wewnątrz ciągu, znak ukośnika odwrotnego `\` może być używany do ucieczki podwójnego znaku cudzysłowu i do wstawiania nowej linii jako `\n`, powrotu karetki jako `\r`i karty jako `\t`.
Na wystąpienie:

```qsharp
"\"Hello world!\", she said.\n"
```

Składnia Q # dla interpolacji ciągów jest podzbiorem składni C# 7,0; Usługa Q # nie obsługuje ciągów interpolowanych Verbatim (wiele wierszy).
Zobacz [*interpolowane ciągi*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) C# składni.

Wyrażenia wewnątrz ciągu interpolowanego są zgodne z składnią Q #, C# a nie składnią.
Dowolne prawidłowe wyrażenie Q # może pojawić się w ciągu interpolowanym.

## <a name="qubit-expressions"></a>Wyrażenia qubit

Jedyne wyrażenia `Qubit` są symbolami, które są powiązane z wartościami `Qubit` lub elementami tablicy tablic `Qubit`.
Brak literałów `Qubit`.

## <a name="pauli-expressions"></a>Wyrażenia Pauli

Cztery `Pauli` wartości, `PauliI`, `PauliX`, `PauliY`i `PauliZ`są prawidłowymi wyrażeniami `Pauli`.

Inne niż to, jedyne wyrażenia `Pauli` są symbolami, które są powiązane z wartościami `Pauli` lub elementami tablicy tablic `Pauli`.

## <a name="result-expressions"></a>Wyrażenia wynikowe

Dwie `Result` wartości `One` i `Zero`są prawidłowymi wyrażeniami `Result`.

Inne niż to, jedyne wyrażenia `Result` są symbolami, które są powiązane z wartościami `Result` lub elementami tablicy tablic `Result`.
W szczególności należy zauważyć, że `One` nie jest taka sama jak liczba całkowita `1`i nie ma żadnej bezpośredniej konwersji między nimi.
Ta sama wartość dotyczy `Zero` i `0`.

## <a name="range-expressions"></a>Wyrażenia zakresu

Uwzględniając wszystkie trzy `Int` wyrażeń `start`, `step`i `stop`, `start .. step .. stop` jest wyrażeniem zakresu, którego pierwszy element jest `start`, drugi element jest `start+step`, trzeci element jest `start+step+step`itd., dopóki nie zostanie przeniesiona `stop`.
Zakres może być pusty, jeśli na przykład `step` jest dodatni i `stop < start`.
Ostatni element zakresu będzie `stop`, jeśli różnica między `start` i `stop` jest integralną wielokrotnością `step`; oznacza to, że zakres jest włącznie na obu końcach.

Uwzględniając wszystkie dwa `Int` wyrażeń `start` i `stop``start .. stop` jest wyrażeniem zakresu, które jest równe `start .. 1 .. stop`.
Należy zauważyć, że implikowane `step` jest + 1 nawet wtedy, gdy `stop` jest mniejsze niż `start`; w takim przypadku zakres jest pusty.

Oto kilka przykładowych zakresów:

- `1..3` jest zakresem 1, 2, 3.
- `2..2..5` jest zakresem od 2 do 4.
- `2..2..6` jest zakresem 2, 4, 6.
- `6..-2..2` jest zakresem 6, 4, 2.
- `2..1` jest pustym zakresem.
- `2..6..7` jest zakresem 2.
- `2..2..1` jest pustym zakresem.
- `1..-1..2` jest pustym zakresem.

## <a name="callable-expressions"></a>Możliwe do przewyrażenia

Możliwy do przeprowadzenia literał jest nazwą operacji lub funkcji zdefiniowanej w zakresie kompilacji.
Na przykład `X` to literał operacji odwołujący się do standardowej operacji `X` biblioteki, a `Message` jest literalną funkcją, która odwołuje się do funkcji `Message` biblioteki standardowej.

Jeśli operacja obsługuje `Adjoint` Funktor, wówczas `Adjoint op` jest wyrażeniem operacji.
Podobnie, jeśli operacja obsługuje `Controlled` Funktor, wówczas `Controlled op` jest wyrażeniem operacji.
Typy tych wyrażeń są określone w [funktory](xref:microsoft.quantum.language.type-model#functors).

Funktory (`Adjoint` i `Controlled`) są bardziej ściśle powiązane niż wszystkie inne operatory, z wyjątkiem `!` operatora rozwinięcia i indeksowania tablicy z `[]`.
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

Na przykład jeśli `Fun` jest funkcją z sygnaturą `'T1->Unit`:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Wywoływanie wyrażeń wywołania

Dane wyrażenie możliwego do wywołania (operacji lub funkcji) i wyrażenie spójnej kolekcji typu wejściowego w podpisie, wyrażenie wywoływania może być sformułowane przez dołączenie wyrażenia krotki do możliwego do wywołania wyrażenia.
Typ wyrażenia wywołania jest typem wyjściowym podpisu, który ma zostać wywołany.

Na przykład jeśli `Op` jest operacją z sygnaturą `((Int, Qubit) => Double)`, `Op(3, qubit1)` jest wyrażeniem typu `Double`.
Podobnie, jeśli `Sin` jest funkcją z sygnaturą `(Double -> Double)`, `Sin(0.1)` jest wyrażeniem typu `Double`.
Na koniec Jeśli `Builder` jest funkcją z sygnaturą `(Int -> (Int -> Int))`, `Builder(3)` jest funkcją z do int.

Wywołanie wyniku wyrażenia z wartościami możliwymi do wywołania wymaga dodatkowej pary nawiasów wokół wartościowego wyrażenia.
W związku z tym, aby wywołać wynik wywołania `Builder` z poprzedniego akapitu, poprawna składnia to:

```qsharp
(Builder(3))(2)
```

W przypadku wywołania sparametryzowanego typu, można określić rzeczywiste parametry typu w nawiasach kątowych `<` i `>` po wyrażeniu możliwym do wywołania.
Zwykle nie jest to konieczne, ponieważ kompilator Q # wykryje rzeczywiste typy.
Jest to wymagane w przypadku częściowej aplikacji (patrz poniżej), jeśli argument z parametrem sparametryzowanym nie został określony.
Jest to również czasami przydatne, gdy przekazywanie operacji z różnymi Funktor obsługuje do możliwego do odwoływać.

Na przykład jeśli `Func` ma sygnaturę `('T1, 'T2, 'T1) -> 'T2`, `Op1` i `Op2` mają sygnaturę `(Qubit[] => Unit is Adj)`, a `Op3` ma sygnaturę `(Qubit[] => Unit)`, aby wywoływać `Func` z `Op1` jako pierwszy argument, `Op2` jako drugi i `Op3` jako trzeci:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Specyfikacja typu jest wymagana, ponieważ `Op3` i `Op1` mają różne typy, więc kompilator traktuje to jako niejednoznaczne bez specyfikacji.

### <a name="partial-application"></a>Aplikacja częściowa

Po otrzymaniu możliwego do przetworzenia wyrażenia można utworzyć nowe wywoływanie, dostarczając podzestaw argumentów do obiektu.
Jest to nazywane _częściową aplikacją_.

W Q #, częściowo zastosowane wywołanie jest wyrażane przez zapisanie wyrażenia zwykłego wywołania, ale przy użyciu podkreślenia, `_`, dla nieokreślonych argumentów.
Wynikowe wywoływanie ma ten sam typ wyniku co podstawowy możliwy do przetworzenie i te same specjalizacje dla operacji.
Typ danych wejściowych częściowej aplikacji jest po prostu oryginalnym typem z określonymi argumentami.

Jeśli zmienna modyfikowalna jest przenoszona jako określony argument podczas tworzenia częściowej aplikacji, używana jest bieżąca wartość zmiennej.
Późniejsze zmiany wartości zmiennej nie wpłyną na częściową aplikację.

Na przykład jeśli `Op` ma typ `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))` jest typu `(((Qubit,Qubit), Double) => Unit is Adj)`i dlatego ma `Op(5,_)`.
- `Op(_,(_,1.0))` ma `((Int, (Qubit,Qubit)) => Unit is Adj)`typu.
- `Op(_,((q1,q2),_))` ma `((Int,Double) => Unit is Adj)`typu.
   Należy zauważyć, że w tym miejscu zastosowano jednokrotną równoważność krotki.

Jeśli częściowo zastosowane wywołanie ma parametry typu, których nie można wywnioskować przez kompilator, muszą one być dostarczone w lokacji wywołania.
Częściowa aplikacja nie może mieć żadnych nieokreślonych parametrów typu.

Na przykład jeśli `Op` ma typ `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

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

Literał krotki jest sekwencją wyrażenia elementu odpowiedniego typu, rozdzielonych przecinkami, ujęty w `(` i `)`.
Na przykład `(1, One)` jest wyrażeniem `(Int, Result)`.

W przypadku innych niż literały jedynymi wyrażeniami krotek są symbole, które są powiązane z wartościami krotki, elementami tablicy tablic krotek i wywoływanie wywołań, które zwracają krotki.

## <a name="user-defined-type-expressions"></a>Wyrażenia typu zdefiniowanego przez użytkownika

Literał typu zdefiniowanego przez użytkownika składa się z nazwy typu, a następnie literału krotki typu krotki podstawowej typu.
Na przykład jeśli `IntPair` jest typem zdefiniowanym przez użytkownika na podstawie `(Int, Int)`, wówczas `IntPair(2,3)` byłby prawidłowym literałem tego typu.

Oprócz literałów jedynymi wyrażeniami typu zdefiniowanego przez użytkownika są symbole, które są powiązane z wartościami tego typu, elementy tablicy tablic tego typu i wywoływanie wywołań, które zwracają ten typ.

## <a name="unwrap-expressions"></a>Odpakowywanie wyrażeń

W Q # operator rozwinięcia jest końcowym znakiem wykrzyknika `!`.
Na przykład jeśli `IntPair` jest typem zdefiniowanym przez użytkownika o typie podstawowym `(Int, Int)`, a `s` była zmienną z wartością `IntPair(2,3)`, `s!` byłoby `(2,3)`.

Dla typów zdefiniowanych przez użytkownika, zdefiniowanych w warunkach innych typów zdefiniowanych przez użytkownika. operatora rozwinięcia można powtórzyć; na przykład `s!!` wskazuje podwójnie nieopakowaną wartość `s`.
W takim przypadku, jeśli `WrappedPair` jest typem zdefiniowanym przez użytkownika o typie podstawowym `IntPair`, a `t` jest zmienną z wartością `WrappedPair(IntPair(1,2))`, `t!!` będzie `(1,2)`.

Operator `!` ma wyższy priorytet niż wszystkie inne operatory inne niż `[]` do indeksowania tablicy i dzielenia.
`!` i `[]` powiązać pozycjonowanie; oznacza to, że `a[i]![3]` powinna zostać odczytana jako `((a[i])!)[3]`: Weź element `i`"z `a`, Odpakuj go, a następnie Pobierz trzeci element nieopakowanej wartości (która musi być tablicą).

Pierwszeństwo operatora `!` ma jeden wpływ, który może nie być oczywisty.
Jeśli funkcja lub operacja zwraca wartość, która staje się nieopakowana, wywołanie funkcji lub operacji musi być ujęte w nawiasy, tak aby krotka argumentu była powiązana z wywołaniem, a nie z odwinięciem.
Na przykład:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Wyrażenia tablic

Literał tablicowy jest sekwencją co najmniej jednego wyrażenia elementu, oddzielone przecinkami, ujęte w `[` i `]`.
Wszystkie elementy muszą być zgodne z tym samym typem.

Jeśli wspólny typ elementu jest operacją lub typem funkcji, wszystkie elementy muszą mieć te same typy danych wejściowych i wyjściowych.
Typ elementu tablicy będzie obsługiwał wszystkie funktory, które są obsługiwane przez wszystkie elementy.
Na przykład jeśli `Op1`, `Op2`i `Op3` wszystkie są `Qubit[] => Unit`, ale `Op1` obsługuje `Adjoint`, `Op2` obsługuje `Controlled`, a `Op3` obsługuje oba:

- `[Op1, Op2]` jest tablicą operacji `(Qubit[] => Unit)`.
- `[Op1, Op3]` jest tablicą operacji `(Qubit[] => Unit is Adj)`.
- `[Op2, Op3]` jest tablicą operacji `(Qubit[] => Unit is Ctl)`.

Puste literały tablicowe, `[]`, są niedozwolone.
Zamiast tego przy użyciu `new ★[0]`, gdzie `★` jest symbolem zastępczym dla odpowiedniego typu, umożliwia utworzenie odpowiedniej tablicy o długości zero.

Mając daną dwie tablice tego samego typu, operator `+` binarnych może służyć do tworzenia nowej tablicy, która jest połączeniem dwóch tablic.
Na przykład `[1,2,3] + [4,5,6]` jest `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Tworzenie tablicy

Uwzględniając typ i wyrażenie `Int`, operatora `new` można użyć do przydzielenia nowej tablicy o danym rozmiarze.
Na przykład `new Int[i+1]` przydzieli nową tablicę `Int` z elementami `i+1`.

Elementy nowej tablicy są inicjowane z wartością domyślną zależną od typu.
W większości przypadków jest to pewna odmiana zero.

W przypadku qubits i elementów, które są odwołaniami do jednostek, nie ma żadnej rozsądnej wartości domyślnej.
W tym przypadku dla tych typów wartość domyślna to nieprawidłowe odwołanie, którego nie można użyć bez powodowania błędu czasu wykonywania.
Jest to podobne do odwołania o wartości null w językach takich C# jak lub Java.
Tablice zawierające qubits lub elementy wywoływane muszą zostać prawidłowo zainicjowane przy użyciu wartości innych niż domyślne, zanim ich elementy mogą być bezpiecznie używane. Odpowiednie procedury inicjowania można znaleźć w <xref:microsoft.quantum.arrays>.

Wartości domyślne dla każdego typu są następujące:

Typ | Domyślne
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _Nieprawidłowy qubit_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | Pusty zakres, `1..1..0`
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

Korzystając z wyrażenia tablicy i wyrażenia `Range`, nowe wyrażenie może być utworzone przy użyciu operatora wycinka tablicy `[` i `]`.
Nowe wyrażenie będzie tego samego typu co tablica i będzie zawierać elementy tablicy indeksowane przez elementy `Range`w kolejności zdefiniowanej przez `Range`.
Na przykład jeśli `a` jest powiązany z tablicą `Double`s, `a[3..-1..0]` jest wyrażeniem `Double[]`, które zawiera pierwsze cztery elementy `a`, ale w kolejności odwrotnej, jak pojawiają się w `a`.

Jeśli `Range` jest puste, powstający wycink tablicy będzie zerem o zerowej długości.

Jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, musi być ujęte w nawiasy klamrowe w celu wycięcia.
Na przykład jeśli `a` i `b` są tablicami `Int`s, wycinek z złączki zostanie wyrażony jako:

```qsharp
(a+b)[1..2..7]
```

Wszystkie tablice w Q # są oparte na zero.
Oznacza to, że pierwszy element tablicy `a` zawsze jest `a[0]`.

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

Korzystając z wyrażenia tablicy i wyrażenia `Int`, nowe wyrażenie może być utworzone za pomocą operatora `[` i `]` elementu tablicy.
Nowe wyrażenie będzie tego samego typu co typ elementu tablicy.
Na przykład jeśli `a` jest powiązany z tablicą `Double`s, `a[4]` jest wyrażeniem `Double`.

Jeśli wyrażenie tablicy nie jest prostym identyfikatorem, musi być ujęte w nawiasy klamrowe, aby można było wybrać element.
Na przykład jeśli `a` i `b` są tablicami `Int`s, element z łączenia byłby wyrażony jako:

```qsharp
(a+b)[13]
```

Wszystkie tablice w Q # są oparte na zero.
Oznacza to, że pierwszy element tablicy `a` zawsze jest `a[0]`.


## <a name="copy-and-update-expressions"></a>Wyrażenia kopiowania i aktualizowania

Nowe tablice można tworzyć z istniejących za pośrednictwem wyrażeń kopiowania i aktualizowania.
Wyrażenie Copy-and-Update jest wyrażeniem `expression1 w/ expression2 <- expression3`, gdzie `expression1` musi być typu `T[]` dla niektórych typów `T`. Druga `expression2` definiuje indeksy elementów do zmodyfikowania w porównaniu do tablicy w `expression1` i musi być albo typu `Int` lub typu `Range`. Jeśli `expression2` jest typu `Int`, `expression3` musi być typu `T`. Jeśli `expression2` jest typu `Range`, `expression3` musi być typu `T[]`.

Wyrażenie Copy-and-Update `arr w/ idx <- value` konstruuje nową tablicę ze wszystkimi elementami ustawionymi na odpowiadający element w `arr`, z wyjątkiem elementów w `idx`, które są ustawione na jedną z nich w `value`. Na przykład jeśli `arr` zawiera tablicę `[0,1,2,3]`, to 
- `arr w/ 0 <- 10` jest `[10,1,2,3]`tablicy.
- `arr w/ 2 <- 10` jest `[0,1,10,3]`tablicy.
- `arr w/ 0..2..3 <- [10,12]` jest `[10,1,12,3]`tablicy.

Podobne wyrażenia istnieją dla nazwanych elementów w typach zdefiniowanych przez użytkownika. Rozważmy przykład typu 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Jeśli `c` zawiera wartość typu `Complex(1.,-1.)`, `c w/ Re <- 0.` jest wyrażeniem typu `Complex`, które oblicza `Complex(0.,-1.)`.

## <a name="conditional-expressions"></a>Wyrażenia warunkowe

W przypadku dwóch innych wyrażeń tego samego typu i wyrażenia logicznego wyrażenie warunkowe może być utworzone przy użyciu znaku zapytania `?` a pionowy pasek `|`.
Na przykład `a==b ? c | d`.
W tym przykładzie wartość wyrażenia warunkowego zostanie `c`, jeśli `a==b` ma wartość true, a `d`, jeśli ma wartość false.

Dwa wyrażenia mogą oszacować do operacji, które mają te same dane wejściowe i wyjściowe, ale obsługują różne funktory.
W tym przypadku typ wyrażenia warunkowego jest operacją z tymi danymi wejściowymi i wyjściowymi, które obsługują wszystkie funktory obsługiwane przez oba wyrażenia.
Na przykład jeśli `Op1`, `Op2`i `Op3` wszystkie są `Qubit[]=>Unit`, ale `Op1` obsługuje `Adjoint`, `Op2` obsługuje `Controlled`, a `Op3` obsługuje oba:

- `flag ? Op1 | Op2` jest operacją `(Qubit[] => Unit)`.
- `flag ? Op1 | Op3` jest operacją `(Qubit[] => Unit is Adj)`.
- `flag ? Op2 | Op3` jest operacją `(Qubit[] => Unit is Ctl)`.

Jeśli jedno z dwóch możliwych wyrażeń wynikowych zawiera wywołanie funkcji lub operacji, to wywołanie będzie odbywać się tylko wtedy, gdy ten wynik będzie wartością wywołania.
Na przykład w przypadku `a==b ? C(qs) | D(qs)`, jeśli `a==b` ma wartość true, operacja `C` zostanie wywołana, a jeśli ma wartość false, tylko `D` zostanie wywołana.
Jest to podobne do krótkich obwodów w innych językach.


## <a name="operator-precedence"></a>Pierwszeństwo operatorów

Wszystkie operatory binarne są z prawej strony skojarzenia, z wyjątkiem `^`.

Nawiasy klamrowe, `[` i `]`, na potrzeby dzielenia i indeksowania tablic.

Funktory `Adjoint` i `Controlled` powiązać po indeksowaniu tablicy, ale przed wszystkimi innymi operatorami.

Nawiasy dla wywołania operacji i funkcji są również powiązane przed dowolnym operatorem, ale po indeksowaniu tablicy i funktory.

Operatory według pierwszeństwa, od najwyższego do najniższego:

Operator | Większa | Opis | Typy operandów
---------|----------|---------|---------------
 `!` końcowy | Jednostk | Unwrap | Dowolny typ zdefiniowany przez użytkownika
 `-`, `~~~`, `not` | Jednostk | Cyfra ujemna, dopełnienie bitowe, Negacja logiczna | `Int`, `BigInt` lub `Double` dla `-`, `Int` lub `BigInt` w `~~~``Bool` `not`
 `^` | Binarny | Moc całkowita | `Int` lub `BigInt` dla podstawy, `Int` dla wykładnika
 `/`, `*`, `%` | Binarny | Dzielenie, mnożenie, moduł całkowity | `Int`, `BigInt` lub `Double` dla `/` i `*`, `Int` lub `BigInt` dla `%`
 `+`, `-` | Binarny | Dodawanie lub łączenie ciągów i tablic, odejmowanie | `Int`, `BigInt` lub `Double`, dodatkowo `String` lub dowolnego typu tablicy dla `+`
 `<<<`, `>>>` | Binarny | Lewy Shift, prawy Shift | `Int` lub `BigInt`
 `<`, `<=`, `>``>=` | Binarny | Mniejsze niż, mniejsze niż lub równe, większe niż, większe niż lub równe | `Int`, `BigInt` lub `Double`
 `==`, `!=` | Binarny | porównania równe, nierówne | dowolny typ pierwotny
 `&&&` | Binarny | Bitowe i | `Int` lub `BigInt`
 `^^^` | Binarny | Bitowe XOR | `Int` lub `BigInt`
 <code>\|\|\|</code> | Binarny | Bitowe lub | `Int` lub `BigInt`
 `and` | Binarny | Koniunkcja logiczna i | `Bool`
 `or` | Binarny | Logiczne lub | `Bool`
 `..` | Plik binarny/Trzyelementowy | Operator zakresu | `Int`
 `?` `|` | Trójargumentowy | Warunkowe | `Bool` po lewej stronie
`w/` `<-` | Trójargumentowy | Kopiuj i Aktualizuj | Zobacz [wyrażenia kopiowania i aktualizowania](#copy-and-update-expressions)

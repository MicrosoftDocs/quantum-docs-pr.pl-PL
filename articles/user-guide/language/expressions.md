---
title: Wyrażenia w Q#
description: Dowiedz się, jak określać, odwoływać i łączyć stałe, zmienne, operatory, operacje i funkcje jako wyrażenia w Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9bf28e3854eae1892692d7ca840e1860de2e2934
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835846"
---
# <a name="expressions-in-no-locq"></a>Wyrażenia w Q#

## <a name="numeric-expressions"></a>Wyrażenia liczbowe

Wyrażenia liczbowe są wyrażeniami typu `Int` , `BigInt` , lub `Double` .
Oznacza to, że są to liczby całkowite lub zmiennoprzecinkowe.

`Int` literały w Q# są zapisywane jako sekwencja cyfr.
Szesnastkowe i binarne liczby całkowite są obsługiwane i zapisywane odpowiednio przy użyciu `0x` `0b` prefiksu i.

`BigInt` literały w Q# mają końcowy `l` `L` sufiks lub.
Szesnastkowe duże liczby całkowite są obsługiwane i zapisywane z prefiksem "0x".
W ten sposób wszystkie prawidłowe zastosowania `BigInt` literałów są następujące:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` literały w Q# są liczbami zmiennoprzecinkowymi zapisanymi przy użyciu cyfr dziesiętnych.
Mogą być napisywane z lub bez separatora dziesiętnego, `.` lub części wykładniczej wskazanej za pomocą znaku "e" lub "e" (po których dozwolone są tylko możliwe znaki minus i cyfry dziesiętne).
Poniżej podano prawidłowe `Double` literały: `0.0` , `1.2e5` , `1e-5` .

Uwzględniając wyrażenie tablicy dowolnego typu elementu, można utworzyć `Int` wyrażenie przy użyciu [`Length`](xref:microsoft.quantum.core.length) wbudowanej funkcji, z wyrażeniem tablicy ujętym w nawiasy.
Na przykład, jeśli `a` jest powiązany z tablicą, `Length(a)` jest wyrażeniem liczby całkowitej.
Jeśli `b` jest tablicą tablic liczb całkowitych, `Int[][]` , a następnie `Length(b)` jest liczbą tablic w `b` , i `Length(b[1])` jest liczbą liczb całkowitych w drugiej tablicy podrzędnej w `b` .

Uwzględniając dwa wyrażenia liczbowe tego samego typu, operatory binarne,, `+` `-` `*` i `/` mogą być używane do tworzenia nowego wyrażenia liczbowego.
Typ nowego wyrażenia jest taki sam jak typy wyrażeń składowych.

Podane dwa wyrażenia całkowite, użyj operatora binarnego `^` (potęgi), aby utworzyć nowe wyrażenie liczby całkowitej.
Analogicznie, można również użyć `^` z dwoma wyrażeniami podwójnymi, aby utworzyć nowe wyrażenie podwójne.
Na koniec możesz użyć `^` z dużą liczbą całkowitą z lewej strony i liczbą całkowitą z prawej strony, aby utworzyć nowe wyrażenie Big Integer.
W takim przypadku drugi parametr musi pasować do 32 bitów; w przeciwnym razie zgłasza błąd czasu wykonania.

W przypadku dwóch liczb całkowitych lub dużych liczb całkowitych należy utworzyć nowe wyrażenie typu Integer lub Big Integer przy użyciu `%` operatorów (moduł), `&&&` (bitowego i), `|||` (bitowego lub bitowego) `^^^` .

W przypadku wyrażenia typu Integer lub Big Integer po lewej stronie i wyrażenia liczb całkowitych po prawej stronie `<<<` można użyć operatorów (arytmetyczne przesunięcie w lewo) lub `>>>` (arytmetyczne przesunięcie w prawo), aby utworzyć nowe wyrażenie z tym samym typem co lewe wyrażenie.

Drugi parametr (wartość przesunięcia) dla operacji Shift musi być większy lub równy zero; zachowanie dla ujemnych kwot przesunięcia jest niezdefiniowane.
Wartość przesunięcia dla operacji przesunięcia musi być również zgodna z 32 bitowymi; w przeciwnym razie zgłasza błąd czasu wykonania.
Jeśli liczba przesunięta jest liczbą całkowitą, wówczas wartość przesunięcia jest interpretowana, `mod 64` czyli przesunięcie 1 i przesunięcie 65 ma ten sam efekt.

W przypadku wartości liczb całkowitych i dużych liczb całkowitych przesunięcia są arytmetyczne.
Przesunięcie wartości ujemnej w lewo lub w prawo powoduje ujemną liczbę.
Oznacza to, że przesunięcie jednego kroku w lewo lub w prawo jest takie samo jak mnożenie lub dzielenie odpowiednio przez 2.

Dzielenie liczb całkowitych i moduł całkowity są zgodne z tym samym zachowaniem dla liczb ujemnych w języku C#. Oznacza to, że `a % b` zawsze ma ten sam znak jako `a` i `b * (a / b) + a % b` zawsze równa się `a` . Przykład:

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| 5 | 2 | 2 | 1 |
| 5 | -2 | -2 | 1 |
| -5 | 2 | -2 | -1 |
| -5 | -2 | 2 | -1 |

Operacje dzielenia w dużej liczbie całkowitej i modułu działają w ten sam sposób.

Mając każde wyrażenie liczbowe, można utworzyć nowe wyrażenie przy użyciu `-` operatora jednoargumentowego.
Nowe wyrażenie jest tego samego typu co wyrażenie elementu.

Podanym wyrażeniem liczb całkowitych lub Big Integer można utworzyć nowe wyrażenie tego samego typu przy użyciu `~~~` operatora jednoargumentowego (dopełnienie bitowe).

## <a name="boolean-expressions"></a>Wyrażenia logiczne

Dwie `Bool` wartości literału są `true` i `false` .

Uwzględniając wszystkie dwa wyrażenia tego samego typu pierwotnego, `==` Operatory i `!=` mogą być używane do konstruowania `Bool` wyrażenia.
Wyrażenie ma wartość true, jeśli dwa wyrażenia są równe i FAŁSZ, jeśli nie.

Wartości typów zdefiniowanych przez użytkownika mogą nie być porównywane. można porównać tylko ich nieopakowane wartości. Na przykład przy użyciu operatora "unotoka" `!` (szczegółowo wyjaśniono w [typach Q# w ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Porównywanie równości dla `Qubit` wartości jest równość tożsamości; oznacza to, czy dwa wyrażenia identyfikują ten sam qubit.
Nie są one porównywane, dostępne, mierzone ani modyfikowane przez to porównanie.

Porównywanie równości dla `Double` wartości może być mylące ze względu na efekt zaokrąglenia.
Na przykład `49.0 * (1.0/49.0) != 1.0`.

Uwzględniając wszystkie dwa wyrażenia liczbowe, operatory binarne `>` ,, `<` `>=` i `<=` mogą być używane do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli pierwsze wyrażenie jest odpowiednio większe niż, mniejsze niż, większe niż lub równe lub mniejsze lub równe drugiemu wyrażeniu.

Uwzględniając wszystkie dwa wyrażenia logiczne, użyj `and` operatora binarnego, aby utworzyć nowe wyrażenie logiczne, które ma wartość true, jeśli oba te dwa wyrażenia mają wartość true. Podobnie przy użyciu `or` operatora tworzy wyrażenie, które ma wartość true, jeśli jedno z dwóch wyrażeń ma wartość true.

Mając każde wyrażenie logiczne, `not` operator jednoargumentowy może służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli wyrażenie elementu składowego ma wartość false.

## <a name="string-expressions"></a>Wyrażenia ciągu

Q# zezwala na użycie ciągów w `fail` instrukcji (objaśnienie w [przepływie sterowania](xref:microsoft.quantum.guide.controlflow#fail-statement)) i w [`Message`](xref:microsoft.quantum.intrinsic.message) funkcji standardowej. Takie zachowanie jest zależne od używanego symulatora, ale zazwyczaj zapisuje komunikat do konsoli hosta, gdy zostanie wywołana w trakcie działania Q# programu.

Ciągi w Q# są literałami lub interpolowanymi ciągami.

Literały ciągu są podobne do prostych literałów ciągu w większości języków: sekwencji znaków Unicode ujętych w podwójne cudzysłowy `" "` .
Wewnątrz ciągu Użyj znaku ukośnika odwrotnego, `\` Aby wypróbować znak podwójnego cudzysłowu ( `\"` ) lub wstawić nowy wiersz ( `\n` ), powrót karetki ( `\r` ) lub kartę ( `\t` ).
Przykład:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Ciągi interpolowane

Q#Składnia interpolacji ciągów jest podzbiorem składni języka C#. Poniżej przedstawiono kluczowe punkty, w odniesieniu do których odnoszą się Q# :

* Aby zidentyfikować literał ciągu jako ciąg interpolowany, poprzedź go `$` symbolem. Między `$` i `"` , które zaczyna się literałem ciągu znaków, nie może być odstępu.

* Poniżej znajduje się podstawowy przykład, za pomocą którego [`Message`](xref:microsoft.quantum.intrinsic.message) można napisać wynik pomiaru do konsoli wraz z innymi Q# wyrażeniami.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* Dowolne prawidłowe Q# wyrażenie może pojawić się w ciągu interpolowanym.

* Wyrażenia wewnątrz ciągu interpolowanego są zgodne z Q# składnią, a nie składnią języka C#. Najbardziej istotną różnicą jest to, że nie Q# obsługuje ciągów interpolowanych Verbatim (wiele wierszy).

Aby uzyskać więcej informacji na temat składni języka C#, zobacz [*interpolowane ciągi*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).

## <a name="range-expressions"></a>Wyrażenia zakresu

Uwzględniając wszystkie trzy `Int` wyrażenia `start` , `step` i `stop` wyrażenie `start .. step .. stop` jest wyrażeniem zakresu, którego pierwszy element jest `start` , drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do momentu przekazania `stop` .
Zakres może być pusty, jeśli na przykład `step` jest wartością dodatnią i `stop < start` .

Zakres jest włącznie na obu końcach. Oznacza to, że jeśli różnica między `start` i `stop` jest wielokrotnością wielokrotności `step` , ostatni element zakresu będzie `stop` .

Uwzględniając wszystkie dwa `Int` wyrażenia `start` i `stop` wyrażenie `start .. stop` jest wyrażeniem zakresu, które jest równe `start .. 1 .. stop` .
Należy zauważyć, że implikowana `step` wartość to + 1 `stop` , nawet jeśli jest mniejsza niż `start` ; w takim przypadku zakres jest pusty.

Oto kilka przykładowych zakresów:

- `1..3` jest zakresem 1, 2, 3.
- `2..2..5` jest zakresem od 2 do 4.
- `2..2..6` jest zakresem 2, 4, 6.
- `6..-2..2` jest zakresem 6, 4, 2.
- `2..1` jest pustym zakresem.
- `2..6..7` jest zakresem 2.
- `2..2..1` jest pustym zakresem.
- `1..-1..2` jest pustym zakresem.

## <a name="qubit-expressions"></a>Wyrażenia qubit

Jedyne `Qubit` wyrażenia to symbole, które są powiązane z `Qubit` wartościami lub tablicami elementów tablic `Qubit` .
Brak `Qubit` literałów.

## <a name="pauli-expressions"></a>Wyrażenia Pauli

Cztery `Pauli` wartości, `PauliI` ,, `PauliX` `PauliY` i `PauliZ` , są prawidłowymi `Pauli` wyrażeniami.

Inaczej niż to, jedyne `Pauli` wyrażenia to symbole, które są powiązane z `Pauli` wartościami lub tablicami elementów tablic `Pauli` .

## <a name="result-expressions"></a>Wyrażenia wynikowe

Dwie `Result` wartości `One` i `Zero` są prawidłowymi `Result` wyrażeniami.

Inaczej niż to, jedyne `Result` wyrażenia to symbole, które są powiązane z `Result` wartościami lub tablicami elementów tablic `Result` .
W szczególności należy zauważyć, że `One` nie jest taka sama jak liczba całkowita `1` i nie ma żadnej bezpośredniej konwersji między nimi.
Ta sama wartość dotyczy `Zero` i `0` .

## <a name="tuple-expressions"></a>Wyrażenia krotki

Literał krotki to sekwencja wyrażeń elementu odpowiedniego typu, rozdzielona przecinkami, ujęta w nawiasy.
Na przykład `(1, One)` jest `(Int, Result)` wyrażeniem.

W przypadku innych niż literały jedynymi wyrażeniami krotek są symbole, które są powiązane z wartościami krotki, elementami tablicy tablic krotek i wywoływanie wywołań, które zwracają krotki.

## <a name="user-defined-type-expressions"></a>Wyrażenia typu zdefiniowanego przez użytkownika

Literał typu zdefiniowanego przez użytkownika składa się z nazwy typu, a następnie literału krotki typu krotki podstawowej typu.
Na przykład jeśli `IntPair` jest typem zdefiniowanym przez użytkownika `(Int, Int)` , a następnie `IntPair(2, 3)` jest prawidłowym literałem tego typu.

Oprócz literałów jedynymi wyrażeniami typu zdefiniowanego przez użytkownika są symbole, które są powiązane z wartościami tego typu, elementy tablicy tablic tego typu i wywoływanie wywołań, które zwracają ten typ.

## <a name="unwrap-expressions"></a>Odpakowywanie wyrażeń

W programie Q# operator rozwinięcia jest końcowym wykrzyknikiem `!` .
Na przykład jeśli `IntPair` jest typem zdefiniowanym przez użytkownika z typem źródłowym `(Int, Int)` i `s` jest zmienną o wartości `IntPair(2, 3)` , `s!` to `(2, 3)` .

Dla typów zdefiniowanych przez użytkownika, zdefiniowanych w warunkach innych typów zdefiniowanych przez użytkownika, można powtórzyć operator rozwinięcia. Na przykład `s!!` wskazuje podwójnie nieopakowaną wartość `s` .
W takim przypadku, jeśli `WrappedPair` jest typem zdefiniowanym przez użytkownika z typem źródłowym `IntPair` i `t` jest zmienną z wartością `WrappedPair(IntPair(1,2))` , `t!!` to jest `(1,2)` .

`!`Operator ma wyższy priorytet niż wszystkie inne operatory inne niż `[]` dla indeksowania tablicy i dzielenia.
`!` i `[]` Powiąż, to jest `a[i]![3]` odczytywane jako `((a[i])!)[3]` : Zrób `i` ty element `a` , Odpakuj go, a następnie Pobierz trzeci element nieopakowanej wartości (która musi być tablicą).

Pierwszeństwo `!` operatora ma jeden wpływ, który może nie być oczywisty.
Jeśli funkcja lub operacja zwraca wartość, która staje się nieopakowana, wywołanie funkcji lub operacji musi być ujęte w nawiasy, tak aby krotka argumentu była powiązana z wywołaniem, a nie z odwinięciem.
Przykład:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Wyrażenia tablic

Literał tablicowy jest sekwencją co najmniej jednego wyrażenia elementu, oddzielone przecinkami, ujęte w nawiasy kwadratowe `[]` .
Wszystkie elementy muszą być zgodne z tym samym typem.

Mając dwie tablice tego samego typu, użyj operatora Binary, `+` Aby utworzyć nową tablicę, która jest połączeniem dwóch tablic.
Na przykład `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Tworzenie tablicy

Uwzględniając typ i `Int` wyrażenie, użyj `new` operatora, aby przydzielić nową tablicę o danym rozmiarze.
Na przykład `new Int[i + 1]` przypisuje nową `Int` tablicę z `i + 1` elementami.

Puste literały tablicowe, takie jak `[]` , są niedozwolone.
Zamiast tego można utworzyć tablicę o długości zero przy użyciu `new T[0]` , gdzie `T` jest symbolem zastępczym dla odpowiedniego typu.

Elementy nowej tablicy są inicjowane do wartości domyślnej zależnej od typu.
W większości przypadków jest to pewna odmiana zero.

W przypadku qubits i elementów, które są odwołaniami do jednostek, nie ma żadnej rozsądnej wartości domyślnej.
W związku z tym, wartością domyślną jest nieprawidłowe odwołanie, którego nie można użyć bez powodowania błędu czasu wykonywania, podobnie jak w przypadku odwołań o wartości null w językach, takich jak C# lub Java.
Tablice zawierające qubits lub elementy wywoływane muszą zostać zainicjowane przy użyciu wartości innych niż domyślne, aby można było bezpiecznie używać ich elementów. Odpowiednie procedury inicjowania można znaleźć w temacie <xref:microsoft.quantum.arrays> .

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
 `Range` | Pusty zakres, `1..1..0`
 `Callable` | _nieprawidłowe wywoływanie_
 `Array['T]` | `'T[0]`

Typy krotek inicjują element po elemencie.


### <a name="array-elements"></a>Elementy tablicy

Podaną wyrażeniem tablicowym i `Int` wyrażeniem, należy utworzyć nowe wyrażenie przy użyciu operatora elementu tablicy `[]` .
Nowe wyrażenie jest tego samego typu co typ elementu tablicy.
Na przykład jeśli `a` jest powiązany z tablicą typu `Double` , wówczas `a[4]` jest `Double` wyrażeniem.

Jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, należy umieścić je w nawiasach, aby wybrać element.
Na przykład jeśli `a` i `b` są obie tablice typu `Int` , element z łączenia jest wyrażony jako:

```qsharp
(a + b)[13]
```

Wszystkie tablice w Q# są zależne od zera.
Oznacza to, że pierwszy element tablicy `a` jest zawsze `a[0]` .


### <a name="array-slices"></a>Wycinki tablicy

Podaną wyrażeniem tablicowym i `Range` wyrażeniem, należy utworzyć nowe wyrażenie przy użyciu operatora wycinka tablicy `[ ]` .
Nowe wyrażenie jest tego samego typu co tablica i zawiera elementy tablicy indeksowane przez elementy w `Range` kolejności zdefiniowanej przez `Range` .
Na przykład, jeśli `a` jest powiązany z tablicą typu `Double` , `a[3..-1..0]` to `Double[]` wyrażenie, które zawiera pierwsze cztery elementy, `a` ale w odwrotnej kolejności, jak pojawiają się w `a` .

Jeśli wartość `Range` jest pusta, powstaje wycinek tablicy o zerowej długości.

Podobnie jak w przypadku elementów tablicy odwołujących się, jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, należy umieścić je w nawiasach, aby je podzielić.
Na przykład jeśli `a` i `b` są obie tablice typu `Int` , wycinek z łączenia jest wyrażony jako:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Wywnioskowane wartości początkowe/końcowe

Począwszy od naszego [0,8 wydania](xref:microsoft.quantum.relnotes), obsługujemy kontekstowe wyrażenia dla dzielenia zakresów. W szczególności można pominąć zakres wartości początkowych i końcowych w kontekście wyrażenia wycinka zakresu. W takim przypadku kompilator stosuje następujące reguły w celu wywnioskowania zamierzonych ograniczników dla zakresu:

* Jeśli wartość *początkowa* zakresu zostanie pominięta, wywnioskowana wartość początkowa
  * ma wartość zero, jeśli nie określono żadnego kroku lub określony krok jest dodatni.  
  * jest długością tablicy wycinka minus jeden, jeśli określony krok jest ujemny.

* W przypadku pominięcia wartości *końcowej* zakresu, wywnioskowana wartość końcowa
  * jest długością tablicy wycinka minus jeden, jeśli żaden krok nie jest określony lub określony krok jest dodatni.
  * ma wartość zero, jeśli określony krok jest ujemny.

Przykłady to:

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

### <a name="copy-and-update-expressions"></a>Wyrażenia kopiowania i aktualizowania

Ponieważ wszystkie Q# typy są typami wartości (z qubitsą podjęciem nieco specjalnej roli), formularz "Copy" jest tworzony, gdy wartość jest powiązana z symbolem lub gdy jest on powiązany. Oznacza to, że zachowanie Q# jest takie samo jak w przypadku utworzenia kopii przy użyciu operatora przypisania. 

Oczywiście tylko odpowiednie fragmenty są ponownie tworzone w miarę potrzeb. Ma to wpływ na sposób kopiowania tablic, ponieważ nie jest możliwe aktualizowanie elementów tablicy. Aby zmodyfikować istniejącą tablicę, należy wykorzystać mechanizm *kopiowania i aktualizowania* .

Można utworzyć nową tablicę z istniejącej tablicy za pośrednictwem wyrażeń *kopiowania i aktualizowania* , które używają operatorów `w/` i `<-` .
Wyrażenie Copy-and-Update jest wyrażeniem formularza `expression1 w/ expression2 <- expression3` , gdzie

* `expression1` Typ musi być typem `T[]` `T` .
* `expression2` definiuje, które indeksy w tablicy określone w `expression1` do zmodyfikowania. `expression2` musi to być typ `Int` lub typ `Range` .
* `expression3` to wartości używane do aktualizowania elementów w programie `expression1` , na podstawie indeksów określonych w `expression2` . Jeśli `expression2` jest typu `Int` , `expression3` musi być typu `T` . Jeśli `expression2` jest typu `Range` , `expression3` musi być typu `T[]` .

Na przykład wyrażenie Copy-and-Update `arr w/ idx <- value` konstruuje nową tablicę ze wszystkimi elementami ustawionymi na odpowiadające im elementy w `arr` , z wyjątkiem elementów określonych przez `idx` , które są ustawione na wartości w `value` . 

Dostarczone `arr` zawiera tablicę `[0,1,2,3]` , a następnie 

- `arr w/ 0 <- 10` jest tablicą `[10,1,2,3]` .
- `arr w/ 2 <- 10` jest tablicą `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]` jest tablicą `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Wyrażenia Copy-and-Update dla nazwanych elementów

Podobne wyrażenia istnieją dla nazwanych elementów w typach zdefiniowanych przez użytkownika. 

Rozważmy na przykład typ 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Jeśli `c` zawiera wartość typu `Complex(1., -1.)` , `c w/ Re <- 0.` jest wyrażeniem typu, `Complex` który jest obliczany `Complex(0., -1.)` .

### <a name="jagged-arrays"></a>Tablice nieregularne

Tablica nieregularna, czasami nazywana "tablicą tablic," jest tablicą, której elementy są tablicami.
Elementy tablicy nieregularnej mogą mieć różne rozmiary.
Poniższy przykład pokazuje, jak zadeklarować i zainicjować tablicę nieregularną reprezentującą tabelę mnożenia.

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

### <a name="arrays-of-callables"></a>Tablice wywoływanych 

Można również utworzyć tablicę z możliwymi do przetworzenia.

* Jeśli wspólny typ elementu jest operacją lub typem funkcji, wszystkie elementy muszą mieć te same typy danych wejściowych i wyjściowych.
* Typ elementu tablicy obsługuje wszystkie [funktory](xref:microsoft.quantum.guide.operationsfunctions) , które są obsługiwane przez wszystkie elementy.
Na przykład jeśli `Op1` , `Op2` , i `Op3` wszystkie są `Qubit[] => Unit` operacjami, ale `Op1` obsługuje `Adjoint` , `Op2` obsługuje `Controlled` i `Op3` obsługuje obie:
  * `[Op1, Op2]` jest tablicą `(Qubit[] => Unit)` operacji.
  * `[Op1, Op3]` jest tablicą `(Qubit[] => Unit is Adj)` operacji.
  * `[Op2, Op3]` jest tablicą `(Qubit[] => Unit is Ctl)` operacji.

Jednak chociaż operacje `(Qubit[] => Unit is Adj)` i  `(Qubit[] => Unit is Ctl)` mają wspólny typ podstawowy `(Qubit[] => Unit)` , *tablice* tych operacji nie mają wspólnego typu podstawowego.

Na przykład `[[Op1], [Op2]]` obecnie zgłaszany jest błąd, ponieważ próbuje utworzyć tablicę dwóch niezgodnych typów tablicy `(Qubit[] => Unit is Adj)[]` i `(Qubit[] => Unit is Ctl)[]` .

Aby uzyskać więcej informacji o wywoływaniu, zobacz temat wywoływane [wyrażenia](#callable-expressions) na tej stronie lub [operacjach oraz funkcje w Q# ](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="conditional-expressions"></a>Wyrażenia warunkowe

W przypadku dwóch wyrażeń tego samego typu i wyrażenia logicznego należy utworzyć wyrażenie warunkowe przy użyciu znaku zapytania, `?` i paska pionowego `|` . W `a==b ? c | d` przypadku wartości wyrażenia warunkowego występuje wartość `c` true, `a==b` a jeśli wartość `d` to false.

### <a name="conditional-expressions-with-callables"></a>Wyrażenia warunkowe z możliwymi do odwoływać

Wyrażenia warunkowe mogą oszacować operacje, które mają te same dane wejściowe i wyjściowe, ale obsługują różne funktory. W tym przypadku typ wyrażenia warunkowego jest operacją z danymi wejściowymi i wyjściowymi, które obsługują wszystkie funktory obsługiwane przez oba wyrażenia.
Na przykład jeśli `Op1` , `Op2` , i `Op3` wszystkie są `Qubit[]=>Unit` , ale obsługuje, `Op1` `Adjoint` `Op2` obsługuje `Controlled` i `Op3` obsługuje obie:

- `flag ? Op1 | Op2` jest `(Qubit[] => Unit)` operacją.
- `flag ? Op1 | Op3` jest `(Qubit[] => Unit is Adj)` operacją.
- `flag ? Op2 | Op3` jest `(Qubit[] => Unit is Ctl)` operacją.

Jeśli jedno z dwóch możliwych wyrażeń wynikowych zawiera wywołanie funkcji lub operacji, to wywołanie odbywa się tylko wtedy, gdy ten wynik jest wartością wywołania. Na przykład w przypadku `a==b ? C(qs) | D(qs)` , gdy `a==b` ma wartość true, `C` operacja jest wywoływana, a jeśli ma wartość false, `D` wywoływana jest tylko operacja. Takie podejście jest podobne do *krótkich obwodów* w innych językach.

## <a name="callable-expressions"></a>Możliwe do przewyrażenia

Możliwy do przeprowadzenia literał jest nazwą operacji lub funkcji zdefiniowanej w zakresie kompilacji. Na przykład, `X` to literał operacji odwołujący się do standardowej `X` operacji biblioteki i `Message` jest literałem funkcji, która odwołuje się do standardowej `Message` funkcji biblioteki.

Jeśli operacja obsługuje `Adjoint` Funktor, `Adjoint op` to wyrażenie operacji.
Podobnie, jeśli operacja obsługuje `Controlled` Funktor, a następnie `Controlled op` jest wyrażeniem operacji.
Aby uzyskać więcej informacji na temat typów tych wyrażeń, zobacz temat [wywoływanie specjalizacji operacji](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Funktory ( `Adjoint` i `Controlled` ) wiąże się bardziej ściśle niż wszystkie inne operatory, z wyjątkiem operatora rozwinięcia `!` i indeksowania tablicy przy użyciu `[ ]` .
W ten sposób wszystkie są prawidłowe, przy założeniu, że operacje obsługują używany funktory:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Wyrażenia, które możliwe do napisania

Można użyć możliwego do oddzielenia literału jako wartości, na przykład w celu przypisania jej do zmiennej lub przekazania jej do innego elementu, który można wywołać. W tym przypadku, jeśli wywołano [parametry typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), należy podać parametry jako część wartości możliwej do nadania.

Wartość możliwej do odwoływać nie może mieć żadnych nieokreślonych parametrów typu. Na przykład jeśli `Fun` jest funkcją z podpisem `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Wywoływanie wyrażeń wywołania

W wyniku możliwego do wywołania wyrażenia (operacji lub funkcji) i wyrażenia spójnej kolekcji typu wejściowego można utworzyć *wyrażenie wywoływania* , dołączając wyrażenie krotki do możliwego do wywołania wyrażenia.
Typ wyrażenia wywołania jest typem wyjściowym podpisu, który ma zostać wywołany.

Na przykład jeśli `Op` jest operacją z podpisem `((Int, Qubit) => Double)` , `Op(3, qubit1)` jest wyrażeniem typu `Double` .
Podobnie, jeśli `Sin` jest funkcją z podpisem `(Double -> Double)` , `Sin(0.1)` jest wyrażeniem typu `Double` .
Na koniec, jeśli `Builder` jest funkcją z podpisem `(Int -> (Int -> Int))` , `Builder(3)` to funkcja z `Int` do `Int` .

Wywołanie wyniku wyrażenia z wartościami możliwymi do wywołania wymaga dodatkowej pary nawiasów wokół wartościowego wyrażenia.
W związku z tym, aby wywołać wynik wywołania `Builder` z poprzedniego akapitu, poprawna składnia to:

```qsharp
(Builder(3))(2)
```

Podczas wywoływania [sparametryzowanego typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , można określić rzeczywiste parametry typu w nawiasach kątowych `< >` po dodaniu wartości wyrażenia.
Ta akcja jest zwykle zbędna, ponieważ Q# kompilator wnioskuje o rzeczywiste typy.
Jednak *jest to* wymagane w przypadku [częściowej aplikacji](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , jeśli argument typu sparametryzowanego nie został określony.
Jest on również przydatny, gdy przekazywanie operacji przy użyciu różnych Funktor obsługuje wywoływany.

Na przykład, jeśli `Func` ma sygnaturę i ma sygnaturę `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` i `Op3` ma sygnaturę `(Qubit[] => Unit)` , do `Func` wywołania `Op1` jako pierwszy argument, `Op2` jako drugi, a `Op3` jako trzeci:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Specyfikacja typu jest wymagana, ponieważ `Op3` i `Op1` ma różne typy, więc kompilator będzie traktować ten sposób jako niejednoznaczny bez specyfikacji.


## <a name="operator-precedence"></a>Kolejność wykonywania działań

* Wszystkie operatory binarne są z prawej strony skojarzenia, z wyjątkiem `^` .

* Nawiasy kwadratowe, `[ ]` , w przypadku dzielenia i indeksowania tablicy, są powiązane przed dowolnym operatorem.

* Funktory `Adjoint` i `Controlled` Powiąż po indeksowaniu tablicy, ale przed wszystkimi innymi operatorami.

* Nawiasy dla wywołania operacji i funkcji są również powiązane przed dowolnym operatorem, ale po indeksowaniu tablicy i funktory.

Q# Operatory według pierwszeństwa, od najwyższego do najniższego:

Operator | Większa | Opis | Typy operandów
---------|----------|---------|---------------
 końcowe `!` | Jednoargumentowy | Unwrap | Dowolny typ zdefiniowany przez użytkownika
 `-`, `~~~`, `not` | Jednoargumentowy | Cyfra ujemna, dopełnienie bitowe, Negacja logiczna | `Int`, `BigInt` lub `Double` dla `-` , `Int` dla `BigInt` `~~~` `Bool``not`
 `^` | Binarne | Moc całkowita | `Int` lub `BigInt` dla podstawy `Int` dla wykładnika
 `/`, `*`, `%` | Binarne | Dzielenie, mnożenie, moduł całkowity | `Int`, `BigInt` lub `Double` dla `/` i `*` , `Int` lub `BigInt` dla `%`
 `+`, `-` | Binarne | Dodawanie lub łączenie ciągów i tablic, odejmowanie | `Int`, `BigInt` or `Double` , dodatkowo `String` lub dowolnego typu tablicy dla `+`
 `<<<`, `>>>` | Binarne | Lewy Shift, prawy Shift | `Int` lub `BigInt`
 `<`, `<=`, `>`, `>=` | Binarne | Mniejsze niż, mniejsze niż lub równe, większe niż, większe niż lub równe | `Int``BigInt`lub`Double`
 `==`, `!=` | Binarne | porównania równe, nierówne | dowolny typ pierwotny
 `&&&` | Binarne | Bitowe ORAZ | `Int` lub `BigInt`
 `^^^` | Binarne | Bitowe XOR | `Int` lub `BigInt`
 <code>\|\|\|</code> | Binarne | Bitowe OR | `Int` lub `BigInt`
 `and` | Binarne | Logiczne AND | `Bool`
 `or` | Binarne | Logiczne OR | `Bool`
 `..` | Plik binarny/Trzyelementowy | Operator zakresu | `Int`
 `?` `|` | Trójargumentowy | Warunkowe | `Bool` po lewej stronie
`w/` `<-` | Trójargumentowy | Kopiuj i Aktualizuj | Zobacz [wyrażenia kopiowania i aktualizowania](#copy-and-update-expressions)

## <a name="next-steps"></a>Następne kroki

Teraz, gdy możesz korzystać z wyrażeń w Q# , przejdź do [operacji i funkcji w programie Q# ](xref:microsoft.quantum.guide.operationsfunctions) , aby dowiedzieć się, jak definiować i wywoływać operacje i funkcje.

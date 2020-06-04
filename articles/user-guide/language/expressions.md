---
title: 'Wyrażenia typu w Q #'
description: 'Dowiedz się, jak określać, odwoływać i łączyć stałe, zmienne, operatory, operacje i funkcje jako wyrażenia w Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: c4b2cc0bed44ffdfb191ba522d6526959e7c6708
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327309"
---
# <a name="type-expressions-in-q"></a>Wyrażenia typu w Q #

## <a name="numeric-expressions"></a>Wyrażenia liczbowe

Wyrażenia liczbowe są wyrażeniami typu `Int` , `BigInt` , lub `Double` .
Oznacza to, że są to liczby całkowite lub zmiennoprzecinkowe.

`Int`literały w Q # są zapisywane po prostu jako sekwencja cyfr.
Liczby całkowite szesnastkowe i binarne są obsługiwane odpowiednio przy użyciu `0x` `0b` prefiksu i.

`BigInt`literały w Q # są zapisywane z końcowym `l` lub `L` sufiksem.
Szesnastkowe duże liczby całkowite są obsługiwane z prefiksem "0x".
W ten sposób wszystkie prawidłowe zastosowania `BigInt` literałów są następujące:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`literały w Q # są liczbami zmiennoprzecinkowymi zapisanymi przy użyciu cyfr dziesiętnych.
Mogą być zapisywane z przecinkiem dziesiętnym, `.` , i/lub części wykładniczej wskazanej za pomocą znaku "e" lub "e" (po których dozwolone są tylko możliwe znaki minus i cyfry dziesiętne).
Poniżej podano prawidłowe `Double` literały: `0.0` , `1.2e5` , `1e-5` .

Jeśli wyrażenie tablicy dowolnego typu elementu, `Int` wyrażenie może być utworzone przy użyciu [`Length`](xref:microsoft.quantum.core.length) wbudowanej funkcji, z wyrażeniem tablicy ujętym w nawiasy `(` i `)` .
Na przykład, jeśli `a` jest powiązany z tablicą, `Length(a)` jest wyrażeniem liczby całkowitej.
Jeśli `b` jest tablicą tablic liczb całkowitych, `Int[][]` , a następnie `Length(b)` jest liczbą tablic w `b` , i `Length(b[1])` jest liczbą liczb całkowitych w drugiej tablicy podrzędnej w `b` .

Uwzględniając dwa wyrażenia liczbowe tego samego typu, operatory binarne,, `+` `-` `*` i `/` mogą być używane do tworzenia nowego wyrażenia liczbowego.
Typ nowego wyrażenia będzie taki sam jak typy wyrażeń składowych.

W przypadku dwóch wyrażeń całkowitych operator binarny `^` (potęga) może służyć do tworzenia nowego wyrażenia liczb całkowitych.
Podobnie, można `^` użyć z dwoma wyrażeniami podwójnymi, aby utworzyć nowe wyrażenie podwójne.
Na koniec, `^` może być używany z dużą liczbą całkowitą z lewej strony i liczbą całkowitą z prawej strony, aby utworzyć nowe wyrażenie Big Integer.
W takim przypadku drugi parametr musi pasować do 32 bitów; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.

W przypadku dwóch wyrażeń całkowitych lub dużych liczb całkowitych można utworzyć nowe wyrażenie typu Integer lub Big Integer przy użyciu `%` operatorów (moduł), `&&&` (bitowe and), `|||` (bitowego or) lub `^^^` (bitowe XOR).

W przypadku wyrażenia typu Integer lub Big Integer po lewej stronie i wyrażenia liczb całkowitych po prawej stronie `<<<` Operatory (arytmetyczne przesunięcie w lewo) lub `>>>` (arytmetyczne przesunięcie w prawo) mogą być używane do tworzenia nowego wyrażenia z tym samym typem co lewe wyrażenie.

Drugi parametr (wartość przesunięcia) dla operacji Shift musi być większy lub równy zero; zachowanie dla ujemnych kwot przesunięcia jest niezdefiniowane.
Wartość przesunięcia dla operacji przesunięcia musi być również zgodna z 32 bitowymi; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.
Jeśli liczba, która ma zostać przesunięta jest liczbą całkowitą, jest interpretowana wartość przesunięcia, `mod 64` czyli przesunięcie 1 i przesunięcie 65 ma ten sam efekt.

W przypadku wartości liczb całkowitych i dużych liczb całkowitych przesunięcia są arytmetyczne.
Przesunięcie wartości ujemnej w lewo lub w prawo spowoduje powstanie liczby ujemnej.
Oznacza to, że przesunięcie jeden krok w lewo lub w prawo jest dokładnie takie samo jak mnożenie lub dzielenie odpowiednio przez 2.

Dzielenie liczb całkowitych i moduł całkowity są zgodne z tym samym zachowaniem dla liczb ujemnych w języku C#.
Oznacza to, że `a % b` będzie zawsze mieć ten sam znak jako `a` i `b * (a / b) + a % b` zawsze będzie równa się `a` .
Przykład:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

Dzielenie z dużymi liczbami całkowitymi i moduł działa w taki sam sposób.

Mając każde wyrażenie liczbowe, nowe wyrażenie może być utworzone za pomocą `-` operatora jednoargumentowego.
Nowe wyrażenie będzie tego samego typu co wyrażenie elementu.

W przypadku dowolnego wyrażenia typu Integer lub Big Integer nowe wyrażenie tego samego typu może być sformułowane przy użyciu `~~~` operatora jednoargumentowego (dopełnienie bitowe).

## <a name="boolean-expressions"></a>Wyrażenia logiczne

Dwie `Bool` wartości literału są `true` i `false` .

Uwzględniając wszystkie dwa wyrażenia tego samego typu pierwotnego, `==` Operatory i `!=` mogą być używane do konstruowania `Bool` wyrażenia.
Wyrażenie będzie prawdziwe, jeśli dwa wyrażenia są równe, i wartość false, jeśli nie.

Wartości typów zdefiniowanych przez użytkownika mogą nie być porównywane. można porównać tylko ich nieopakowane wartości. Na przykład przy użyciu operatora "unotoka" `!` (szczegółowo wyjaśniono w [typach w Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

Porównywanie równości dla `Qubit` wartości jest równość tożsamości; oznacza to, czy dwa wyrażenia identyfikują ten sam qubit.
Stan dwóch qubits nie jest porównywany, dostępny, mierzony ani modyfikowany przez to porównanie.

Porównywanie równości dla `Double` wartości może być mylące ze względu na efekt zaokrąglenia.
Na przykład `49.0 * (1.0/49.0) != 1.0` .

Uwzględniając wszystkie dwa wyrażenia liczbowe, operatory binarne `>` ,, `<` `>=` i `<=` mogą być używane do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli pierwsze wyrażenie jest odpowiednio większe niż, mniejsze niż, większe niż lub równe lub mniejsze lub równe drugiemu wyrażeniu.

W przypadku wszystkich dwóch wyrażeń logicznych `and` Operatory i `or` mogą być używane do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli oba wyrażenia (komp. or lub Both) mają wartość true.

Mając każde wyrażenie logiczne, `not` operator jednoargumentowy może służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli wyrażenie elementu składowego ma wartość false.

## <a name="string-expressions"></a>Wyrażenia ciągów

Funkcja Q # umożliwia używanie ciągów w `fail` instrukcji (wyjaśniono w [przepływie sterowania](xref:microsoft.quantum.guide.controlflow#fail-statement)) i w [`Message`](xref:microsoft.quantum.intrinsic.message) funkcji standardowej.
Określone zachowanie tego elementu jest zależne od używanego symulatora, ale zazwyczaj zapisuje komunikat do konsoli hosta po wywołaniu w programie Q #.

Ciągi w Q # są literałami lub interpolowanymi ciągami.

Literały ciągu są podobne do prostych literałów ciągu w większości języków: sekwencji znaków Unicode ujętych w podwójne cudzysłowy `"` .
Wewnątrz ciągu znak ukośnika odwrotnego `\` może być używany do ucieczki podwójnego znaku cudzysłowu i do wstawiania nowej linii jako `\n` , powrotu karetki jako `\r` i karty jako `\t` .
Przykład:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Ciągi interpolowane

Składnia Q # dla interpolacji ciągów jest podzbiorem składni języka C#, ale w tym miejscu podsumowano najważniejsze punkty, które odnoszą się do Q #.
Główne rozróżnienia zostały omówione poniżej.

Aby zidentyfikować literał ciągu jako ciąg interpolowany, poprzedź go `$` symbolem.
Między `$` i `"` , które zaczyna się literałem ciągu znaków, nie może zawierać żadnego odstępu.

Poniżej znajduje się podstawowy przykład, za pomocą którego [`Message`](xref:microsoft.quantum.intrinsic.message) można napisać wynik pomiaru do konsoli wraz z innymi wyrażeniami Q #.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
Dowolne prawidłowe wyrażenie Q # może pojawić się w ciągu interpolowanym.

Więcej szczegółowych informacji na temat składni języka C# można znaleźć w [*ciągach interpolowanych*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).
Najbardziej istotną różnicą jest to, że Q # nie obsługuje ciągów interpolowanych Verbatim (wiele wierszy).
Wyrażenia wewnątrz ciągu interpolowanego są zgodne z składnią Q #, a nie składnią języka C#.

## <a name="range-expressions"></a>Wyrażenia zakresu

Każde trzy `Int` wyrażenie `start` , `step` , i `stop` , `start .. step .. stop` jest wyrażeniem zakresu, którego pierwszy element jest `start` , drugi element jest `start+step` , trzeci element jest `start+step+step` itp., do do `stop` .
Zakres może być pusty, jeśli na przykład `step` jest wartością dodatnią i `stop < start` .
Ostatnim elementem zakresu będzie `stop` , jeśli różnica między `start` i `stop` jest całkowitą wielokrotnością `step` ; oznacza to, że zakres jest włącznie na obu końcach.

Uwzględniając wszystkie dwa `Int` wyrażenia `start` i `stop` , `start .. stop` jest wyrażenie zakresu, które jest równe `start .. 1 .. stop` .
Należy zauważyć, że implikowana `step` wartość to + 1 `stop` , nawet jeśli jest mniejsza niż `start` ; w takim przypadku zakres jest pusty.

Oto kilka przykładowych zakresów:

- `1..3`jest zakresem 1, 2, 3.
- `2..2..5`jest zakresem od 2 do 4.
- `2..2..6`jest zakresem 2, 4, 6.
- `6..-2..2`jest zakresem 6, 4, 2.
- `2..1`jest pustym zakresem.
- `2..6..7`jest zakresem 2.
- `2..2..1`jest pustym zakresem.
- `1..-1..2`jest pustym zakresem.

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

Literał krotki to sekwencja wyrażeń elementu odpowiedniego typu, rozdzielona przecinkami, ujęta w `(` i `)` .
Na przykład `(1, One)` jest `(Int, Result)` wyrażeniem.

W przypadku innych niż literały jedynymi wyrażeniami krotek są symbole, które są powiązane z wartościami krotki, elementami tablicy tablic krotek i wywoływanie wywołań, które zwracają krotki.

## <a name="user-defined-type-expressions"></a>Wyrażenia typu zdefiniowanego przez użytkownika

Literał typu zdefiniowanego przez użytkownika składa się z nazwy typu, a następnie literału krotki typu krotki podstawowej typu.
Na przykład, jeśli `IntPair` jest typem zdefiniowanym przez użytkownika na podstawie `(Int, Int)` , `IntPair(2, 3)` byłby on prawidłowym literałem tego typu.

Oprócz literałów jedynymi wyrażeniami typu zdefiniowanego przez użytkownika są symbole, które są powiązane z wartościami tego typu, elementy tablicy tablic tego typu i wywoływanie wywołań, które zwracają ten typ.

## <a name="unwrap-expressions"></a>Odpakowywanie wyrażeń

W Q # operator rozwinięcia jest końcowym wykrzyknikiem `!` .
Na przykład, jeśli `IntPair` jest typem zdefiniowanym przez użytkownika z typem źródłowym `(Int, Int)` i `s` była zmienną z wartością `IntPair(2, 3)` , wówczas `s!` zostałby `(2, 3)` .

Dla typów zdefiniowanych przez użytkownika, zdefiniowanych w warunkach innych typów zdefiniowanych przez użytkownika. operatora rozwinięcia można powtórzyć; na przykład `s!!` wskazuje podwójnie nieopakowaną wartość `s` .
W takim przypadku, jeśli `WrappedPair` jest typem zdefiniowanym przez użytkownika z typem źródłowym `IntPair` i `t` jest zmienną z wartością `WrappedPair(IntPair(1,2))` , wówczas `t!!` zostałby `(1,2)` .

`!`Operator ma wyższy priorytet niż wszystkie inne operatory inne niż `[]` dla indeksowania tablicy i dzielenia.
`!`i `[]` powiąże się z pozycją, czyli `a[i]![3]` należy ją przeczytać jako `((a[i])!)[3]` : Take `i` "ty" elementu `a` , Odpakuj go, a następnie Pobierz trzeci element nieopakowanej wartości (która musi być tablicą).

Pierwszeństwo `!` operatora ma jeden wpływ, który może nie być oczywisty.
Jeśli funkcja lub operacja zwraca wartość, która staje się nieopakowana, wywołanie funkcji lub operacji musi być ujęte w nawiasy, tak aby krotka argumentu była powiązana z wywołaniem, a nie z odwinięciem.
Przykład:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Wyrażenia tablic

Literał tablicowy jest sekwencją co najmniej jednego wyrażenia elementu, rozdzielonych przecinkami, ujęty w `[` i `]` .
Wszystkie elementy muszą być zgodne z tym samym typem.

Mając daną dwie tablice tego samego typu, operator binarny `+` może służyć do tworzenia nowej tablicy, która jest połączeniem dwóch tablic.
Na przykład `[1,2,3] + [4,5,6]` ma `[1,2,3,4,5,6]` .

### <a name="array-creation"></a>Tworzenie tablicy

Uwzględniając typ i `Int` wyrażenie, `new` operator może służyć do przydzielenia nowej tablicy o danym rozmiarze.
Na przykład `new Int[i + 1]` przydzieli nową `Int` tablicę z `i + 1` elementami.

Puste literały tablicowe, `[]` , są niedozwolone.
Zamiast używać `new ★[0]` , gdzie `★` jest jako symbol zastępczy dla odpowiedniego typu, umożliwia utworzenie odpowiedniej tablicy o długości zero.

Elementy nowej tablicy są inicjowane z wartością domyślną zależną od typu.
W większości przypadków jest to pewna odmiana zero.

W przypadku qubits i elementów, które są odwołaniami do jednostek, nie ma żadnej rozsądnej wartości domyślnej.
W tym przypadku dla tych typów wartość domyślna to nieprawidłowe odwołanie, którego nie można użyć bez powodowania błędu czasu wykonywania.
Jest to podobne do odwołania o wartości null w językach, takich jak C# lub Java.
Tablice zawierające qubits lub elementy wywoływane muszą zostać prawidłowo zainicjowane przy użyciu wartości innych niż domyślne, zanim ich elementy mogą być bezpiecznie używane. Odpowiednie procedury inicjowania można znaleźć w temacie <xref:microsoft.quantum.arrays> .

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
 `Range` | Pusty zakres,`1..1..0`
 `Callable` | _nieprawidłowe wywoływanie_
 `Array['T]` | `'T[0]`

Typy krotek są inicjowane element po elemencie.


### <a name="array-elements"></a>Elementy tablicy

Jeśli wyrażenie tablicowe i `Int` wyrażenie, nowe wyrażenie może być utworzone przy użyciu `[` `]` operatora elementu Array i.
Nowe wyrażenie będzie tego samego typu co typ elementu tablicy.
Na przykład, jeśli `a` jest powiązany z tablicą `Double` s, a następnie `a[4]` jest `Double` wyrażeniem.

Jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, musi być ujęte w nawiasy, aby można było wybrać element.
Na przykład, jeśli `a` i `b` są obie tablice `Int` s, element z łączenia zostałby wyrażony jako:

```qsharp
(a + b)[13]
```

Wszystkie tablice w Q # są oparte na zero.
Oznacza to, że pierwszy element tablicy `a` jest zawsze `a[0]` .


### <a name="array-slices"></a>Wycinki tablicy

Jeśli wyrażenie tablicowe i `Range` wyrażenie, nowe wyrażenie może być utworzone przy użyciu `[` `]` operatora wycinka Array i.
Nowe wyrażenie będzie tego samego typu co tablica i będzie zawierać elementy tablicy indeksowane przez elementy `Range` w kolejności zdefiniowanej przez `Range` .
Na przykład, jeśli `a` jest powiązany z tablicą `Double` s, a następnie `a[3..-1..0]` jest `Double[]` wyrażeniem zawierającym cztery pierwsze elementy z, `a` ale w odwrotnej kolejności, jak pojawiają się w `a` .

Jeśli wartość `Range` jest pusta, powstający wycink tablicy będzie zerem o zerowej długości.

Podobnie jak w przypadku elementów tablicy odwołujących się, jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, musi być ujęte w nawiasy klamrowe w celu wycięcia.
Jeśli `a` i `b` są obydwa tablice `Int` s, wycinek z łączenia będzie wyrażony jako:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Wywnioskowane wartości początkowe/końcowe

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

### <a name="copy-and-update-expressions"></a>Wyrażenia kopiowania i aktualizowania

Ponieważ wszystkie typy Q # są typami wartości — w przypadku qubits z bardzo specjalną rolą — "kopia" jest tworzona, gdy wartość jest powiązana z symbolem lub gdy jest on powiązany. Oznacza to, że zachowanie Q # jest takie samo, jak w przypadku tworzenia kopii podczas przypisywania.
Oczywiście w praktyce tylko odpowiednie fragmenty są w rzeczywistości odtworzone w razie potrzeby. 

Dotyczy to również tablic.
W szczególności nie jest możliwe aktualizowanie elementów tablicy. Aby zmodyfikować istniejącą tablicę, należy wykorzystać mechanizm *kopiowania i aktualizowania* .

Nowe tablice można tworzyć z istniejących za pośrednictwem wyrażeń *kopiowania i aktualizowania* .
Wyrażenie Copy-and-Update jest wyrażeniem formularza `expression1 w/ expression2 <- expression3` , gdzie `expression1` musi być typu `T[]` dla pewnego typu `T` .
Sekunda `expression2` definiuje indeksy elementów do zmodyfikowania w porównaniu do tablicy w `expression1` i musi być typu `Int` lub typu `Range` .
Jeśli `expression2` jest typu `Int` , `expression3` musi być typu `T` . Jeśli `expression2` jest typu `Range` , `expression3` musi być typu `T[]` .

Wyrażenie Copy-and-Update `arr w/ idx <- value` konstruuje nową tablicę ze wszystkimi elementami ustawionymi na odpowiadający element w `arr` , z wyjątkiem elementów `idx` , które są ustawione na jeden z nich w `value` . Na przykład, jeśli `arr` zawiera tablicę `[0,1,2,3]` , 
- `arr w/ 0 <- 10`jest tablicą `[10,1,2,3]` .
- `arr w/ 2 <- 10`jest tablicą `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]`jest tablicą `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Wyrażenia Copy-and-Update dla nazwanych elementów

Podobne wyrażenia istnieją dla nazwanych elementów w typach zdefiniowanych przez użytkownika. 

Rozważmy przykład typu 

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

Należy zauważyć, że więcej informacji na temat żądanych typów można znaleźć poniżej, a także na następnej stronie, [operacji i funkcji w Q #](xref:microsoft.quantum.guide.operationsfunctions).

Jeśli wspólny typ elementu jest operacją lub typem funkcji, wszystkie elementy muszą mieć te same typy danych wejściowych i wyjściowych.
Typ elementu tablicy będzie obsługiwał wszystkie funktory, które są obsługiwane przez wszystkie elementy.
Na przykład jeśli `Op1` , `Op2` , i `Op3` wszystkie są `Qubit[] => Unit` , ale obsługuje, `Op1` `Adjoint` `Op2` obsługuje `Controlled` i `Op3` obsługuje obie:

- `[Op1, Op2]`jest tablicą `(Qubit[] => Unit)` operacji.
- `[Op1, Op3]`jest tablicą `(Qubit[] => Unit is Adj)` operacji.
- `[Op2, Op3]`jest tablicą `(Qubit[] => Unit is Ctl)` operacji.

Jednak chociaż `(Qubit[] => Unit is Adj)` `(Qubit[] => Unit is Ctl)` operacje mają wspólny typ podstawowy `(Qubit[] => Unit)` , należy pamiętać, że tablice tych operatorów *of* nie mają wspólnego typu podstawowego. Na przykład `[[Op1], [Op2]]` obecnie zgłaszany jest błąd, ponieważ próbuje on utworzyć tablicę niezgodnych typów tablicy `(Qubit[] => Unit is Adj)[]` i `(Qubit[] => Unit is Ctl)[]` .


## <a name="conditional-expressions"></a>Wyrażenia warunkowe

Uwzględniając dwa inne wyrażenia tego samego typu i wyrażenie logiczne, wyrażenie warunkowe może być utworzone przy użyciu znaku zapytania `?` i pionowego paska `|` .
Na przykład `a==b ? c | d` .
W tym przykładzie wartość wyrażenia warunkowego będzie równa true, `c` `a==b` a `d` Jeśli jest fałszywa.

### <a name="conditional-expressions-with-callables"></a>Wyrażenia warunkowe z możliwymi do odwoływać

Dwa wyrażenia mogą oszacować do operacji, które mają te same dane wejściowe i wyjściowe, ale obsługują różne funktory.
W tym przypadku typ wyrażenia warunkowego jest operacją z tymi danymi wejściowymi i wyjściowymi, które obsługują wszystkie funktory obsługiwane przez oba wyrażenia.
Na przykład jeśli `Op1` , `Op2` , i `Op3` wszystkie są `Qubit[]=>Unit` , ale obsługuje, `Op1` `Adjoint` `Op2` obsługuje `Controlled` i `Op3` obsługuje obie:

- `flag ? Op1 | Op2`jest `(Qubit[] => Unit)` operacją.
- `flag ? Op1 | Op3`jest `(Qubit[] => Unit is Adj)` operacją.
- `flag ? Op2 | Op3`jest `(Qubit[] => Unit is Ctl)` operacją.

Jeśli jedno z dwóch możliwych wyrażeń wynikowych zawiera wywołanie funkcji lub operacji, to wywołanie będzie odbywać się tylko wtedy, gdy ten wynik będzie wartością wywołania.
Na przykład w przypadku `a==b ? C(qs) | D(qs)` , gdy `a==b` ma wartość true, `C` operacja zostanie wywołana, a jeśli ma wartość false, tylko `D` zostanie wywołana.
Jest to podobne do krótkich obwodów w innych językach.

## <a name="callable-expressions"></a>Możliwe do przewyrażenia

Możliwy do przeprowadzenia literał jest nazwą operacji lub funkcji zdefiniowanej w zakresie kompilacji.
Na przykład, `X` to literał operacji odwołujący się do standardowej `X` operacji biblioteki i `Message` jest literalną funkcją, która odwołuje się do standardowej `Message` funkcji biblioteki.

Jeśli operacja obsługuje `Adjoint` Funktor, `Adjoint op` to wyrażenie operacji.
Podobnie, jeśli operacja obsługuje `Controlled` Funktor, a następnie `Controlled op` jest wyrażeniem operacji.
Typy tych wyrażeń są określane podczas [wywoływania specjalizacji operacji](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Funktory ( `Adjoint` i `Controlled` ) wiąże się bardziej ściśle niż wszystkie inne operatory, z wyjątkiem operatora rozwinięcia `!` i indeksowania tablicy z [] ".
W ten sposób obowiązują wszystkie kwestie prawne, przy założeniu, że operacje obsługują użycie funktory:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Wyrażenia, które możliwe do napisania

Możliwy do oddzielenia literału można użyć jako wartości, powiedzmy, aby przypisać do zmiennej lub przekazać do innego elementu.
W takim przypadku, jeśli wywoływany ma [parametry typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), muszą one być podane jako część wartości możliwej do napisania.
Wartość możliwej do odwoływać nie może mieć żadnych nieokreślonych parametrów typu.

Na przykład jeśli `Fun` jest funkcją z podpisem `'T1->Unit` :

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Wywoływanie wyrażeń wywołania

Dane wyrażenie możliwego do wywołania (operacji lub funkcji) i wyrażenie spójnej kolekcji typu wejściowego w podpisie, wyrażenie wywoływania może być sformułowane przez dołączenie wyrażenia krotki do możliwego do wywołania wyrażenia.
Typ wyrażenia wywołania jest typem wyjściowym podpisu, który ma zostać wywołany.

Na przykład jeśli `Op` jest operacją z podpisem `((Int, Qubit) => Double)` , `Op(3, qubit1)` jest wyrażeniem typu `Double` .
Podobnie, jeśli `Sin` jest funkcją z podpisem `(Double -> Double)` , `Sin(0.1)` jest wyrażeniem typu `Double` .
Na koniec, jeśli `Builder` jest funkcją z podpisem `(Int -> (Int -> Int))` , `Builder(3)` to funkcja od do int.

Wywołanie wyniku wyrażenia z wartościami możliwymi do wywołania wymaga dodatkowej pary nawiasów wokół wartościowego wyrażenia.
W związku z tym, aby wywołać wynik wywołania `Builder` z poprzedniego akapitu, poprawna składnia to:

```qsharp
(Builder(3))(2)
```

W przypadku wywołania [sparametryzowanego typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , rzeczywiste parametry typu można określić w nawiasach kątowych `<` i `>` po wyrażeniu możliwym do wywołania.
Zwykle nie jest to konieczne, ponieważ kompilator Q # wykryje rzeczywiste typy.
Jednak *jest to* wymagane w przypadku [częściowej aplikacji](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , jeśli argument typu sparametryzowanego nie został określony.
Jest to również czasami przydatne, gdy przekazywanie operacji z różnymi Funktor obsługuje do możliwego do odwoływać.

Na przykład, jeśli `Func` ma sygnaturę i ma sygnaturę `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` i `Op3` ma sygnaturę `(Qubit[] => Unit)` , do `Func` wywołania `Op1` jako pierwszy argument, `Op2` jako drugi i `Op3` jako trzeci:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

Specyfikacja typu jest wymagana, ponieważ `Op3` i `Op1` ma różne typy, więc kompilator będzie traktować ten sposób jako niejednoznaczny bez specyfikacji.


## <a name="operator-precedence"></a>Kolejność wykonywania działań

Wszystkie operatory binarne są z prawej strony skojarzenia, z wyjątkiem `^` .

Nawiasy klamrowe `[` i `]` , w przypadku dzielenia i indeksowania tablicy, należy powiązać przed dowolnym operatorem.

Funktory `Adjoint` i `Controlled` Powiąż po indeksowaniu tablicy, ale przed wszystkimi innymi operatorami.

Nawiasy dla wywołania operacji i funkcji są również powiązane przed dowolnym operatorem, ale po indeksowaniu tablicy i funktory.

Operatory według pierwszeństwa, od najwyższego do najniższego:

Operator | Większa | Opis | Typy operandów
---------|----------|---------|---------------
 końcowe`!` | Jednoargumentowy | Unwrap | Dowolny typ zdefiniowany przez użytkownika
 `-`, `~~~`, `not` | Jednoargumentowy | Cyfra ujemna, dopełnienie bitowe, Negacja logiczna | `Int`, `BigInt` lub `Double` dla `-` , `Int` dla `BigInt` `~~~` `Bool``not`
 `^` | Binarne | Moc całkowita | `Int`lub `BigInt` dla podstawy `Int` dla wykładnika
 `/`, `*`, `%` | Binarne | Dzielenie, mnożenie, moduł całkowity | `Int`, `BigInt` lub `Double` dla `/` i `*` , `Int` lub `BigInt` dla`%`
 `+`, `-` | Binarne | Dodawanie lub łączenie ciągów i tablic, odejmowanie | `Int`, `BigInt` or `Double` , dodatkowo `String` lub dowolnego typu tablicy dla`+`
 `<<<`, `>>>` | Binarne | Lewy Shift, prawy Shift | `Int` lub `BigInt`
 `<`, `<=`, `>`, `>=` | Binarne | Mniejsze niż, mniejsze niż lub równe, większe niż, większe niż lub równe | `Int``BigInt`lub`Double`
 `==`, `!=` | Binarne | porównania równe, nierówne | dowolny typ pierwotny
 `&&&` | Binarne | Bitowe ORAZ | `Int` lub `BigInt`
 `^^^` | Binarne | Bitowe XOR | `Int` lub `BigInt`
 <code>\|\|\|</code> | Binarne | Bitowe OR | `Int` lub `BigInt`
 `and` | Binarne | Logiczne AND | `Bool`
 `or` | Binarne | Logiczne OR | `Bool`
 `..` | Plik binarny/Trzyelementowy | Operator zakresu | `Int`
 `?` `|` | Trójargumentowy | Warunkowe | `Bool`po lewej stronie
`w/` `<-` | Trójargumentowy | Kopiuj i Aktualizuj | Zobacz [wyrażenia kopiowania i aktualizowania](#copy-and-update-expressions)

## <a name="next-steps"></a>Następne kroki

Teraz, gdy można korzystać z wyrażeń w Q #, można [odstawić do operacji i funkcji w q #](xref:microsoft.quantum.guide.operationsfunctions) , aby dowiedzieć się, jak definiować i wywoływać operacje i funkcje.

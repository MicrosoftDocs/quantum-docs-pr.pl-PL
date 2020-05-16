---
title: 'Typy w Q #'
description: 'Dowiedz się więcej na temat różnych typów używanych w języku programowania Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 58370193bd62e306197a9e07c28f8611f043e55c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431142"
---
# <a name="types-in-q"></a>Typy w Q #

Na tej stronie przedstawiono model typu Q # i opisano składnię służącą do określania typów i pracy z typami.
Następna strona, [wyrażenia typu](xref:microsoft.quantum.guide.expressions), szczegóły dotyczące tworzenia i operowania wyrażeniami tych typów.

Należy pamiętać, że funkcja Q # jest językiem o *jednoznacznie określonym* typie, w taki sposób, że dokładne użycie tych typów może pomóc kompilatorowi zapewnić silne gwarancje dotyczące programów Q # w czasie kompilacji.
Aby zapewnić najwyższy możliwy poziom gwarancji, konwersje między typami w Q # muszą być jawne przy użyciu wywołań do funkcji, które wyrażają konwersję. Różne takie funkcje są dostępne jako część <xref:microsoft.quantum.convert> przestrzeni nazw.
Rzutowanie na zgodne typy z drugiej strony odbywa się niejawnie. 

Polecenie Q # zapewnia typy pierwotne, które mogą być używane bezpośrednio, i różne sposoby tworzenia nowych typów z innych typów.
Opiszemy każdą z nich w pozostałej części tej sekcji.

## <a name="primitive-types"></a>Typy pierwotne

Język Q # zawiera kilka *typów pierwotnych*, z których można utworzyć inne typy:

- `Int`Typ reprezentuje 64-bitową liczbę całkowitą ze znakiem, np.: `2` , `107` , `-5` .
- `BigInt`Typ reprezentuje podpisaną liczbę całkowitą o dowolnym rozmiarze, np. `2L` , `107L` , `-5L` .
   Ten typ jest oparty na platformie .NET<xref:System.Numerics.BigInteger>
   Wprowadź.
- `Double`Typ reprezentuje liczbę zmiennoprzecinkową o podwójnej precyzji, np.: `0.0` , `-1.3` , `4e-7` .
- `Bool`Typ reprezentuje wartość logiczną, która może być `true` lub `false` .
- `Range`Typ reprezentuje sekwencję liczb całkowitych, wskazywane przez `start..step..stop` , gdzie oznacza to opcje. 
   Odpowiada to `start .. stop` `start..1..stop` , a np. `1..2..7` reprezentuje sekwencję $ \{ 1, 3, 5, 7 \} $.
- `String`Typ jest sekwencją znaków Unicode, które są nieprzezroczyste dla użytkownika po utworzeniu.
  Ten typ służy do zgłaszania komunikatów do klasycznego hosta w przypadku błędu lub zdarzenia diagnostycznego.
- `Unit`Typ jest typem, który dopuszcza tylko jedną wartość `()` . 
  Ten typ jest używany do wskazania, że funkcja Q # lub operacja nie zwraca żadnych informacji. 
- `Qubit`Typ reprezentuje bit Quantum lub qubit.
   `Qubit`s nie jest nieprzezroczysty dla użytkownika; Jedyną operacją dopuszczalną dla nich, inną niż przekazanie jej do innej operacji, jest przetestowanie pod kątem tożsamości (równość).
   Ostatecznie akcje na `Qubit` s są implementowane przez wywołanie wewnętrznych instrukcji na procesorze Quantum (lub w jego symulacji).
- `Pauli`Typ reprezentuje jeden z czterech operatorów Pauli pojedynczej qubit.
   Ten typ służy do oznaczania operacji podstawowej dla rotacji i do określenia zauważalnego pomiaru.
   Jest to typ wyliczeniowy, który ma cztery możliwe wartości: `PauliI` , `PauliX` , `PauliY` , i `PauliZ` , które są stałymi typu `Pauli` .
- `Result`Typ reprezentuje wynik pomiaru.
   Jest to typ wyliczeniowy z dwoma możliwymi wartościami: `One` i `Zero` , które są stałymi typu `Result` .
   `Zero`wskazuje, że eigenvalue + 1 została zmierzona; `One`wskazuje wartość-1 eigenvalue.

Stałe,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` i `Zero` są zastrzeżonymi symbolami w Q #.

## <a name="array-types"></a>Typy tablic

Uwzględniając dowolny prawidłowy typ Q # `'T` , istnieje typ, który reprezentuje tablicę wartości typu `'T` .
Ten typ tablicy jest reprezentowany jako `'T[]` ; na przykład `Qubit[]` lub `Int[][]` .
Na przykład, kolekcja liczb całkowitych jest oznaczona `Int[]` , podczas gdy tablica tablic `(Bool, Pauli)` wartości jest oznaczona `(Bool, Pauli)[][]` .

W drugim przykładzie należy zauważyć, że reprezentuje to potencjalnie nieregularną tablicę tablic, a nie prostokątną dwuwymiarową tablicę.
Usługa Q # nie zapewnia obsługi prostokątnych tablic wielowymiarowych.

Wartość tablicy można napisać w kodzie źródłowym Q # przy użyciu nawiasów kwadratowych wokół elementów tablicy, jak w `[PauliI, PauliX, PauliY, PauliZ]` .
Typ literału tablicy jest określany przez wspólny typ podstawowy wszystkich elementów w tablicy. 

> [!WARNING]
> Elementy tablicy nie mogą być zmieniane po utworzeniu tablicy.
> [Instrukcje Update-and-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) i/lub [wyrażenia Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) mogą służyć do konstruowania zmodyfikowanej tablicy.

Alternatywnie można utworzyć tablicę na podstawie jej rozmiaru przy użyciu `new` słowa kluczowego:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

W obu przypadkach, gdy tablica została skonstruowana, funkcja podstawowa `Length` może służyć do uzyskania liczby elementów jako `Int` .
Tablice można indeksować za pomocą nawiasów kwadratowych, z indeksami dolnymi albo typem `Int` lub typem `Range` , aby uzyskać pojedyncze elementy lub nowe tablice zawierające podzestaw elementów tablicy.
Indeksy dolne tablic są oparte na zero:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Typy krotek

Podaną zero lub kilka różnych typów,,..., `T0` `T1` `Tn` można zauważyć, że nowy *Typ krotki* jest w postaci `(T0, T1, ..., Tn)` .
Typy używane do konstruowania nowego typu krotki mogą sami być krotkami, jak w `(Int, (Qubit, Qubit))` .
Takie zagnieżdżenie jest zawsze ograniczone, jednak ponieważ typy krotek nie mogą znajdować się w żadnych okolicznościach.

Wartości nowego typu krotki są krotkami tworzonymi przez sekwencje wartości z każdego typu w spójnej kolekcji.
Na przykład `(3, false)` jest krotką, której typem jest typ krotki `(Int, Bool)` .
Istnieje możliwość tworzenia tablic spójnych krotek, krotek tablic, krotek podkolekcji itd.

Począwszy od Q # 0,3, `Unit` jest nazwą *typu* pustej krotki; `()` jest używana dla pustej *wartości*krotki.

Wystąpienia krotki są niezmienne.
Usługa Q # nie udostępnia mechanizmu zmiany zawartości spójnej kolekcji po utworzeniu.

Krotki są zaawansowaną koncepcją używaną przez funkcję Q # do zbierania wartości w jednej wartości, co ułatwia ich przekazywanie.
W szczególności, za pomocą notacji spójnej, możemy wyrazić, że każda operacja i możliwy do oddzwonienia przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.

### <a name="singleton-tuple-equivalence"></a>Równoważna krotka singleton

Można utworzyć pojedynczą (jednoelementową) krotkę, `('T1)` taką jak `(5)` lub `([1,2,3])` .
Jednakże Q # traktuje pojedynczą krotkę jako całkowicie równoważną wartości typu zamkniętego.
Oznacza to, że nie ma różnicy między `5` i `(5)` , lub między i i między i `5` `(((5)))` `(5, (6))` `(5, 6)` .
Jest równie ważna do zapisu `(5)+3` jako do zapisu `5+3` , a oba wyrażenia będą oceniane do `8` .

Ta równoważność ma zastosowanie do wszystkich celów, w tym przypisania i wyrażeń.
Uwzględniając dowolne wyrażenie, to samo wyrażenie ujęte w nawiasy jest wyrażeniem tego samego typu.
Na przykład, `(7)` jest wyrażeniem `Int` , `([1,2,3])` jest wyrażeniem typu Array `Int` -s i `((1,2))` jest wyrażeniem typu `(Int, Int)` .

W szczególności oznacza to, że operacja lub funkcja, której kolekcja wejściowa lub typ krotki danych wyjściowych ma jedno pole może być uważane za przyjmujące pojedynczy argument lub zwracającą pojedynczą wartość.

Nazywamy tę właściwość jako _równoważność spójnej kolekcji_.


## <a name="user-defined-types"></a>Typy zdefiniowane przez użytkownika

Deklaracja typu zdefiniowanego przez użytkownika składa się ze słowa kluczowego `newtype` , po którym następuje nazwa typu zdefiniowanego przez użytkownika, elementu `=` , prawidłowej specyfikacji typu i kończącego się średnika.

Przykład:

```qsharp
newtype PairOfInts = (Int, Int);
```

Każdy plik źródłowy Q # może deklarować dowolną liczbę typów zdefiniowanych przez użytkownika.
Nazwy typów muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktów z nazwami operacji i funkcji.

Typy zdefiniowane przez użytkownika są różne, nawet jeśli typy podstawowe są identyczne.
W szczególności nie istnieje Automatyczna konwersja między wartościami dwóch typów zdefiniowanych przez użytkownika, nawet jeśli typy bazowe są identyczne.

### <a name="named-vs-anonymous-items"></a>Elementy nazwane a anonimowe

Plik Q # może definiować nowy nazwany typ zawierający pojedynczą wartość dowolnego typu prawnego.
Dla dowolnego typu krotki `T` można zadeklarować nowy typ zdefiniowany przez użytkownika, który jest podtypem `T` `newtype` instrukcji.
Na @"microsoft.quantum.math" przykład w przestrzeni nazw liczba zespolona jest definiowana jako typ zdefiniowany przez użytkownika:

```qsharp
newtype Complex = (Double, Double);
```
Ta instrukcja tworzy nowy typ z dwoma anonimowymi elementami typu `Double` .   

Poza elementami anonimowymi typy zdefiniowane przez użytkownika obsługują również *nazwane elementy* w przypadku Q # w wersji 0,7 lub nowszej. Na przykład możemy mieć nazwę do elementów `Re` dla podwójnego reprezentowania rzeczywistej części liczby zespolonej i `Im` dla części urojonej: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Nazewnictwo jednego elementu w typie zdefiniowanym przez użytkownika nie oznacza, że wszystkie elementy muszą mieć nazwę, a także obsługiwane są dowolne kombinacje elementów nazwanych i nienazwanych. Ponadto elementy wewnętrzne mogą być również nazwane.
Typ, `Nested` zgodnie z definicją poniżej, ma typ podstawowy `(Double, (Int, String))` , którego tylko element typu `Int` ma nazwę i wszystkie pozostałe elementy są anonimowe. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Elementy nazwane mają zalety, do których można uzyskiwać dostęp bezpośrednio za pośrednictwem *operatora dostępu* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Oprócz udostępniania krótkich aliasów dla potencjalnie skomplikowanych typów krotek, jedną istotną zaletą zdefiniowania takich typów jest możliwość udokumentowania zamiaru określonej wartości.
Powracanie do przykładu `Complex` , może być również zdefiniowane współrzędne bieguna 2D jako typ zdefiniowany przez użytkownika:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Mimo że oba `Complex` i `Polar` oba mają typ podstawowy `(Double, Double)` , dwa typy są całkowicie niezgodne z Q #, minimalizując ryzyko przypadkowego wywołania złożonej funkcji matematycznej ze współrzędnymi biegunowymi i odwrotnie.
W ten sposób zdefiniowane przez użytkownika typy mają podobną rolę jako rekordy w języku F #. 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Dostęp do anonimowych elementów za pomocą operatora rozwinięcia

Aby można było uzyskać dostęp do anonimowych elementów z drugiej strony, najpierw musi zostać wyodrębniona wartość opakowana przy użyciu operatora przyrostkowego `!` .
Operator "unotocz" `!` umożliwia wyodrębnienie wartości zawartej w typie zdefiniowanym przez użytkownika.
Typ takiego wyrażenia "unotoka" jest typem podstawowym typu zdefiniowanego przez użytkownika. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Operator rozwinięcia odpakuje dokładnie jedną warstwę zawijania.
Wielokrotne operatory odwinięcia mogą być używane w celu uzyskania dostępu do wartości przepakowanej wielokrotnie.

Przykład:

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

Więcej szczegółów dotyczących operatora odpakowania można znaleźć w [wyrażeniach typu w Q #](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Tworzenie wartości typów zdefiniowanych przez użytkownika

Wartości typu zdefiniowanego przez użytkownika można utworzyć, wywołując odpowiedni Konstruktor typów:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Alternatywnie nowe wartości można tworzyć z istniejących przy użyciu [wyrażeń Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Podobnie jak w przypadku tablic, takie wyrażenia kopiują wszystkie wartości elementu oryginalnego wyrażenia, z wyjątkiem określonych nazwanych elementów. Dla tych wartości są ustawiane na te, które zostały zdefiniowane po prawej stronie wyrażenia. Wszystkie inne konstrukcje języka, takie jak przykładowe [instrukcje Update-and-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), które są dostępne dla elementów tablicy istnieje dla elementów nazwanych w typach zdefiniowanych przez użytkownika.

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

Typy zdefiniowane przez użytkownika mogą być używane wszędzie tam, gdzie można korzystać z dowolnego innego typu.
W szczególności można zdefiniować tablicę typu zdefiniowanego przez użytkownika i dołączenia typu zdefiniowanego przez użytkownika jako elementu typu krotki.

Uwaga nie można utworzyć struktur typów cyklicznych.
Oznacza to, że typ definiujący typ zdefiniowany przez użytkownika nie może być typem krotki, który zawiera element typu zdefiniowanego przez użytkownika.
Ogólnie rzecz biorąc, typy zdefiniowane przez użytkownika mogą nie zawierać cyklicznych zależności od siebie, więc następujący zestaw definicji typu byłby niedozwolony:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>Typy operacji i funkcji

Typ podstawowy dla każdego elementu, który można wywołać, jest zapisywana jako `('Tinput => 'Tresult)` lub `('Tinput -> 'Tresult)` , gdzie oba `'Tinput` i `'Tresult` są typami.
Są one nazywane *sygnaturą* wywołania.

Wszystkie wywoływane wartości Q # są traktowane jako dane wejściowe i zwracają pojedynczą wartość jako dane wyjściowe.
Zarówno wartość wejściowa, jak i wyjściowa mogą być krotki.
Możliwe do zwrócenia, które nie zwracają wyniku `Unit` .
Możliwe do nadania, że żadne dane wejściowe nie przyjmują pustej kolekcji jako dane wejściowe.

> [!NOTE]
> Pierwszy formularz, z `=>` , jest używany do operacji; drugi formularz, z `->` , dla usługi Functions.
> Na przykład `((Qubit, Pauli) => Result)` reprezentuje podpis dla możliwej operacji pomiaru pojedynczej qubit.
Typy *funkcji* są w pełni określone przez ich sygnaturę.
Na przykład funkcja, która oblicza sinus kąta, będzie miała typ `(Double -> Double)` .

*Operacje*---, ale nie funkcje---mają pewne dodatkowe cechy, które są wyrażane jako część typu operacji. Takie charakterystyki zawierają informacje o tym, co *funktory* operacja obsługuje.
Na przykład, jeśli wykonanie operacji może być kondycjonowane na stanie innych qubits, powinien obsługiwać `Controlled` Funktor; Jeśli operacja ma odwrotność, powinien obsługiwać `Adjoint` Funktor. Funktory i operacje są szczegółowo omówione w temacie [Operations and Functions in Q #](xref:microsoft.quantum.guide.operationsfunctions), ale po prostu omawiamy, jak to zmienia sygnaturę operacji.

Aby wymagać obsługi dla `Controlled` i/lub `Adjoint` Funktor w typie operacji, musimy dodać adnotację wskazującą odpowiednie cechy.
Adnotacja `is Ctl` (np. `(Qubit => Unit is Ctl)` ) wskazuje, że operacja jest sterowana---, co oznacza, że jest wykonywana na stanie innego qubit lub qubits. Podobnie, `is Adj` oznacza to, że operacja ma sąsiadujące; lub po prostu może być "odwrócona", co oznacza, że po zastosowaniu operacji, a następnie jej przyłączenie do stanu pozostawia stan bez zmian. 

Jeśli chcemy wymagać, aby operacja tego typu obsługiwała zarówno `Adjoint` i Funktor, `Controlled` jak to możliwe `(Qubit => Unit is Adj + Ctl)` . Na przykład wbudowana <xref:microsoft.quantum.intrinsic.x> operacja Pauli ma typ `(Qubit => Unit is Adj + Ctl)` . 

Typ operacji, która nie obsługuje żadnej funktory, jest określany za pomocą samego typu danych wejściowych i wyjściowych, bez dodatkowej adnotacji.

### <a name="type-parameterized-functions-and-operations"></a>Funkcje i operacje sparametryzowane typu

Możliwe do napisania typy mogą zawierać parametry typu.
Parametry typu są wskazywane przez symbol poprzedzony pojedynczym cudzysłowem; na przykład `'A` jest parametrem typu prawnego.
Szczegóły dotyczące definiowania parametrów z parametrami, które są wywoływane, są dostępne na stronie [operacje i funkcje w polu Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) .

Parametr typu może pojawić się więcej niż raz w pojedynczym podpisie.
Na przykład funkcja, która stosuje inną funkcję do każdego elementu tablicy i zwraca zebrane wyniki byłyby sygnaturą `(('A[], 'A->'A) -> 'A[])` .
Podobnie funkcja, która zwraca skład dwóch operacji, może mieć sygnaturę `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

W przypadku wywołania sparametryzowanego typu, wszystkie argumenty, które mają ten sam parametr typu, muszą być tego samego typu.

Funkcja Q # nie udostępnia mechanizmu ograniczenia możliwych typów, które mogą zostać zastąpione dla parametru typu.

## <a name="whats-next"></a>Co dalej?
Teraz, gdy wykorzystano wszystkie typy, które składają się na język Q #, można umieścić [wyrażenia w polu q #](xref:microsoft.quantum.guide.expressions) , aby zobaczyć, jak tworzyć i manipulować wyrażeniami różnych typów.



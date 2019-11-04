---
title: 'Typ modelu Q # | Microsoft Docs'
description: 'Model typu Q #'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184750"
---
# <a name="the-type-model"></a>Model typu

W tej sekcji przedstawiono model typu Q # i opisano składnię służącą do określania typów i pracy z typami.
Należy pamiętać, że funkcja Q # jest językiem o *jednoznacznie określonym* typie, w taki sposób, że dokładne użycie tych typów może pomóc kompilatorowi zapewnić silne gwarancje dotyczące programów Q # w czasie kompilacji.

Aby zapewnić najwyższy możliwy poziom gwarancji, konwersje między typami w Q # muszą być jawne przy użyciu wywołań do funkcji, które wyrażają konwersję. Różne takie funkcje są dostępne jako część przestrzeni nazw <xref:microsoft.quantum.convert>.
Rzutowanie na zgodne typy z drugiej strony odbywa się niejawnie. 

Polecenie Q # zapewnia typy pierwotne, które mogą być używane bezpośrednio, i różne sposoby tworzenia nowych typów z innych typów.
Opiszemy każdą z nich w pozostałej części tej sekcji.

## <a name="primitive-types"></a>Typy pierwotne

Język Q # zawiera kilka *typów pierwotnych*, z których można utworzyć inne typy:

- Typ `Int` reprezentuje 64-bitową liczbę całkowitą ze znakiem, np.: `2`, `107``-5`.
- Typ `BigInt` reprezentuje podpisaną liczbę całkowitą o dowolnym rozmiarze, np. `2L`, `107L``-5L`.
   Ten typ jest oparty na <xref:System.Numerics.BigInteger> .NET
   Wprowadź.
- Typ `Double` reprezentuje liczbę zmiennoprzecinkową o podwójnej precyzji, np.: `0.0`, `-1.3``4e-7`.
- Typ `Bool` reprezentuje wartość logiczną, która może być `true` lub `false`.
- Typ `Qubit` reprezentuje bit Quantum lub qubit.
   `Qubit`s są nieprzezroczyste dla użytkownika; Jedyną operacją dopuszczalną dla nich, inną niż przekazanie jej do innej operacji, jest przetestowanie pod kątem tożsamości (równość).
   W rezultacie akcje na `Qubit`s są implementowane przez wywoływanie instrukcji wewnętrznych na procesorze Quantum (lub w jego symulacji).
- Typ `Pauli` reprezentuje jeden z czterech operatorów Pauli (Single-qubit).
   Ten typ służy do oznaczania operacji podstawowej dla rotacji i do określenia zauważalnego pomiaru.
   Jest to typ wyliczeniowy, który ma cztery możliwe wartości: `PauliI`, `PauliX`, `PauliY`i `PauliZ`, które są stałymi typu `Pauli`.
- Typ `Result` reprezentuje wynik pomiaru.
   Jest to typ wyliczeniowy z dwoma możliwymi wartościami: `One` i `Zero`, które są stałymi typu `Result`.
   `Zero` wskazuje, że eigenvalue + 1 została zmierzona; `One` wskazuje-1 eigenvalue.
- Typ `Range` reprezentuje sekwencję liczb całkowitych, która jest oznaczona przez `start..step..stop`, gdzie oznacza to, że jest to opcja. 
   `start .. stop` odpowiada `start..1..stop`, a na przykład `1..2..7` reprezentuje sekwencję $\{1, 3, 5, 7\}$.
- Typ `String` jest sekwencją znaków Unicode, które są nieprzezroczyste dla użytkownika po utworzeniu.
  Ten typ służy do zgłaszania komunikatów do klasycznego hosta w przypadku błędu lub zdarzenia diagnostycznego.
- Typ `Unit` jest typem, który dopuszcza tylko jedną wartość `()`. 
  Ten typ jest używany do wskazania, że funkcja Q # lub operacja nie zwraca żadnych informacji. 

Stałe `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`i `Zero` są zastrzeżonymi symbolami w Q #.

## <a name="array-types"></a>Typy tablic

Uwzględniając dowolny prawidłowy typ Q # `'T`, istnieje typ, który reprezentuje tablicę wartości typu `'T`.
Ten typ tablicy jest reprezentowany jako `'T[]`; na przykład `Qubit[]` lub `Int[][]`.
Na przykład kolekcja liczb całkowitych jest oznaczona `Int[]`, podczas gdy tablica tablic `(Bool, Pauli)` wartości jest oznaczona jako `(Bool, Pauli)[][]`.

W drugim przykładzie należy zauważyć, że reprezentuje to potencjalnie nieregularną tablicę tablic, a nie prostokątną dwuwymiarową tablicę.
Usługa Q # nie zapewnia obsługi prostokątnych tablic wielowymiarowych.

Wartość tablicy można napisać w kodzie źródłowym Q # przy użyciu nawiasów kwadratowych wokół elementów tablicy, jak w `[PauliI, PauliX, PauliY, PauliZ]`.
Typ literału tablicy jest określany przez wspólny typ podstawowy wszystkich elementów w tablicy. 

> [!WARNING]
> Elementy tablicy nie mogą być zmieniane po utworzeniu tablicy.
> Instrukcje Update-and-Reassign i/lub wyrażenia Copy-and-Update mogą służyć do konstruowania zmodyfikowanej tablicy.

Alternatywnie można utworzyć tablicę na podstawie jej rozmiaru przy użyciu słowa kluczowego `new`:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

W obu przypadkach, gdy macierz została skonstruowana, funkcja podstawowa `Length` może służyć do uzyskania liczby elementów jako `Int`.
Tablice można indeksować za pomocą nawiasów kwadratowych, ze indeksami dolnymi lub typem `Int` lub `Range`, aby uzyskać pojedyncze elementy lub nowe tablice zawierające podzestaw elementów tablicy.
Indeksy dolne tablic są oparte na zero:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Typy krotek

Nadawane zero lub więcej różnych typów `T0`, `T1`,..., `Tn`, możemy zauważyć nowy *Typ krotki* jako `(T0, T1, ..., Tn)`.
Typy używane do konstruowania nowego typu krotki mogą być krotkami, jak w `(Int, (Qubit, Qubit))`.
Takie zagnieżdżenie jest zawsze ograniczone, jednak ponieważ typy krotek nie mogą znajdować się w żadnych okolicznościach.

Wartości nowego typu krotki są krotkami tworzonymi przez sekwencje wartości z każdego typu w spójnej kolekcji.
Na przykład `(3, false)` jest krotką, której typem jest typ krotki `(Int, Bool)`.
Istnieje możliwość tworzenia tablic spójnych krotek, krotek tablic, krotek podkolekcji itd.

Począwszy od Q # 0,3, `Unit` jest nazwą *typu* pustej krotki; `()` jest używany dla pustej *wartości*krotki.

Wystąpienia krotki są niezmienne.
Usługa Q # nie udostępnia mechanizmu zmiany zawartości spójnej kolekcji po utworzeniu.

Krotki są zaawansowaną koncepcją używaną przez funkcję Q # do zbierania wartości w jednej wartości, co ułatwia ich przekazywanie.
W szczególności, za pomocą notacji spójnej, możemy wyrazić, że każda operacja i możliwy do oddzwonienia przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.

### <a name="singleton-tuple-equivalence"></a>Równoważna krotka singleton

Istnieje możliwość utworzenia pojedynczego (pojedynczego elementu) krotki, `('T1)`, takiej jak `(5)` lub `([1,2,3])`.
Jednakże Q # traktuje pojedynczą krotkę jako całkowicie równoważną wartości typu zamkniętego.
Oznacza to, że nie ma różnicy między `5` i `(5)`, lub między `5` i `(((5)))`lub między `(5, (6))` i `(5, 6)`.

Ta równoważność ma zastosowanie do wszystkich celów, w tym przypisania i wyrażeń.
Jest tak samo ważne, aby można było pisać `(5)+3` jak do zapisu `5+3`, a oba wyrażenia będą oceniane do `8`.
W szczególności oznacza to, że operacja lub funkcja, której kolekcja wejściowa lub typ krotki danych wyjściowych ma jedno pole może być uważane za przyjmujące pojedynczy argument lub zwracającą pojedynczą wartość.

Nazywamy tę właściwość jako _równoważność spójnej kolekcji_.

## <a name="user-defined-types"></a>Typy zdefiniowane przez użytkownika

Plik Q # może definiować nowy nazwany typ zawierający pojedynczą wartość dowolnego typu prawnego.
Dla dowolnego typu krotki `T`można zadeklarować nowy typ zdefiniowany przez użytkownika, który jest podtypem `T` za pomocą instrukcji `newtype`.
W przestrzeni nazw @"microsoft.quantum.canon", na przykład liczba zespolona jest definiowana jako typ zdefiniowany przez użytkownika:

```qsharp
newtype Complex = (Double, Double);
```

Ta instrukcja tworzy nowy typ z dwoma anonimowymi elementami typu `Double`.   
Poza elementami anonimowymi typy zdefiniowane przez użytkownika obsługują również nazwane elementy w przypadku Q # w wersji 0,7 lub nowszej. Można na przykład nazwać elementy do `Re` dla podwójnego reprezentowania rzeczywistej części liczby zespolonej i `Im` dla części urojonej: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Nazewnictwo jednego elementu w typie zdefiniowanym przez użytkownika nie oznacza, że wszystkie elementy muszą mieć nazwę, a także jest obsługiwana żadna kombinacja elementów nazwanych i nienazwanych. Ponadto elementy wewnętrzne mogą być nazywane.
Typ `Nested`, jak zdefiniowano poniżej, ma `(Double, (Int, String))`typ podstawowy, dla którego tylko element typu `Int` ma nazwę i wszystkie pozostałe elementy są anonimowe. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
Elementy nazwane mają zalety, do których można uzyskiwać dostęp bezpośrednio za pośrednictwem operatora dostępu `::`. 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Aby można było uzyskać dostęp do anonimowych elementów z drugiej strony, najpierw musi zostać wyodrębniona wartość opakowana przy użyciu operatora przyrostkowego `!`.
Operator "unotocz" `!`, umożliwia wyodrębnienie wartości zawartej w typie zdefiniowanym przez użytkownika.
Typ takiego wyrażenia "unotoka" jest typem podstawowym typu zdefiniowanego przez użytkownika. 

```qsharp
function PrintMsg (value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Operator rozwinięcia odpakuje dokładnie jedną warstwę zawijania.
Wielokrotne operatory odwinięcia mogą być używane w celu uzyskania dostępu do wartości przepakowanej wielokrotnie.

Na wystąpienie:

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

Aby uzyskać więcej informacji, zapoznaj się z sekcją dotyczącą [niezawijania wyrażeń](xref:microsoft.quantum.language.expressions#unwrap-expressions) i [operatorów](xref:microsoft.quantum.language.expressions#operator-precedence) .

Wartości typu zdefiniowanego przez użytkownika można utworzyć, wywołując odpowiedni Konstruktor typów:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Alternatywnie nowe wartości można tworzyć z istniejących przy użyciu [wyrażeń Copy-and-Update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions). Podobnie jak w przypadku tablic, takie wyrażenia kopiują wszystkie wartości elementu oryginalnego wyrażenia, z wyjątkiem określonych nazwanych elementów. Dla tych wartości są ustawiane na te, które zostały zdefiniowane po prawej stronie wyrażenia. Wszystkie inne konstrukcje języka, takie jak przykładowe [instrukcje Update-and-Reassign](xref:microsoft.quantum.language.statements#update-and-reassign-statement), które są dostępne dla elementów tablicy istnieje dla elementów nazwanych w typach zdefiniowanych przez użytkownika.

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

Nie można tworzyć struktur typów cyklicznych.
Oznacza to, że typ definiujący typ zdefiniowany przez użytkownika nie może być typem krotki, który zawiera element typu zdefiniowanego przez użytkownika.
Ogólnie rzecz biorąc, typy zdefiniowane przez użytkownika mogą nie zawierać cyklicznych zależności od siebie, więc następujący zestaw definicji typu byłby niedozwolony:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

Oprócz udostępniania krótkich aliasów dla potencjalnie skomplikowanych typów krotek, jedną istotną zaletą zdefiniowania takich typów jest możliwość udokumentowania zamiaru określonej wartości.
Powracanie do przykładu `Complex`może mieć również zdefiniowane współrzędne bieguna 2D jako typ zdefiniowany przez użytkownika:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Mimo że oba `Complex` i `Polar` mają typ podstawowy `(Double, Double)`, dwa typy są w pełni niezgodne z Q #, minimalizując ryzyko przypadkowego wywołania złożonej funkcji matematycznej ze współrzędnymi biegunowymi i odwrotnie.
W ten sposób zdefiniowane przez użytkownika typy mają podobną rolę jako rekordy F# na przykład. 


## <a name="operation-and-function-types"></a>Typy operacji i funkcji

_Operacja_ Q # jest podprocedurą Quantum.
Oznacza to, że jest to procedura, która zawiera operacje Quantum.

_Funkcja_ Q # to klasyczna procedura użyta w algorytmie Quantum.
Może zawierać kod klasyczny, ale nie ma operacji Quantum.
W przeciwnym razie funkcje nie mogą przydzielić ani zażyczyć qubits ani nie mogą wywoływać operacji.
Można jednak przekazać im operacje lub qubits do przetwarzania.
Funkcje są więc całkowicie deterministyczne w sensie, że wywołanie ich przy użyciu tych samych argumentów zawsze da ten sam wynik. 

Razem operacje i funkcje _są wywoływane._  Poniżej znajdują się [przykłady](#examples) poniżej.

Wszystkie wywoływane wartości Q # są traktowane jako dane wejściowe i zwracają pojedynczą wartość jako dane wyjściowe.
Zarówno wartość wejściowa, jak i wyjściowa mogą być krotki.
Liczba wywoływanych, które nie mają zwracanych wyników `Unit`.
Możliwe do nadania, że żadne dane wejściowe nie przyjmują pustej kolekcji jako dane wejściowe.

Typ podstawowy dla każdego elementu, który można wywołać, jest zapisywana jako `('Tinput => 'Tresult)` lub `('Tinput -> 'Tresult)`, gdzie zarówno `'Tinput`, jak i `'Tresult` są typami.
Pierwszy formularz z `=>`jest używany do operacji; Drugi formularz z `->`dla funkcji.
Na przykład `((Qubit, Pauli) => Result)` reprezentuje sygnaturę dla możliwej operacji pomiaru pojedynczej qubit.

Typy funkcji są w pełni określone przez ich sygnaturę.
Na przykład funkcja, która oblicza sinus kąta, będzie miała typ `(Double -> Double)`.

Operacje — ale nie funkcje — mają pewne dodatkowe _cechy_ , które są wyrażane jako część typu operacji. Takie charakterystyki zawierają informacje o tym, co funktory operacja obsługuje.
Funktory są operacjami, które generują specjalizację operacji podstawowej; Zobacz [funktory](#functors), poniżej.

Typy operacji są określane przez ich typ danych wejściowych, typ danych wyjściowych i ich cechy.    
Aby wymagać pomocy technicznej dla `Controlled` i/lub `Adjoint` Funktor w typie operacji, musimy dodać adnotację wskazującą odpowiednie cechy.
Adnotacja `is Ctl` na przykład wskazuje, że operacja jest sterowana. Jeśli chcemy wymagać, aby operacja tego typu obsługiwała zarówno `Adjoint`, jak i `Controlled` Funktor, możemy to zrobić jako `(Qubit => Unit is Adj + Ctl)`. Charakterystyki używanej operacji `Adj` i `Ctl` ściśle wymawiają dwa wstępnie zdefiniowane zestawy etykiet, gdzie każda etykieta wskazuje konkretne właściwości operacji, takie jak np. Pomoc techniczna dla określonego Funktor.
W związku z tym `+` jest używany do wskazania Unii tych dwóch zestawów, a `*` jest używany do wskazania przedziału, tj. etykiet wspólnych dla obu zestawów.  

Na przykład operacja Pauli `X` ma typ `(Qubit => Unit is Adj + Ctl)`.
Typ operacji, która nie obsługuje żadnej funktory, jest określany za pomocą samego typu danych wejściowych i wyjściowych, bez dodatkowej adnotacji.


### <a name="type-parameterized-functions-and-operations"></a>Funkcje i operacje sparametryzowane typu

Możliwe do napisania typy mogą zawierać parametry typu.
Parametry typu są wskazywane przez symbol poprzedzony pojedynczym cudzysłowem; na przykład `'A` jest dozwolonym parametrem typu.

Parametr typu może pojawić się więcej niż raz w pojedynczym podpisie.
Na przykład funkcja, która stosuje inną funkcję do każdego elementu tablicy i zwraca zebrane wyniki, ma `(('A[], 'A->'A) -> 'A[])`sygnatur.
Podobnie funkcja, która zwraca skład dwóch operacji, może mieć sygnaturę `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.

W przypadku wywołania sparametryzowanego typu, wszystkie argumenty, które mają ten sam parametr typu, muszą być tego samego typu.

Funkcja Q # nie udostępnia mechanizmu ograniczenia możliwych typów, które mogą zostać zastąpione dla parametru typu.

### <a name="type-compatibility"></a>Zgodność typów

Operacja z dodatkowymi obsługiwanymi funktory może być używana wszędzie tam, gdzie operacja jest mniejsza niż funktory, ale oczekiwano tego samego podpisu.
Na przykład operacja typu `(Qubit => Unit is Adj)` może być używana wszędzie tam, gdzie jest oczekiwana operacja typu `(Qubit => Unit)`.

Q # jest współwariantem w odniesieniu do możliwego do zwrócenia typu zwracanego: wywoływany, który zwraca typ `'A` jest zgodny z tym samym typem danych wejściowych i typem wyniku, który `'A` jest zgodny z.

Q # jest kontrawariantne w odniesieniu do typów danych wejściowych: wywoływanie, który przyjmuje typ `'A` jako dane wejściowe jest zgodny z wywoływanym z tym samym typem wyniku i typem danych wejściowych zgodnym z `'A`.

Oznacza to, że podano następujące definicje:

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

spełnione są następujące kwestie:

- `ConjugateInvertibleWith` operacji może być wywołana z argumentem `inner` `Invertible` lub `Unitary`.
- `ConjugateUnitaryWith` operacji może być wywołana z argumentem `inner` `Unitary`, ale nie `Invertible`.
- Wartość typu `(Qubit[] => Unit is Adj + Ctl)` może być zwracana z `ConjugateInvertibleWith`.

> [!IMPORTANT]
> Q # 0,3 wprowadza znaczącą różnicę w zachowaniu typów zdefiniowanych przez użytkownika.

Typy zdefiniowane przez użytkownika są traktowane jako opakowana wersja typu podstawowego, a nie jako podtyp.
Oznacza to, że wartość typu zdefiniowanego przez użytkownika nie jest użyteczna, gdy oczekiwana jest wartość typu podstawowego.

### <a name="functors"></a>Funktory

Funktor w Q # to fabryka, która definiuje nową operację z innej operacji.
Funktory mają dostęp do implementacji operacji podstawowej podczas definiowania implementacji nowej operacji.
W ten sposób funktory może wykonywać bardziej złożone funkcje niż tradycyjne funkcje wyższego poziomu.

Funktory nie ma reprezentacji w systemie typu Q #. Obecnie nie można powiązać ich ze zmienną lub przekazać ich jako argumenty. 

Funktor jest używany przez zastosowanie go do operacji, zwracając nową operację.
Na przykład operacja będąca wynikiem zastosowania `Adjoint` Funktor do operacji `Y` jest zapisywana jako `Adjoint Y`.
Nowa operacja może następnie zostać wywołana jak każda inna operacja.
W tym celu `Adjoint Y(q1)` stosuje Funktor sąsiadujący do operacji `Y` w celu wygenerowania nowej operacji i stosuje tę nową operację do `q1`.

Podobnie `Controlled X(controls, target)` ma zastosowanie kontrolowane Funktor do operacji `X` w celu wygenerowania nowej operacji i stosuje tę nową operację do `controls` i `target`.

Dwa standardowe funktory w Q # są `Adjoint` i `Controlled`.

#### <a name="adjoint"></a>Sąsiadująco

W przypadku przetwarzania Quantum, sąsiadująca operacja jest złożona sprzężona operacja.
W przypadku operacji implementujących operator jednostki sąsiednie jest odwrotność operacji.
W przypadku prostej operacji, która po prostu wywołuje sekwencję innych operacji jednostkowych na zestawie qubits, sąsiadujący może być obliczany przez zastosowanie adjoints podrzędnych operacji w tym samym qubits, w odwrotnej sekwencji.

Po otrzymaniu wyrażenia operacji nowe wyrażenie operacji może być utworzone przy użyciu `Adjoint` Funktor.
Na przykład `Adjoint QFT` wyznacza sąsiadujący operacji `QFT`.
Nowa operacja ma ten sam podpis i typ co operacja podstawowa.
W szczególności Nowa operacja umożliwia również `Adjoint`i zezwala na `Controlled`, jeśli i tylko wtedy, gdy operacja podstawowa zakończyła się.

Sąsiadujący Funktor jest własnym odwrotnością; oznacza to, że `Adjoint Adjoint Op` jest zawsze taka sama jak `Op`.

#### <a name="controlled"></a>Kontrolowane

Kontrolowana wersja operacji jest nową operacją, która efektywnie stosuje operację podstawową tylko wtedy, gdy wszystkie kontrolki qubits są w określonym stanie.
Jeśli kontrolka qubits znajduje się w położeniu, wówczas podstawowa operacja jest stosowana spójnie z odpowiednią częścią położenia.
W ten sposób kontrolowane operacje są często używane do generowania Entanglement.

W programie Q # kontrolowane wersje zawsze pobierają tablicę qubits kontroli, a określony stan jest zawsze przeznaczony dla wszystkich kontrolek qubits, które mają być w stanie `One` obliczeniowym (`PauliZ`), $ \ket{1}$.
Kontrolę w oparciu o inne Stany można osiągnąć przez zastosowanie odpowiedniej operacji jednostkowej do kontrolki qubits przed operacją kontrolowanej, a następnie zastosowanie odwrotności operacji jednostkowej po kontrolowanej operacji.
Na przykład zastosowanie operacji `X` do kontrolki qubit przed i po kontrolowanej operacji spowoduje, że operacja kontroluje stan `Zero` ($ \ket{0}$) dla tego qubit; zastosowanie `H` operacji przed i po nim będzie kontrolować stan `One` `PauliX`, czyli-1 eigenvalue Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$, a nie `PauliZ` `One`.

Po otrzymaniu wyrażenia operacji nowe wyrażenie operacji może być utworzone przy użyciu `Controlled` Funktor.
Sygnatura nowej operacji jest oparta na podpisie oryginalnej operacji.
Typ wyniku jest taki sam, ale typ danych wejściowych jest krotką dwukrotną z tablicą qubit, która przechowuje qubit kontrolki jako pierwszy element i argumenty oryginalnej operacji jako drugi element.
Nowa operacja obsługuje `Controlled`i będzie obsługiwać `Adjoint`, jeśli i tylko wtedy, gdy oryginalna operacja zakończyła się.

Jeśli oryginalna Operacja trwała tylko z pojedynczym argumentem, w tym miejscu będzie można odtwarzać pojedynczej korelacji krotek.
Na przykład `Controlled X` jest kontrolowana wersja operacji `X`.
`X` ma `(Qubit => Unit is Adj + Ctl)`typu, dlatego `Controlled X` ma `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`typu; ze względu na równoważność spójnej kolekcji jest taka sama jak `((Qubit[], Qubit) => Unit is Adj + Ctl)`.

Jeśli operacja podstawowa wymagała kilku argumentów, pamiętaj, aby ująć odpowiednie argumenty kontrolowanej wersji operacji w nawiasach, aby przekonwertować je na krotkę.
Na przykład `Controlled Rz` jest kontrolowana wersja operacji `Rz`.
`Rz` ma `((Double, Qubit) => Unit is Adj + Ctl)`typu, dlatego `Controlled Rz` ma `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`typu.
W tym celu `Controlled Rz(controls, (0.1, target))` być prawidłowym wywołaniem `Controlled Rz` (należy zauważyć nawiasy wokół `0.1, target`).

Innym przykładem `CNOT(control, target)` można zaimplementować jako `Controlled X([control], target)`. Jeśli element docelowy powinien być kontrolowany przez 2 Control qubits (CCNOT), możemy użyć instrukcji `Controlled X([control1, control2], target)`.

### <a name="examples"></a>Przykłady

Ten przykład operacji Q # pochodzi z próbki [pomiarowej](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) . W ramach operacji można przydzielić qubits i używać operacji Quantum na tych qubits, takich jak `H` i `X`:

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit

            set result = M(qubit);      // Measure the qubit

            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

Ten przykład funkcji pochodzi z przykładu [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) . Zawiera czysto klasyczny kod. Zobaczysz, że w przeciwieństwie do powyższego przykładu nie przydzielono żadnych qubits i nie są używane żadne operacje Quantum.


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

Jest również możliwe, aby funkcja przekazała qubits do przetwarzania, jak w tym przykładzie z przykładu [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) . Qubits są przenoszone do funkcji i używane do przetwarzania, chociaż w żadnym momencie nie są modyfikowane qubit.

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```

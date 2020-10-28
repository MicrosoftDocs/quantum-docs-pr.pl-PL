---
title: Typy w Q#
description: Dowiedz się więcej na temat różnych typów używanych w Q# języku programowania.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: 349138984387cc564cca18ea09c7bf161524b0b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691616"
---
# <a name="types-in-no-locq"></a>Typy w Q#

W tym artykule opisano Q# model typu i składnię służącą do określania typów i pracy z tymi typami. Aby uzyskać szczegółowe informacje na temat sposobu tworzenia i obsługi wyrażeń tych typów, zobacz [wyrażenia typu](xref:microsoft.quantum.guide.expressions).

Należy pamiętać, że Q# jest *strongly-typed* to wulgarny język, w taki sposób, że staranne korzystanie z tych typów może pomóc kompilatorowi zapewnić silne gwarancje dotyczące Q# programów w czasie kompilacji.
Aby zapewnić najmocniejsze gwarancje, konwersje między typami w Q# muszą być jawne przy użyciu wywołań do funkcji, które wyrażają tę konwersję. 
Q# oferuje różne funkcje, które są częścią <xref:Microsoft.Quantum.Convert> przestrzeni nazw.
Przerzuty do zgodnych typów, z drugiej strony, nastąpią niejawnie. 

Q# zawiera typy pierwotne, które są używane bezpośrednio, i różne sposoby tworzenia nowych typów z innych typów.
Opiszemy każdą z nich w dalszej części tego artykułu.

## <a name="primitive-types"></a>Typy pierwotne

Q#Język zawiera następujące *typy pierwotne* , z których można korzystać bezpośrednio w Q# programach. Można również użyć tych typów pierwotnych do konstruowania nowych typów.

- `Int`Typ reprezentuje 64-bitową liczbę całkowitą ze znakiem, na przykład,, `2` `107` `-5` .
- `BigInt`Typ reprezentuje podpisaną liczbę całkowitą z dowolnego rozmiaru, na przykład, `2L` , `107L` `-5L` .
   Ten typ jest oparty na platformie .NET <xref:System.Numerics.BigInteger>
   Wprowadź.

- `Double`Typ reprezentuje liczbę zmiennoprzecinkową o podwójnej precyzji, na przykład,, `0.0` `-1.3` `4e-7` .
- `Bool`Typ reprezentuje wartość logiczną albo `true` lub `false` .
- `Range`Typ reprezentuje sekwencję liczb całkowitych, oznaczaną przez `start..step..stop` , gdzie oznacza to, że ten krok jest opcjonalny. 
   Na przykład `start .. stop` odpowiada `start..1..stop` , i `1..2..7` reprezentuje sekwencję $ \{ 1, 3, 5, 7 \} $.
- `String`Typ jest sekwencją znaków Unicode, które są nieprzezroczyste dla użytkownika po utworzeniu.
  Użyj `string` typu, aby zgłosić komunikaty do klasycznego hosta w przypadku błędu lub zdarzenia diagnostycznego.
- `Unit`Typ może mieć tylko jedną wartość, `()` . 
  Użyj tego typu, aby wskazać, że Q# Funkcja lub operacja nie zwraca żadnych informacji. 
- `Qubit`Typ reprezentuje bit Quantum lub qubit.
   `Qubit`s nie jest nieprzezroczysty dla użytkownika. Jedyną operacją dopuszczalną dla nich, inną niż przekazanie jej do innej operacji, jest przetestowanie pod kątem tożsamości (równość).
   Ostatecznie wdrażasz akcje na `Qubit` s, wywołując instrukcje wewnętrzne na procesorach Quantum (lub w symulatorze Quantum).
- `Pauli`Typ reprezentuje jeden z czterech operatorów Pauli pojedynczej qubit.
   Użyj tego typu, aby zauważyć podstawową operację dla rotacji i określić zauważalny pomiar.
   Jest to typ wyliczeniowy, który ma cztery możliwe wartości: `PauliI` , `PauliX` , `PauliY` , i `PauliZ` , które są stałymi typu `Pauli` .
- `Result`Typ reprezentuje wynik pomiaru.
   Jest to typ wyliczeniowy z dwoma możliwymi wartościami: `One` i `Zero` , które są stałymi typu `Result` .
   `Zero` wskazuje, że eigenvalue + 1 została zmierzona; `One` wskazuje, że eigenvalue — 1.

Stałe,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` i `Zero` są zastrzeżonymi symbolami w Q# .

## <a name="array-types"></a>Typy tablic

* Dla dowolnego prawidłowego Q# typu istnieje typ, który reprezentuje tablicę wartości tego typu.
    Na przykład `Qubit[]` i `(Bool, Pauli)[]` reprezentuje tablice `Qubit` wartości i `(Bool, Pauli)` wartości krotek.

* Tablica tablic jest również prawidłowa. Rozszerzanie w poprzednim przykładzie, tablica `(Bool, Pauli)` tablic jest oznaczona `(Bool, Pauli)[][]` .

> [!NOTE] 
> Ten przykład, `(Bool, Pauli)[][]` , reprezentuje potencjalnie nieregularną tablicę tablic, a nie prostokątną dwuwymiarową tablicę. Q# nie obsługuje prostokątnych tablic wielowymiarowych.

* Wartość tablicy może być zapisywana w Q# kodzie źródłowym przy użyciu nawiasów kwadratowych wokół elementów tablicy, jak w `[PauliI, PauliX, PauliY, PauliZ]` .
Wspólny typ podstawowy wszystkich elementów w tablicy określa typ literału tablicy. W związku z tym konstruowanie tablicy z elementami, które nie mają wspólnego typu podstawowego, zgłasza błąd.  
Aby zapoznać się z przykładem, zobacz [tablice o możliwych wartościach](xref:microsoft.quantum.guide.expressions#arrays-of-callables).

    > [!WARNING]
    > Po utworzeniu elementy tablicy nie mogą być zmieniane.
    > Aby utworzyć zmodyfikowaną tablicę, należy użyć [instrukcji Update-and-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) lub [wyrażeń Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).

* Alternatywnie można utworzyć tablicę na podstawie jej rozmiaru przy użyciu `new` słowa kluczowego:

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* Użyj funkcji Core, `Length` Aby uzyskać liczbę elementów z tablicy jako `Int` .
* Tablice można indeksować, aby uzyskać pojedyncze elementy lub nowe tablice zawierające podzestaw elementów tablicy.
Indeksy dolne tablic są oparte na zero i muszą być typu `Int` lub typu `Range` :

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>Typy krotek

Krotki są zaawansowaną koncepcją używaną przez cały Q# program do zbierania wartości w jednej wartości, co ułatwia ich przekazywanie.
W szczególności przy użyciu notacji krotki można wyrazić, że każda operacja i możliwy do odwoływać przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.

* Podaną zero lub kilka różnych typów,,..., `T0` `T1` można zauważyć, że `Tn` Nowy  *Typ krotki* jako `(T0, T1, ..., Tn)` .
Typy używane do konstruowania nowego typu krotki mogą sami być krotkami, jak w `(Int, (Qubit, Qubit))` .
Takie zagnieżdżenie jest zawsze ograniczone, jednak ponieważ typy krotek nie mogą znajdować się w żadnych okolicznościach.

* Wartości nowego typu krotki są krotkami tworzonymi przez sekwencje wartości z każdego typu w spójnej kolekcji.
Na przykład `(3, false)` jest to krotka, której typem jest typ krotki `(Int, Bool)` .
Istnieje możliwość tworzenia tablic krotek, spójnych kolekcji tablic, krotek podkolekcji i tak dalej.

* Od Q# 0,3, `Unit` jest nazwą *typu* pustej krotki; `()` jest używana dla *wartości* pustej krotki.

* Wystąpienia krotki są niezmienne.
Q# Program nie udostępnia mechanizmu zmiany zawartości spójnej kolekcji po utworzeniu.



### <a name="singleton-tuple-equivalence"></a>Równoważna krotka singleton

Możliwe jest utworzenie pojedynczej krotki (pojedynczego elementu) `('T1)` , takiej jak `(5)` lub `([1,2,3])` .
Jednakże Q# traktuje pojedynczą krotkę jako odpowiednik wartości zamkniętego typu.
Oznacza to, że nie ma różnicy między `5` i `(5)` , lub między i i między i `5` `(((5)))` `(5, (6))` `(5, 6)` .
Jest to równie ważne, aby można było pisać `(5)+3` w miarę pisania `5+3` ; oba wyrażenia są oceniane do `8` .

Ta równoważność ma zastosowanie do wszystkich celów, w tym przypisania i wyrażeń.
Uwzględniając dowolne wyrażenie, to samo wyrażenie ujęte w nawiasy jest wyrażeniem tego samego typu.
Na przykład `(7)` jest wyrażeniem typu `Int` , `([1,2,3])` jest wyrażeniem typu `Int[]` i `((1,2))` jest wyrażeniem typu `(Int, Int)` .

W szczególności oznacza to, że można wyświetlić operację lub funkcję, której kolekcja wejściowa lub typ krotki danych wyjściowych ma jedno pole jako przyjmujące pojedynczy argument lub zwraca pojedynczą wartość.

Nazywamy tę właściwość jako _równoważność spójnej kolekcji_ .


## <a name="user-defined-types"></a>Typy User-Defined

Deklaracja typu zdefiniowanego przez użytkownika składa się ze słowa kluczowego `newtype` , po którym następuje nazwa typu zdefiniowanego przez użytkownika, elementu `=` , prawidłowej specyfikacji typu i kończącego się średnika.

Na przykład:

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* Każdy Q# plik źródłowy może deklarować dowolną liczbę typów zdefiniowanych przez użytkownika.
* Nazwy typów muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktów z nazwami operacji i funkcji.
* Typy zdefiniowane przez użytkownika są różne, nawet jeśli typy podstawowe są identyczne.
W szczególności nie istnieje Automatyczna konwersja między wartościami dwóch typów zdefiniowanych przez użytkownika, nawet jeśli typy bazowe są identyczne.

### <a name="named-vs-anonymous-items"></a>Elementy nazwane a anonimowe

Q#Plik może definiować nowy nazwany typ zawierający pojedynczą wartość dowolnego typu prawnego.
Dla dowolnego typu krotki `T` można zadeklarować nowy typ zdefiniowany przez użytkownika, który jest podtypem `T` `newtype` instrukcji.
Na @"microsoft.quantum.math" przykład w przestrzeni nazw liczba zespolona jest definiowana jako typ zdefiniowany przez użytkownika:

```qsharp
newtype Complex = (Double, Double);
```
Ta instrukcja tworzy nowy typ z dwoma anonimowymi elementami typu `Double` .   

Poza elementami anonimowymi typy zdefiniowane przez użytkownika obsługują również *nazwane elementy* w Q# wersji 0,7 lub nowszej. Można na przykład nazwać elementy do `Real` dla podwójnego reprezentowania rzeczywistej części liczby zespolonej i `Imag` dla części urojonej: 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
Nazewnictwo jednego elementu w typie zdefiniowanym przez użytkownika nie oznacza, że wszystkie elementy muszą mieć nazwę, a także obsługiwane są dowolne kombinacje elementów nazwanych i nienazwanych. Ponadto elementy wewnętrzne mogą być również nazwane.
Typ `Nested` , jak pokazano poniżej, ma typ podstawowy `(Double, (Int, String))` , którego tylko element typu `Int` ma nazwę, a wszystkie inne elementy są anonimowe. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Elementy nazwane mają zalety, do których można uzyskiwać dostęp bezpośrednio za pośrednictwem *operatora dostępu* `::` . 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

Oprócz udostępniania krótkich aliasów dla potencjalnie skomplikowanych typów krotek, istotną zaletą definiowania takich typów jest możliwość udokumentowania zamiaru określonej wartości.
Powracanie do przykładu `Complex` , może także definiować współrzędne biegunowe represenation jako typ zdefiniowany przez użytkownika:

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

Mimo że oba te `Complex` i `ComplexPolar` oba mają typ podstawowy `(Double, Double)` , te dwa typy są całkowicie niezgodne Q# , co minimalizuje ryzyko przypadkowego wywołania złożonej funkcji matematycznej z współrzędnymi biegunowymi i odwrotnie.

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Dostęp do anonimowych elementów za pomocą operatora rozwinięcia

Aby uzyskać dostęp do anonimowych elementów, najpierw Wyodrębnij wartość opakowaną przy użyciu operatora przyrostkowego `!` .
Za pomocą operatora "unotocz" `!` można wyodrębnić wartość zawartą w typie zdefiniowanym przez użytkownika.
Typ takiego wyrażenia "unotoka" jest typem podstawowym typu zdefiniowanego przez użytkownika. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Pojedynczy operator odpakowywania odpakuje jedną warstwę otoki. Użyj wielu nieopakowanych operatorów, aby uzyskać dostęp do wartości w postaci mnożenia.

Na przykład:

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

Aby uzyskać więcej informacji na temat operatora rozwinięcia, zobacz [wyrażenia typów Q# w ](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Tworzenie wartości typów zdefiniowanych przez użytkownika

Utwórz wartości typu zdefiniowanego przez użytkownika, wywołując odpowiedni Konstruktor typów:

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Alternatywnie można tworzyć nowe wartości z istniejących przy użyciu [wyrażeń Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Podobnie jak w przypadku tablic, wyrażeń kopiowania i aktualizacji Kopiuj wszystkie wartości elementu oryginalnego wyrażenia z wyjątkiem określonych nazwanych elementów. Dla tych wyjątków wartości tych elementów są wartości zdefiniowane po prawej stronie wyrażenia. Wszystkie inne konstrukcje językowe dostępne dla elementów tablicowych, na przykład [instrukcje Update-and-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), istnieją dla elementów nazwanych w typach zdefiniowanych przez użytkownika.

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

* Możesz użyć typów zdefiniowanych przez użytkownika wszędzie tam, gdzie używasz dowolnego innego typu.
W szczególności można zdefiniować tablicę typu zdefiniowanego przez użytkownika i dołączenia typu zdefiniowanego przez użytkownika jako elementu typu krotki.

* Nie można tworzyć struktur typów cyklicznych.
Oznacza to, że typ definiujący typ zdefiniowany przez użytkownika nie może być typem krotki, który zawiera element typu zdefiniowanego przez użytkownika.
Ogólnie rzecz biorąc, typy zdefiniowane przez użytkownika mogą nie zawierać cyklicznych zależności od siebie, więc następujący zestaw definicji typu jest nieprawidłowy:

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>Typy operacji i funkcji

Uwzględniając typy `'Tinput` i `'Tresult` :

* `('Tinput => 'Tresult)` jest typem podstawowym dla każdej *operacji* , na przykład `((Qubit, Pauli) => Result)` .
* `('Tinput -> 'Tresult)` jest typem podstawowym dla dowolnej *funkcji* , na przykład `(Int -> Int)` . 

Są one nazywane *sygnaturą* wywołania.

* Wszystkie Q# wartości są wywoływane jako dane wejściowe i zwracają pojedynczą wartość jako dane wyjściowe.
* Można używać krotek zarówno dla wartości wejściowych, jak i wyjściowych.
* Liczba, która nie ma wyniku, zwraca `Unit` .
* Możliwe do nadania, że żadne dane wejściowe nie przyjmują pustej kolekcji jako dane wejściowe.

### <a name="functors"></a>Funktory

Typy *funkcji* są w pełni określone przez ich sygnaturę. Na przykład funkcja, która oblicza sinus kąta, będzie miała typ `(Double -> Double)` . 

*Operacje* mają pewne dodatkowe cechy, które są wyrażane jako część typu operacji. Takie charakterystyki zawierają informacje o tym, które *funktory* operacja obsługuje.
Na przykład, Jeśli uruchomienie operacji opiera się na stanie innych qubits, powinien on obsługiwać `Controlled` Funktor; Jeśli operacja ma odwrotność, powinien obsługiwać `Adjoint` Funktor.

> [!NOTE]
> W tym artykule omówiono, jak funktory zmienić sygnaturę operacji. Aby uzyskać więcej informacji na temat funktory i operacji, zobacz [operacje i Q# funkcje w ](xref:microsoft.quantum.guide.operationsfunctions). 

Aby wymagać obsługi dla `Controlled` i/lub `Adjoint` Funktor w typie operacji, należy dodać adnotację wskazującą odpowiadające jej cechy.
Adnotacja `is Ctl` (na przykład `(Qubit => Unit is Ctl)` ) wskazuje, że operacja jest sterowana. Oznacza to, że jego przebieg zależy od stanu innego qubit lub qubits. Podobnie adnotacja `is Adj` wskazuje, że operacja ma sąsiadujące, to oznacza, że może być "odwrócona", co oznacza, że po zastosowaniu operacji, a następnie jej współdziałanie do stanu pozostawia stan niezmieniony. 

Jeśli chcesz wymagać, aby operacja tego typu obsługiwała zarówno element, `Adjoint` jak i `Controlled` Funktor, możesz to zrobić jako `(Qubit => Unit is Adj + Ctl)` . Na przykład wbudowana <xref:Microsoft.Quantum.Intrinsic.X> operacja Pauli ma typ `(Qubit => Unit is Adj + Ctl)` . 

Typ operacji, która nie obsługuje żadnej funktory, jest określany za pomocą samego typu danych wejściowych i wyjściowych, bez dodatkowej adnotacji.

### <a name="type-parameterized-functions-and-operations"></a>Type-Parameterized funkcje i operacje

Możliwe do napisania typy mogą zawierać *parametry typu* .
Użyj symbolu poprzedzonego znakiem pojedynczego cudzysłowu, aby wyznaczyć parametr typu; na przykład `'A` jest parametrem typu prawnego.
Aby uzyskać więcej informacji i szczegółowe informacje na temat sposobu definiowania dożądanych parametrów typu, zobacz [operacje i Q# funkcje w ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).

Parametr typu może pojawić się więcej niż raz w pojedynczym podpisie.
Na przykład funkcja, która stosuje inną funkcję do każdego elementu tablicy i zwraca zebrany wynik ma sygnaturę `(('A[], 'A->'A) -> 'A[])` .
Podobnie funkcja, która zwraca skład dwóch operacji, ma sygnaturę `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Po wywołaniu wywołania typu sparametryzowanego wszystkie argumenty, które mają ten sam parametr typu, muszą być tego samego typu.

Q# Program nie udostępnia mechanizmu ograniczania możliwych typów, które użytkownik może zastąpić parametrem typu.

## <a name="next-steps"></a>Następne kroki

Teraz, gdy wykorzystano wszystkie typy, które składają się na Q# język, zobacz [typy wyrażeń Q# w](xref:microsoft.quantum.guide.expressions) , aby dowiedzieć się, jak tworzyć i manipulować wyrażeniami tych różnych typów.

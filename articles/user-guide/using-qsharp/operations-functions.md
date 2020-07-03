---
title: 'Operacje i funkcje w funkcji Q #'
description: Jak definiować i wywoływać operacje i funkcje, a także wyspecjalizowane specjalizacje operacji.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 08eaf150a38afd789f8a23f567ff111d002bac07
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884205"
---
# <a name="operations-and-functions-in-q"></a>Operacje i funkcje w funkcji Q #

## <a name="defining-new-operations"></a>Definiowanie nowych operacji

Operacje są rdzeniem Q #.
Po zadeklarowaniu można je wywołać z klasycznej aplikacji .NET, na przykład za pomocą symulatora lub przez inne operacje w usłudze Q #.
Każda operacja zdefiniowana w Q # może wywołać dowolną liczbę innych operacji, łącznie z wbudowanymi operacjami wewnętrznymi zdefiniowanymi przez język. Określony sposób, w jaki funkcja Q # definiuje te operacje wewnętrzne, zależy od maszyny docelowej.
Po skompilowaniu każda operacja jest reprezentowana jako typ klasy .NET, który można dostarczyć dla maszyn docelowych.

Każdy plik źródłowy Q # może definiować dowolną liczbę operacji.
Nazwy operacji muszą być unikatowe w obrębie przestrzeni nazw i nie mogą powodować konfliktów z nazwami typów lub funkcji.

Deklaracja operacji składa się ze słowa kluczowego `operation` , po którym występuje symbol, który jest nazwą operacji, spójna kolekcja identyfikatorów, która definiuje argumenty do operacji, dwukropek `:` , adnotację typu opisującą typ wyniku operacji, opcjonalnie adnotację z charakterystykami operacji, otwartym nawiasem klamrowym, a następnie treść deklaracji operacji ujętą w nawiasy klamrowe `{ }` .

Każda operacja przyjmuje dane wejściowe, tworzy dane wyjściowe i określa Implementację dla co najmniej jednej specjalizacji operacji.
Możliwe specjalizacje oraz sposób definiowania i wywoływania tych elementów są szczegółowo opisane w różnych sekcjach tego artykułu.
Na razie Rozważmy następujące operacje, które definiują tylko domyślną specjalizację treści i pobierają pojedyncze qubit jako dane wejściowe, a następnie wywołują wbudowaną <xref:microsoft.quantum.intrinsic.x> operację na tym wejściu:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Słowo kluczowe `operation` rozpoczyna definicję operacji, po której następuje nazwa; tutaj, `BitFlip` .
Następnie typ danych wejściowych jest zdefiniowany ( `Qubit` ), wraz z nazwą,, w odniesieniu `target` do danych wejściowych w ramach nowej operacji.
Wreszcie definiuje, `Unit` że dane wyjściowe operacji są puste.
`Unit`jest używany podobnie do `void` języka C# i innych nieużywanych języków i jest odpowiednikiem `unit` w języku F # i innych językach funkcjonalnych.

Operacje mogą również zwracać bardziej interesujące typy niż `Unit` .
Na przykład <xref:microsoft.quantum.intrinsic.m> operacja zwraca dane wyjściowe typu `Result` , reprezentujący wykonywanie pomiaru.  Można przekazać ją z operacji do innej operacji lub użyć jej ze `let` słowem kluczowym, aby zdefiniować nową zmienną.

Takie podejście umożliwia reprezentowanie klasycznego obliczenia, które współdziała z operacjami Quantum na niskim poziomie, na przykład w przypadku [kodowania](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)z nadmiernym użyciem:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> Każda operacja w funkcji Q # przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.
> Wiele danych wejściowych i wyjściowych jest przedstawianych przy użyciu *krotek*, które zbierają wiele wartości w jedną wartość.
> W tym przypadku Q # to język "Krotka w kolekcji".
> Po tym koncepcji zestaw pustych nawiasów `()` powinien zostać odczytany jako krotka "Empty", która ma typ `Unit` .

## <a name="controlled-and-adjoint-operations"></a>Operacje kontrolowane i sąsiadujące

Jeśli operacja implementuje transformację jednostkową, podobnie jak w przypadku wielu operacji w Q #, można zdefiniować sposób działania operacji podczas *adjointed* lub *kontrolowania*. *Podległych* specjalizacji operacji określa sposób działania "odwrotności" operacji, podczas gdy *kontrolowana* specjalizacja określa, jak działa operacja, gdy jej aplikacja jest kondycjonowana na stanie określonego rejestru Quantum.

Adjoints operacji Quantum są kluczowe dla wielu aspektów przetwarzania Quantum. Przykład jednej takiej sytuacji omówionej wraz z użyteczną techniką programowania Q # można znaleźć w temacie [sprzężenia](#conjugations) w tym artykule. 

Kontrolowana wersja operacji jest nową operacją, która efektywnie stosuje operację podstawową tylko wtedy, gdy wszystkie kontrolki qubits są w określonym stanie.
Jeśli kontrolka qubits znajduje się w położeniu, wówczas podstawowa operacja jest stosowana spójnie z odpowiednią częścią położenia.
W ten sposób kontrolowane operacje są często używane do generowania Entanglement.

W naturalny sposób *kontrolowanego* obszaru specjalizacji może istnieć również określenie kontrolowanej aplikacji sąsiadującej operacji.

> [!NOTE]
> Jeśli $U $ to transformacja jednostkowa zaimplementowana przez operację `U` , `Adjoint U` reprezentuje ona transformację jednostkową $U ^ \dagger $, która jest złożonym transpozycję sprzężonej sprzężenia.
> Po zastosowaniu operacji, a następnie jej współdziałaniu do stanu pozostawia stan niezmieniony, tak jak pokazano to jest fakt, że $UU ^ \dagger = U ^ \dagger U = \id $, macierz tożsamości.
> Reprezentacja jednostkowa kontrolowanej operacji jest nieco bardziej złożonych, ale można znaleźć więcej szczegółów na temat [koncepcji przetwarzania Quantum: wielu qubits](xref:microsoft.quantum.concepts.multiple-qubits).

W poniższej sekcji opisano, jak wywoływać różne specjalizacje w kodzie Q # oraz jak definiować operacje do ich obsługi.

### <a name="calling-operation-specializations"></a>Wywoływanie specjalizacji operacji

*Funktor* w Q # to fabryka, która definiuje nową operację z innej operacji.
Dwa standardowe funktory w pytaniach Q # są `Adjoint` i `Controlled` .

Funktory mają dostęp do implementacji operacji podstawowej podczas definiowania implementacji nowej operacji.
W ten sposób funktory może wykonywać bardziej złożone funkcje niż tradycyjne funkcje wyższego poziomu. Funktory nie ma reprezentacji w systemie typu Q #. Obecnie nie można powiązać ich ze zmienną lub przekazać ich jako argumenty. 

Użyj Funktor, stosując go do operacji, która zwraca nową operację.
Na przykład zastosowanie `Adjoint` Funktor do `Y` operacji zwraca nową operację `Adjoint Y` . Nową operację można wywołać tak jak każda inna operacja.
W przypadku operacji do obsługi aplikacji `Adjoint` lub `Controlled` funktory jej typ zwracany musi być `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`Funktor

W tym celu program `Adjoint Y(q1)` stosuje `Adjoint` Funktor do `Y` operacji w celu wygenerowania nowej operacji i stosuje tę nową operację do `q1` .
Nowa operacja ma ten sam podpis i typ co operacja podstawowa `Y` .
W szczególności Nowa operacja obsługuje także `Adjoint` i obsługuje tylko wtedy, `Controlled` gdy operacja podstawowa zakończyła się.
`Adjoint`Funktor jest własnym odwrotnością; oznacza to, że `Adjoint Adjoint Op` jest zawsze taka sama jak `Op` .

#### <a name="controlled-functor"></a>`Controlled`Funktor

Podobnie program `Controlled X(controls, target)` stosuje `Controlled` Funktor do `X` operacji w celu wygenerowania nowej operacji i stosuje tę nową operację do `controls` i `target` .

> [!NOTE]
> W programie Q # kontrolowane wersje zawsze przyjmują tablicę kontrolek qubits, a kontrola jest zawsze oparta na wszystkich formantach qubits w stanie obliczeniowym ( `PauliZ` ) `One` , $ \ket {1} $.
> Kontrola oparta na innych Stanach jest osiągana przez zastosowanie odpowiedniej operacji jednostkowej do kontrolki qubits przed operacją sterowaną, a następnie zastosowanie odwrotności operacji jednostkowej po kontrolowanej operacji.
> Na przykład stosowanie `X` operacji do kontrolki qubit przed i po kontrolowanej operacji powoduje, że operacja kontroluje `Zero` stan ($ \ket {0} $) dla tego qubit; stosowanie `H` operacji przed i po kontrolkach `PauliX` `One` stanu, czyli-1 eigenvalue Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $, a nie `PauliZ` `One` stan.

Po otrzymaniu wyrażenia operacji można utworzyć nowe wyrażenie operacji przy użyciu `Controlled` Funktor.
Sygnatura nowej operacji jest oparta na podpisie oryginalnej operacji.
Typ wyniku jest taki sam, ale typ danych wejściowych jest krotką dwukrotną z tablicą qubit, która przechowuje qubit kontrolki jako pierwszy element i argumenty oryginalnej operacji jako drugi element.
Nowa operacja obsługuje `Controlled` i będzie obsługiwać funkcję `Adjoint` if i tylko wtedy, gdy oryginalna operacja zakończyła się.

Jeśli oryginalna Operacja trwała tylko z pojedynczym argumentem, w tym miejscu będzie można odtwarzać [pojedynczej równoważności krotek](xref:microsoft.quantum.guide.types) .
Na przykład `Controlled X` jest kontrolowana wersja `X` operacji. 
`X`ma typ `(Qubit => Unit is Adj + Ctl)` , więc `Controlled X` ma typ `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; ze względu na równoważność spójnej kolekcji, jest to taka sama jak `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Jeśli operacja podstawowa wymagała kilku argumentów, pamiętaj, aby ująć odpowiednie argumenty kontrolowanej wersji operacji w nawiasach, aby przekonwertować je na krotkę.
Na przykład `Controlled Rz` jest kontrolowana wersja `Rz` operacji. 
`Rz`ma typ `((Double, Qubit) => Unit is Adj + Ctl)` , więc `Controlled Rz` ma typ `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
W rezultacie będzie `Controlled Rz(controls, (0.1, target))` to poprawne wywołanie `Controlled Rz` (należy zwrócić uwagę na nawiasy `0.1, target` ).

Innym przykładem `CNOT(control, target)` może być implementacja `Controlled X([control], target)` . Jeśli element docelowy powinien być kontrolowany przez dwie qubits kontroli (CCNOT), użyj `Controlled X([control1, control2], target)` instrukcji.

#### `Controlled Adjoint` 

`Controlled`I `Adjoint` funktory się, więc nie ma różnicy między stosowaniem `Controlled Adjoint Op` lub `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definiowanie kontrolowanych i sąsiadujących implementacji

W pierwszej deklaracji operacji w poprzednich przykładach operacje `BitFlip` i `DecodeSuperdense` zostały zdefiniowane z podpisami `(Qubit => Unit)` i `((Qubit, Qubit) => (Result, Result))` odpowiednio.
Jak `DecodeSuperdense` obejmuje pomiary, nie jest operacją jednostkową i w związku z tym nie może istnieć żadne kontrolowane niesąsiadujące specjalizacje (odwołaj powiązane wymaganie, aby ta operacja zwracała `Unit` ).
Jednak jak `BitFlip` po prostu wykonuje operację jednostkową <xref:microsoft.quantum.intrinsic.x> , można ją zdefiniować przy użyciu obu specjalizacji.

W tej sekcji szczegółowo opisano, jak uwzględnić istnienie specjalizacji w deklaracjach operacji Q #, dzięki czemu można wywołać tę możliwość w połączeniu z `Adjoint` lub `Controlled` funktory.
Aby uzyskać więcej informacji o niektórych sytuacjach, w których jest to prawidłowe lub nieprawidłowe, aby zadeklarować specjalizacje, zobacz [warunki dotyczące prawidłowej definiowania specjalizacji](#circumstances-for-validly-defining-specializations) w tym artykule.

Charakterystyki operacji definiują rodzaje funktory, które można zastosować do zadeklarowanej operacji oraz jaki ma wpływ. Istnienie tych specjalizacji może być zadeklarowane jako część podpisu operacji, w odniesieniu do adnotacji z charakterystyką operacji: `is Adj` , `is Ctl` lub `is Adj + Ctl` .
Rzeczywista implementacja każdej specjalizacji może być *jawnie* lub *jawnie* zdefiniowana.

### <a name="implicitly-specifying-implementations"></a>Niejawnie Określanie implementacji

W takim przypadku treść deklaracji operacji składa się wyłącznie z implementacji domyślnej. Przykład:

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
W tym miejscu odpowiednia implementacja dla każdej takiej niejawnie zadeklarowanej specjalizacji jest automatycznie generowana przez kompilator, która ma zostać wykonana w przypadku `Adjoint` `Controlled` użycia lub funktory.

Dlatego wywołanie `Adjoint PrepareEntangledPair` spowodowałaby kompilator implementujący sąsiadujące, `CNOT` a następnie sąsiadująco `H` .
Te poszczególne operacje są samodzielne, więc wynikiem `Adjoint PrepareEntangledPair` operacji będzie po prostu zastosowanie, `CNOT(here, there)` a następnie `H(here)` .
W związku z tym możesz użyć tego polecenia `DecodeSuperdense` , aby napisać w poprzednim przykładzie bardziej kompaktowo, przy użyciu sąsiadująco w `PrepareEntangledPair` celu przekształcenia stanu Entangled z powrotem do pary unentangled qubits:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Adnotacja z charakterystyką operacji w deklaracji jest przydatna, aby zapewnić, że kompilator automatycznie generuje inne specjalizacje na podstawie domyślnej implementacji. 

Istnieje kilka istotnych ograniczeń, które należy wziąć pod uwagę podczas projektowania operacji do użycia z funktory.
W przypadku niekrytycznej specjalizacji dla operacji korzystającej z wartości wyjściowej żadnej innej operacji *nie może* być automatycznie generowana przez kompilator, ponieważ jest niejednoznaczna w przypadku zmiany kolejności instrukcji w takiej operacji w celu uzyskania tego samego efektu.

W związku z tym często warto jawnie określić różne implementacje.

### <a name="explicitly-specifying-implementations"></a>Jawne określanie implementacji

W przypadku, gdy kompilator nie może wygenerować implementacji, można określić ją jawnie. Takie jawne deklaracje specjalizacji mogą składać się z odpowiedniej *dyrektywy generacji* lub implementacji zdefiniowanej przez użytkownika.
Poniżej przedstawiono pełen zakres możliwości, z kilkoma przykładami jawnej specjalizacji. 


#### <a name="explicit-specialization-declarations"></a>Jawne deklaracje specjalizacji

Operacje Q # mogą zawierać następujące jawne deklaracje specjalizacji:

- `body`Specjalizacja określa implementację operacji bez zastosowanych funktory.
- `adjoint`Specjalizacja określa implementację operacji z `Adjoint` zastosowaniem Funktor.
- `controlled`Specjalizacja określa implementację operacji z `Controlled` zastosowaniem Funktor.
- `controlled adjoint`Specjalizacja określa implementację operacji z `Adjoint` `Controlled` zastosowaniem zarówno i funktory.
  Ta specjalizacja może być również nazywana `adjoint controlled` , ponieważ dwie funktory.


Specjalizacja operacji składa się z tagu specjalizacji (na przykład `body` lub `adjoint` ), po którym następuje jedna z następujących wartości:

- Jawna deklaracja zgodnie z opisem w poniższej tabeli.
- *Dyrektywa* , która informuje kompilator, *jak* generować specjalizację, jeden z:
  - `intrinsic`, co oznacza, że komputer docelowy udostępnia specjalizację.
  - `distribute`, używany z `controlled` `controlled adjoint` specjalizacjami i.
    Gdy jest używany z `controlled` , wskazuje, że kompilator powinien obliczyć specjalizację, stosując `Controlled` do wszystkich operacji w `body` .
    Gdy jest używany z `controlled adjoint` , wskazuje, że kompilator powinien obliczyć specjalizację przez zastosowanie `Controlled` do wszystkich operacji w `adjoint` specjalizacji.
  - `invert`, co oznacza, że kompilator powinien obliczyć `adjoint` specjalizację, odwracając `body` , na przykład, odwracając kolejność operacji i stosując sąsiednie do każdego z nich.
    Gdy jest używany z `adjoint controlled` , oznacza to, że kompilator powinien obliczyć specjalizację, odwracając `controlled` specjalizację.
  - `self`, aby wskazać, że podległych specjalizacji jest taka sama jak `body` specjalizacja.
    Korzystanie `self` z programu jest dozwolone `adjoint` dla `adjoint controlled` specjalizacji i.
    W przypadku programu `adjoint controlled` `self` oznacza, że `adjoint controlled` specjalizacja jest taka sama jak `controlled` specjalizacja.
  - `auto`, aby wskazać, że kompilator powinien wybrać odpowiednią dyrektywę, która ma zostać zastosowana.
    Nie można użyć `auto` dla `body` specjalizacji.

Dyrektywy i `auto` wszystkie wymagają zamykającego średnika `;` .
`auto`Dyrektywa jest rozpoznawana jako następująca wygenerowana dyrektywa, jeśli określono jawną deklarację `body` :

- `adjoint`Specjalizacja generuje zgodnie z dyrektywą `invert` .
- `controlled`Specjalizacja generuje zgodnie z dyrektywą `distribute` .
- `adjoint controlled`Specjalizacja generuje zgodnie z dyrektywą, `invert` Jeśli jawna Deklaracja dla `controlled` jest podano, ale nie dla `adjoint` , i `distribute` w inny sposób.

> [!TIP]   
> Jeśli operacja jest samodzielna, należy jawnie określić sąsiadujące lub kontrolowane specjalizację za pomocą dyrektywy generacji, `self` Aby umożliwić kompilatorowi użycie tych informacji do celów optymalizacji.

Deklaracja specjalizacji, która zawiera implementację zdefiniowaną przez użytkownika, składa się z krotki argumentu, po której następuje blok instrukcji z kodem Q #, który implementuje specjalizację.
Na liście argumentów `...` służy do reprezentowania argumentów zadeklarowanych dla operacji jako całości.
Dla `body` i `adjoint` , lista argumentów powinna być zawsze `(...)` ; dla `controlled` i `adjoint controlled` , lista argumentów powinna być symbolem, który reprezentuje tablicę kontrolki qubits, a następnie `...` ujętą w nawiasy; na przykład `(controls,...)` .

### <a name="examples"></a>Przykłady

Deklaracja operacji może być prosta jako następująca, która definiuje pierwotną operację Pauli X:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
Należy zauważyć, że sąsiadująca operacja Pauli X została zdefiniowana z dyrektywą, `self` ponieważ według definicji `X` jest jej własnymi oddziałami.

W poprzednim `PrepareEntangledPair` przykładzie kod jest równoważny z poniższym kodem zawierającym jawne deklaracje specjalizacji: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
Słowo kluczowe `auto` wskazuje, że kompilator powinien określić sposób generowania implementacji specjalizacji.

#### <a name="user-defined-specialization-implementation"></a>Implementacja specjalizacji zdefiniowanej przez użytkownika

Jeśli kompilator nie może automatycznie wygenerować implementacji dla konkretnej specjalizacji lub można określić bardziej wydajną implementację, można ręcznie zdefiniować implementację.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
W poprzednim przykładzie oznacza to, `adjoint invert;` że jest generowana podległych specjalizacji przez odwrócenie implementacji treści i `controlled adjoint invert;` wskazuje, że kontrolowana specjalizacja jest generowana przez odwrócenie danej implementacji kontrolowanej specjalizacji.

Jeśli co najmniej jedna specjalizacja poza treścią domyślną musi być zadeklarowana w sposób jawny, implementacja treści domyślnej musi być opakowana do odpowiedniej deklaracji specjalizacji:

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a>Warunki dotyczące prawidłowej definiowania specjalizacji

#### <a name="operation-declarations-with-adjointcontrolled"></a>Deklaracje operacji z sąsiadującymi/kontrolowanymi

Istnieje możliwość określenia operacji bez wersji sąsiednich lub kontrolowanych. Na przykład operacje pomiarów nie mają żadnego elementu, ponieważ nie są odwracalna ani nie są kontrolowane.

Operacja obsługuje `Adjoint` i funktory, `Controlled` Jeśli jej deklaracja zawiera niejawną lub jawną deklarację odpowiednich specjalizacji.

Jawne zadeklarowane, sąsiadujące/kontrolowane specjalizacje implikuje istnienie podległych/kontrolowanej specjalizacji. 

Dla operacji, której treść zawiera pętle REPEAT-until-Success, Set instrukcje, pomiary, instrukcje Return lub wywołania do innych operacji, które nie obsługują `Adjoint` Funktor, nie jest możliwe wygenerowanie przyległych specjalizacji po `invert` dyrektywie lub `auto` .

Dla operacji, której treść zawiera wywołania do innych operacji, które nie obsługują `Controlled` Funktor, nie jest możliwe wygenerowanie kontrolowanej specjalizacji po `distribute` `auto` dyrektywie lub.

#### <a name="controlled-adjoint"></a>Kontrolowane sąsiadująco

Sterowana sąsiadująco wersja operacji określa sposób implementacji kontrolowanej przez Quantum wersji podległych operacji.
Istnieje możliwość określenia operacji bez kontrolowanej wersji sąsiadującej; na przykład operacje pomiarów nie mają kontrolowanej wersji sąsiadującej, ponieważ nie są ani odwracalnae ani nie są dostępne.

Kontrolowana podległych specjalizacji dla operacji musi istnieć, jeśli i tylko wtedy, gdy istnieje zarówno przyległych, jak i kontrolowanych specjalizacji. W takim przypadku istnieje wywnioskowane istnienie kontrolowanej specjalizacji. Jeśli żadna implementacja nie jest jawnie zdefiniowana, kompilacja generuje odpowiednią specjalizację.

W przypadku operacji, której treść zawiera wywołania do innych operacji, które nie mają kontrolowanej sąsiedniej wersji, funkcja nie jest możliwa do wygenerowania podległych specjalizacji zgodnie z `invert` , `distribute` lub `auto` .


### <a name="type-compatibility"></a>Zgodność typów

Użyj operacji z dodatkowymi funktoryami obsługiwanymi wszędzie tam, gdzie używasz operacji z mniejszą liczbą funktory, ale z tą samą sygnaturą. Na przykład użyj operacji typu w `(Qubit => Unit is Adj)` dowolnym miejscu, w którym używasz operacji typu `(Qubit => Unit)` .

Q # jest *współwariantem* w odniesieniu do możliwego do zwrócenia typu zwracanego: wywoływany, który zwraca typ `'A` jest zgodny z tym samym typem danych wejściowych i typem wyniku, który jest zgodny z `'A` .

Q # jest *kontrawariantne* w odniesieniu do typów danych wejściowych: wywoływany typ `'A` jako dane wejściowe jest zgodny z wywoływanym z tym samym typem wyniku i typem danych wejściowych zgodnym z `'A` .

Oznacza to, że podano następujące definicje:

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

Można

- Wywołaj funkcję `ConjugateInvertWith` z `inner` argumentem `Invert` lub `ApplyUnitary` .
- Wywołaj funkcję `ConjugateUnitaryWith` z `inner` argumentem `ApplyUnitary` , ale nie `Invert` .
- Zwraca wartość typu `(Qubit[] => Unit is Adj + Ctl)` z `ConjugateInvertWith` .

> [!IMPORTANT]
> Q # 0,3 wprowadza znaczną różnicę w zachowaniu typów zdefiniowanych przez użytkownika.

Typy zdefiniowane przez użytkownika są traktowane jako opakowana wersja typu podstawowego, a nie jako podtyp.
Oznacza to, że wartość typu zdefiniowanego przez użytkownika nie może być użyteczna w przypadku, gdy oczekiwano wartości typu podstawowego.


### <a name="conjugations"></a>Liczby sprzężone

W przeciwieństwie do klasycznych bitów zwalnianie pamięci Quantum jest nieco bardziej zamierzone, ponieważ niequbitse Resetowanie może mieć niepożądane skutki dla pozostałych obliczeń, jeśli qubits nadal Entangled. Te efekty można uniknąć przez prawidłowe wykonanie obliczeń przed przystąpieniem do zwolnienia pamięci. Typowym wzorcem przetwarzania Quantum jest następujące: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

Począwszy od naszego 0,9 wydania, Q # obsługuje instrukcję sprzężenia implementującą poprzednie przekształcenie. Korzystając z tej instrukcji, `ApplyWith` można zaimplementować operację w następujący sposób:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Taka instrukcja sprzężona jest znacznie bardziej użyteczna, jeśli przekształcenia zewnętrzne i wewnętrzne nie są łatwo dostępne jako operacje, ale są bardziej wygodne do opisania przez blok składający się z kilku instrukcji. 

Przekształcenie odwrotne dla instrukcji zdefiniowanych w bloku jest automatycznie generowane przez kompilator i uruchamiane po zakończeniu zastosowania instrukcji.
Ponieważ żadne zmienne modyfikowalne używane jako część wewnątrz bloku nie mogą być ponownie powiązane w bloku Apply, wygenerowane przekształcenie jest gwarantowane jako sąsiadujące obliczenie w bloku. 


## <a name="defining-new-functions"></a>Definiowanie nowych funkcji

Funkcje są całkowicie deterministyczne, klasyczne procedury w Q #, które różnią się od operacji w tym, że nie mogą mieć żadnych efektów poza obliczaniem wartości wyjściowej.
W szczególności funkcje nie mogą wywoływać operacji; Działaj na, alokuj lub zażycz qubits; Przykładowe liczby losowe; lub w inny sposób zależy od stanu poza wartością wejściową do funkcji.
W związku z tym funkcje Q # są *czyste*, w tym przypadku zawsze mapują te same wartości wejściowe na te same wartości wyjściowe.
Dzięki temu kompilator Q # może bezpiecznie zmienić kolejność i czas wywoływania funkcji podczas generowania specjalizacji operacji.

Każdy plik źródłowy Q # może definiować dowolną liczbę funkcji.
Nazwy funkcji muszą być unikatowe w obrębie przestrzeni nazw i nie mogą powodować konfliktu z nazwami operacji lub typów.

Definiowanie funkcji działa podobnie do definiowania operacji, z tą różnicą, że dla funkcji nie można definiować podległych lub kontrolowanych specjalizacji.
Przykład:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

lub 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a>Klasyczna logika w funkcjach = = dobra

Za każdym razem, gdy jest to możliwe, warto napisać klasyczną logikę pod kątem funkcji, a nie operacji, dzięki czemu operacje mogą łatwo korzystać z niej. Na przykład, jeśli wcześniej zapisałeś wcześniejszą `Square` deklarację jako *operację*, kompilator nie może zagwarantowania, że wywołanie go z tymi samymi danymi wejściowymi będzie spójnie generować te same dane wyjściowe.

Aby podkreślić różnicę między funkcjami i operacjami, należy wziąć pod uwagę problem z próbkami klasycznymi losowych, z poziomu operacji Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Za każdym razem `U` , gdy jest wywoływana, ma inną akcję na `target` .
W szczególności kompilator nie może zagwarantować, że jeśli dodasz `adjoint auto` deklarację specjalizacji do `U` , `U(target); Adjoint U(target);` działa jako tożsamość (to oznacza, że jako No-op).
To narusza definicję części sąsiedniej zdefiniowanej w [wektorach i macierzach](xref:microsoft.quantum.concepts.vectors), takich jak umożliwienie kompilatorowi automatyczne wygenerowanie sąsiadującej specjalizacji w operacji, w której wywołanie operacji <xref:microsoft.quantum.math.randomreal> spowodowałoby przerwanie gwarancji dostarczonych przez kompilator; <xref:microsoft.quantum.math.randomreal> jest operacją, dla której nie istnieje przyległych lub kontrolowana wersja.

Z drugiej strony, zezwolenie na wywołania funkcji, takie jak `Square` jest bezpieczne, i gwarantuje, że kompilator musi tylko zachować dane wejściowe, aby `Square` zachować stabilny wynik.
W ten sposób izolowanie możliwie największej logiki w ramach funkcji pozwala łatwo ponownie wykorzystać tę logikę w innych funkcjach i operacjach.


## <a name="generic-type-parameterized-callables"></a>Typy ogólne (sparametryzowane od typu)

Wiele funkcji i operacji, które można zdefiniować, nie jest w rzeczywistości zależne od typów danych wejściowych, ale raczej niejawnie Używaj ich typów za pośrednictwem innej funkcji lub operacji.
Rozważmy na przykład, że koncepcja *mapy* jest wspólna dla wielu języków funkcjonalnych; dana funkcja $f (x) $ i Kolekcja wartości $ \{ x_1, x_2, \dots, x_n \} $, map zwraca nową kolekcję $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.
W celu zaimplementowania tej funkcji w programie Q # Skorzystaj z faktu, że funkcje są pierwszej klasy.
Oto szybki przykład `Map` użycia `T` jako symbol zastępczy podczas ustalania potrzebnych typów.

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Należy zauważyć, że ta funkcja wygląda bardzo podobnie niezależnie od tego, jakie typy rzeczywiste zostały zastąpione.
Mapa z liczb całkowitych na Paul, na przykład, wygląda podobnie jak mapa od liczb zmiennoprzecinkowych do ciągów:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

W zasadzie można napisać wersję programu `Map` dla każdej pary typów, które napotykasz, ale wprowadzamy kilka trudności.
Na przykład jeśli znajdziesz usterkę w programie `Map` , należy upewnić się, że poprawka jest stosowana jednolicie we wszystkich wersjach programu `Map` .
Ponadto w przypadku konstruowania nowej spójnej kolekcji lub UDT, należy również utworzyć nową, `Map` Aby przejść do nowego typu.
Chociaż jest to możliwe w przypadku niewielkiej liczby takich funkcji, podczas zbierania większej i większej liczby funkcji tego samego formularza co `Map` koszt wprowadzenia nowych typów stanie się nieuzasadniony w dość krótkim porządku.

Jednak większość tego rodzaju trudności wynika z faktu, że nie podano w kompilatorze informacji, które muszą rozpoznać, w jaki sposób `Map` są powiązane różne wersje.
Efektywnie, chcesz, aby kompilator traktował `Map` jako rodzaj funkcji matematycznej z *typów* q # do funkcji q #.

Q # formalizes to pojęcie, zezwalając na funkcje i operacje mające *parametry typu*, a także ich zwykłe parametry krotek.
W poprzednich przykładach, chcesz traktować `Map` jako parametry typu `Int, Pauli` w pierwszym przypadku i `Double, String` w drugim przypadku.
W większości przypadków Użyj tych parametrów typu, tak jakby były to typy zwykłe. Używaj wartości parametrów typu do wprowadzania tablic i krotek, wywoływania funkcji i operacji oraz przypisywania do zmiennych normalnych lub modyfikowalnych.

> [!NOTE]
> Największą sytuacją pośrednią jest to, że qubits, w którym program Q # nie może bezpośrednio polegać na strukturze `Qubit` typu, ale **musi** przekazać takie typy do innych operacji i funkcji.

Powracanie do wcześniejszego przykładu, zobaczysz, że `Map` musi mieć parametry typu, jeden do reprezentowania danych wejściowych `fn` i jeden do reprezentowania danych wyjściowych `fn` .
W polu Q # jest to zapisywana przez dodanie nawiasów kątowych ( `<>` nie brakets $ \braket {} $!) po nazwie funkcji lub operacji w jej deklaracji oraz przez wystawienie poszczególnych parametrów typu.
Nazwa każdego parametru typu musi rozpoczynać się od osi `'` , wskazując, że jest parametrem typu, a nie zwykłym typem (znanym także jako *konkretny* typ).
W tym przypadku `Map` :

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Należy zauważyć, że definicja `Map<'Input, 'Output>` wygląda bardzo podobna do wersji previoius.
Jedyną różnicą jest to, że użytkownik jawnie poinformowany o kompilatorze, który `Map` nie zależy bezpośrednio od tego `'Input` `'Output` , co jest `fn`
Po zdefiniowaniu `Map<'Input, 'Output>` w ten sposób można wywołać tę funkcję, tak jakby była to funkcja zwykła:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Pisanie funkcji ogólnych i operacji to jedno miejsce, w którym "krotka spójna z krotką" to bardzo użyteczny sposób, aby myśleć o funkcjach i operacjach pytań i odpowiedzi.
> Ponieważ każda funkcja przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście, dane wejściowe typu `'T -> 'U` dopasowują *dowolną* funkcję Q #.
> Podobnie można przekazać dowolną operację do danych wejściowych typu `'T => 'U` .

W drugim przykładzie należy wziąć pod uwagę wyzwanie napisania funkcji, która zwraca skład dwóch innych funkcji:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

W tym miejscu należy określić dokładnie to `A` , co `B` i co `C` to jest, a tym samym znacznie ograniczyć narzędzie do nowej `Compose` funkcji.
Po wszystko jest `Compose` zależne od `A` , `B` i `C` *przez* `innerFn` i `outerFn` .
Alternatywnie, można dodać parametry typu do `Compose` , które wskazują, że działa dla *dowolnego* `A` , `B` i `C` , tak długo, jak te parametry są zgodne z oczekiwanymi przez `innerFn` i `outerFn` :

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Biblioteki Q # Standard oferują wiele takich operacji i funkcji sparametryzowanych typu, aby ułatwić przepływ sterowania wyższym kolejnością.
Są one omówione bardziej szczegółowo w [przewodniku po bibliotece standardowej Q #](xref:microsoft.quantum.libraries.standard.intro).


## <a name="callables-as-first-class-values"></a>Możliwy do przełożenia jako wartości pierwszej klasy

Jedną z kluczowych technik z przyczyn dotyczących przepływu sterowania i klasycznej logiki przy użyciu funkcji, a nie operacji, jest wykorzystanie tych operacji i funkcji w Q # są *pierwszą klasą*.
Oznacza to, że są to poszczególne wartości w języku we własnym zakresie.
Na przykład, poniżej jest doskonale prawidłowy kod Q #, w przypadku niewielkiego pośrednika:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Wartość zmiennej `ourH` w poprzednim fragmencie kodu jest następnie operacją <xref:microsoft.quantum.intrinsic.h> , która umożliwia wywoływanie tej wartości podobnie jak każda inna operacja.
Dzięki tej możliwości można pisać operacje, które przyjmują operacje w ramach danych wejściowych, tworząc koncepcje przepływu sterowania wyższego rzędu.
Na przykład można wyobrazić się do operacji "kwadratowych", stosując ją dwa razy do tego samego elementu docelowego qubit.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Zwracanie operacji z funkcji

Ważne jest, aby podkreślić, że można również zwracać operacje w ramach danych wyjściowych, takich jak możliwość izolowania pewnego rodzaju klasycznej logiki warunkowej jako funkcji klasycznej, która zwraca opis programu Quantum w postaci operacji.
W ramach prostego przykładu Rozważmy przykład teleportowego, w którym strona otrzymująca dwubitowy klasyczny komunikat musi użyć komunikatu, aby zdekodować qubit w odpowiedni stan teleportowy.
Można napisać to pod względem funkcji, która pobiera te dwa klasyczne bity i zwraca odpowiednią operację dekodowania.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Ta nowa funkcja jest w rzeczywistości funkcją, w tym przypadku, gdy wywołuje ją z tymi samymi wartościami `hereBit` i `thereBit` , zawsze jest przywracana ta sama operacja.
W związku z tym dekoder może być bezpiecznie uruchamiany wewnątrz operacji bez powodowania, jak logika dekodowania współdziała z definicjami różnych specjalizacji operacji.
Oznacza to, że klasyczna logika wewnątrz funkcji jest izolowana, co gwarantuje kompilatorowi możliwość zmiany kolejności wywołania funkcji z impunity tak długo, jak dane wejściowe są zachowywane.


## <a name="partial-application"></a>Aplikacja częściowa

Można wykonać znacznie więcej dzięki funkcjom, które zwracają operacje przy użyciu *częściowej aplikacji*, w którym można dostarczyć co najmniej jedną część danych wejściowych do funkcji lub operacji bez jej rzeczywistego wywoływania. W poprzednim `ApplyTwice` przykładzie można wskazać, że nie chcesz określać, od razu, do czego qubit powinna być stosowana operacja wejściowa:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

W takim przypadku zmienna lokalna `twiceOp` zawiera częściowo zastosowana operacja `ApplyTwice(op, _)` , gdzie `_` wskazuje części danych wejściowych, które nie zostały jeszcze określone.
Po wywołaniu `twiceOp` w następnym wierszu zostanie przekazane jako dane wejściowe do operacji częściowo zastosowanej wszystkie pozostałe części danych wejściowych do oryginalnej operacji.
W związku z tym poprzedni fragment kodu jest efektywnie identyczny, aby był wywoływany `ApplyTwice(op, target)` bezpośrednio, Zapisz, że wprowadzono nową zmienną lokalną, aby można było opóźnić połączenie, jednocześnie dostarczając niektóre części danych wejściowych.

Ponieważ operacja, która została częściowo zastosowana, nie jest faktycznie wywoływana do momentu podania całego danych wejściowych, można bezpiecznie zastosować częściowe operacje nawet z poziomu funkcji.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

W zasadzie klasyczna logika w ramach `SquareOperation` mogły być znacznie inne, ale nadal jest odizolowana od reszty operacji przez gwarancje, które kompilator może zaoferować na informacje o funkcjach. Standardowa biblioteka Q # korzysta z tego podejścia w celu wyrażenia klasycznego przepływu sterowania w sposób, w jaki programy Quantum mogą łatwo używać.


## <a name="recursion"></a>Rekursja

Liczba wywoływanych Q może być bezpośrednio lub pośrednio cykliczna.
Oznacza to, że operacja lub funkcja może wywołać się sama lub wywołać inne wywołanie, które bezpośrednio lub pośrednio wywołuje operację wywołującą.

Istnieją jednak dwa ważne komentarze dotyczące korzystania z rekursji:

- Użycie rekursji w operacjach może zakłócać pewne optymalizacje.
  Zakłócenia te mogą mieć znaczny wpływ na czas wykonywania algorytmu.
- W przypadku uruchamiania na rzeczywistym urządzeniu Quantum przestrzeń stosu może być ograniczona, a więc Szczegółowa rekursja może prowadzić do błędu czasu wykonywania.
  W szczególności kompilator Q # i środowisko wykonawcze nie identyfikują i nie optymalizują rekursji końcowego.

## <a name="next-steps"></a>Następne kroki

Więcej informacji na temat [zmiennych](xref:microsoft.quantum.guide.variables) w Q #.
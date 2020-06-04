---
title: 'Operacje i funkcje w funkcji Q #'
description: Jak definiować i wywoływać operacje i funkcje, a także wyspecjalizowane specjalizacje operacji.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 9e924b973c4f22a59dd862df3f4f0d70278a1b4e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327802"
---
# <a name="operations-and-functions-in-q"></a>Operacje i funkcje w funkcji Q #

## <a name="defining-new-operations"></a>Definiowanie nowych operacji

Operacje są rdzeniem Q #.
Po zadeklarowaniu można je wywołać z klasycznej aplikacji .NET, np. przy użyciu symulatora lub innych operacji w ramach Q #.
Każda operacja zdefiniowana w Q # może następnie wywołać dowolną liczbę innych operacji, łącznie z wbudowanymi operacjami wewnętrznymi zdefiniowanymi przez język. Określony sposób, w jaki te operacje wewnętrzne są zdefiniowane, zależy od maszyny docelowej.
Po skompilowaniu każda operacja jest reprezentowana jako typ klasy .NET, który można dostarczyć dla maszyn docelowych.

Każdy plik źródłowy Q # może definiować dowolną liczbę operacji.
Nazwy operacji muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktów z nazwami typów lub funkcji.

Deklaracja operacji składa się ze słowa kluczowego `operation` , po którym występuje symbol, który jest nazwą operacji, spójna kolekcja identyfikatorów, która definiuje argumenty do operacji, dwukropek `:` , adnotację typu opisującą typ wyniku operacji, opcjonalnie adnotację z charakterystykami operacji, otwierającym nawiasem klamrowym `{` , treścią deklaracji operacji i końcowym nawiasem zamykającym `}` .

Każda operacja przyjmuje dane wejściowe, tworzy dane wyjściowe i określa Implementację dla co najmniej jednej specjalizacji operacji.
Możliwe specjalizacje oraz sposób definiowania/wywoływania ich, są szczegółowo opisane poniżej.
Na razie Rozważmy następujące operacje, które definiują tylko domyślną specjalizację treści i pobierają pojedyncze qubit jako dane wejściowe, a następnie wywołują wbudowaną <xref:microsoft.quantum.intrinsic.x> operację na tym wejściu:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Słowo kluczowe `operation` rozpoczyna definicję operacji, a po niej następuje nazwa; tutaj, `BitFlip` .
Następnie typ danych wejściowych jest zdefiniowany jako `Qubit` , wraz z nazwą `target` odwołującą się do danych wejściowych w ramach nowej operacji.
Podobnie definiuje, `Unit` że dane wyjściowe operacji są puste.
Jest to podobne do `void` języka C# i innych języków nieużywanych i jest równoważne `unit` w języku F # i innych językach funkcjonalnych.

Operacje mogą również zwracać bardziej interesujące typy niż `Unit` .
Na przykład <xref:microsoft.quantum.intrinsic.m> operacja zwraca dane wyjściowe typu `Result` , reprezentujący wykonywanie pomiaru. Możemy przekazać dane wyjściowe z operacji do innej operacji lub użyć jej przy użyciu `let` słowa kluczowego, aby zdefiniować nową zmienną.

Pozwala to na reprezentowanie klasycznego obliczenia, które współdziała z operacjami Quantum na niskim poziomie, na przykład w przypadku [kodowania w stojaku](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):

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
> Dane wejściowe i wyjściowe są następnie reprezentowane przy użyciu *krotek*, które zbierają wiele wartości w jedną wartość.
> Nieformalnie Załóżmy, że Q # to język "Krotka w poziomie".
> Postępując zgodnie z tym pojęciem, `()` należy go odczytać jako spójną krotkę, która ma typ `Unit` .


## <a name="controlled-and-adjoint-operations"></a>Operacje kontrolowane i sąsiadujące

Jeśli operacja implementuje transformację jednostkową, podobnie jak w przypadku wielu operacji w Q #, można zdefiniować sposób działania operacji podczas *adjointed* lub *kontrolowania*. *Podległych* specjalizacji operacji określa sposób działania "odwrotności" operacji, podczas gdy *kontrolowana* specjalizacja określa, jak działa operacja, gdy jej aplikacja jest kondycjonowana na stanie określonego rejestru Quantum.

Adjoints operacji Quantum są kluczowe dla wielu aspektów przetwarzania Quantum. Dokładniej poniżej, w sekcji [sprzężenia](#conjugations) znajdziesz jedną taką sytuację omówioną wraz z użyteczną techniką programowania Q #.

Kontrolowana wersja operacji jest nową operacją, która efektywnie stosuje operację podstawową tylko wtedy, gdy wszystkie kontrolki qubits są w określonym stanie.
Jeśli kontrolka qubits znajduje się w położeniu, wówczas podstawowa operacja jest stosowana spójnie z odpowiednią częścią położenia.
W ten sposób kontrolowane operacje są często używane do generowania Entanglement.

W naturalny sposób *kontrolowanego* obszaru specjalizacji może istnieć również określenie kontrolowanej aplikacji sąsiadującej operacji.

> [!NOTE]
> Jeśli $U $ to transformacja jednostkowa zaimplementowana przez operację `U` , `Adjoint U` reprezentuje ona transformację jednostkową $U ^ \dagger $, która jest złożonym transpozycję sprzężonej sprzężenia.
> Po zastosowaniu operacji, a następnie jej współdziałaniu do stanu pozostawia stan niezmieniony, tak jak pokazano to jest fakt, że $UU ^ \dagger = U ^ \dagger U = \id $, macierz tożsamości.
> Reprezentacja jednostkowa kontrolowanej operacji jest nieco bardziej złożonych, ale można znaleźć więcej szczegółów na temat [koncepcji przetwarzania Quantum: wielu qubits](xref:microsoft.quantum.concepts.multiple-qubits).

W poniższej sekcji opisano, jak wywoływać różne specjalizacje w kodzie Q.
Poniżej szczegółowo opisano sposób definiowania operacji do ich obsługi.

### <a name="calling-operation-specializations"></a>Wywoływanie specjalizacji operacji

*Funktor* w Q # to fabryka, która definiuje nową operację z innej operacji.
Dwa standardowe funktory w pytaniach Q # są `Adjoint` i `Controlled` .

Funktory mają dostęp do implementacji operacji podstawowej podczas definiowania implementacji nowej operacji.
W ten sposób funktory może wykonywać bardziej złożone funkcje niż tradycyjne funkcje wyższego poziomu. Funktory nie ma reprezentacji w systemie typu Q #. Obecnie nie można powiązać ich ze zmienną lub przekazać ich jako argumenty. 

Funktor jest używany przez zastosowanie go do operacji, zwracając nową operację.
Na przykład operacja będąca wynikiem zastosowania `Adjoint` Funktor do `Y` operacji jest zapisywana jako `Adjoint Y` .
Nowa operacja może następnie zostać wywołana jak każda inna operacja.
Aby operacja obsługiwała zastosowanie `Adjoint` i/lub `Controlled` funktory, jego typ zwracany musi być `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`Funktor

W tym celu program `Adjoint Y(q1)` stosuje Funktor sąsiadujący do `Y` operacji w celu wygenerowania nowej operacji i stosuje tę nową operację do `q1` .
Nowa operacja ma ten sam podpis i typ co operacja podstawowa `Y` .
W szczególności Nowa operacja zezwala również na `Adjoint` użycie i tylko wtedy, `Controlled` gdy operacja podstawowa zakończyła się.
Sąsiadujący Funktor jest własnym odwrotnością; oznacza to, że `Adjoint Adjoint Op` jest zawsze taka sama jak `Op` .

#### <a name="controlled-functor"></a>`Controlled`Funktor

Podobnie program `Controlled X(controls, target)` stosuje kontrolowane Funktor do `X` operacji w celu wygenerowania nowej operacji i stosuje tę nową operację do `controls` i `target` .

> [!NOTE]
> W programie Q # kontrolowane wersje zawsze pobierają tablicę qubits kontroli, a określony stan jest zawsze przeznaczony dla wszystkich kontrolek qubits, które mają być w stanie obliczeniowym ( `PauliZ` ) `One` , $ \ket {1} $.
> Kontrolę w oparciu o inne Stany można osiągnąć przez zastosowanie odpowiedniej operacji jednostkowej do kontrolki qubits przed operacją kontrolowanej, a następnie zastosowanie odwrotności operacji jednostkowej po kontrolowanej operacji.
> Na przykład zastosowanie `X` operacji do kontrolki qubit przed i po kontrolowanej operacji spowoduje, że operacja kontroluje `Zero` stan ($ \ket {0} $) dla tego qubit; stosowanie `H` operacji przed i po kontroli `PauliX` `One` stanu, czyli-1 eigenvalue Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $, a nie w `PauliZ` `One` stanie.

Po otrzymaniu wyrażenia operacji nowe wyrażenie operacji może być utworzone przy użyciu `Controlled` Funktor.
Sygnatura nowej operacji jest oparta na podpisie oryginalnej operacji.
Typ wyniku jest taki sam, ale typ danych wejściowych jest krotką dwukrotną z tablicą qubit, która przechowuje qubit kontrolki jako pierwszy element i argumenty oryginalnej operacji jako drugi element.
Nowa operacja obsługuje `Controlled` i będzie obsługiwać funkcję `Adjoint` if i tylko wtedy, gdy oryginalna operacja zakończyła się.

Jeśli oryginalna Operacja trwała tylko z pojedynczym argumentem, w tym miejscu będzie można odtwarzać pojedynczej korelacji krotek.
Na przykład `Controlled X` jest kontrolowana wersja `X` operacji. 
`X`ma typ `(Qubit => Unit is Adj + Ctl)` , więc `Controlled X` ma typ `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; ze względu na równoważność spójnej kolekcji, jest to taka sama jak `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Jeśli operacja podstawowa wymagała kilku argumentów, pamiętaj, aby ująć odpowiednie argumenty kontrolowanej wersji operacji w nawiasach, aby przekonwertować je na krotkę.
Na przykład `Controlled Rz` jest kontrolowana wersja `Rz` operacji. 
`Rz`ma typ `((Double, Qubit) => Unit is Adj + Ctl)` , więc `Controlled Rz` ma typ `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
W rezultacie będzie `Controlled Rz(controls, (0.1, target))` to poprawne wywołanie `Controlled Rz` (należy zwrócić uwagę na nawiasy `0.1, target` ).

Innym przykładem `CNOT(control, target)` może być implementacja `Controlled X([control], target)` . Jeśli element docelowy powinien być kontrolowany przez 2 Control qubits (CCNOT), możemy użyć `Controlled X([control1, control2], target)` instrukcji.

#### `Controlled Adjoint` 

`Controlled`I `Adjoint` funktory się, więc nie ma różnicy między stosowaniem `Controlled Adjoint Op` lub `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definiowanie kontrolowanych i sąsiadujących implementacji

W pierwszym przykładzie deklaracji operacji, operacje `BitFlip` i `DecodeSuperdense` zostały zdefiniowane z podpisami `(Qubit => Unit)` i `((Qubit, Qubit) => (Result, Result))` odpowiednio.
Jak `DecodeSuperdense` obejmuje pomiary, nie jest operacją jednostkową i w związku z tym nie może istnieć żadne kontrolowane niesąsiadujące specjalizacje (odwołaj powiązane wymaganie, aby ta operacja zwracała `Unit` ).
Jednak `BitFlip` po prostu wykonuje operację jednostkową <xref:microsoft.quantum.intrinsic.x> , możemy ją zdefiniować przy użyciu obu specjalizacji.

W tym miejscu szczegółowo opisano, jak uwzględnić istnienie specjalizacji w deklaracjach operacji Q #, dzięki czemu można je wywołać w połączeniu z `Adjoint` i/lub `Controlled` funktory.
[Poniżej](#circumstances-for-validly-defining-specializations)opisano niektóre sytuacje, w których jest to prawidłowe lub nieprawidłowe, aby zadeklarować specjalizacje.

Charakterystyki operacji definiują, jakie rodzaje funktory można stosować do zadeklarowanej operacji oraz jaki ma wpływ. Istnienie tych specjalizacji może być zadeklarowane jako część podpisu operacji, w odniesieniu do adnotacji z charakterystyką operacji: `is Adj` , `is Ctl` lub `is Adj + Ctl` .
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
W związku z tym możemy użyć tego `DecodeSuperdense` przykładu, aby napisać w powyższym przykładzie więcej kompaktów, przy użyciu sąsiadującej części `PrepareEntangledPair` do przekształcenia stanu Entangled z powrotem do pary unentangled qubits:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Adnotacja z charakterystyką operacji w deklaracji jest przydatna, aby zapewnić, że kompilator automatycznie generuje inne specjalizacje na podstawie domyślnej implementacji. 

Istnieje kilka ważnych ograniczeń, które należy wziąć pod uwagę podczas projektowania operacji do użycia z funktory.
W przypadku niekrytycznej specjalizacji dla operacji korzystającej z wartości wyjściowej żadnej innej operacji *nie może* być automatycznie generowana przez kompilator, ponieważ jest niejednoznaczna w przypadku zmiany kolejności instrukcji w takiej operacji w celu uzyskania tego samego efektu.

W związku z tym często warto jawnie określić różne implementacje.

### <a name="explicitly-specifying-implementations"></a>Jawne określanie implementacji

W przypadku, gdy implementacja nie może zostać wygenerowana przez kompilator, można ją jawnie określić. Takie jawne deklaracje specjalizacji mogą składać się z odpowiedniej *dyrektywy generacji* lub implementacji zdefiniowanej przez użytkownika.
Tutaj udostępniamy pełen zakres możliwości, z poniższymi przykładami.


#### <a name="explicit-specialization-declarations"></a>Jawne deklaracje specjalizacji

Operacje Q # mogą zawierać następujące jawne deklaracje specjalizacji:

- `body`Specjalizacja określa implementację operacji bez zastosowanych funktory.
- `adjoint`Specjalizacja określa implementację operacji z `Adjoint` zastosowaniem Funktor.
- `controlled`Specjalizacja określa implementację operacji z `Controlled` zastosowaniem Funktor.
- `controlled adjoint`Specjalizacja określa implementację operacji z `Adjoint` `Controlled` zastosowaniem zarówno i funktory.
  Ta specjalizacja może być również nazywana `adjoint controlled` , ponieważ dwie funktory.


Specjalizacja operacji składa się z tagu specjalizacji (np. `body` , lub `adjoint` itp.), po którym następuje jeden z:

- Jawna deklaracja opisana poniżej.
- *Dyrektywa* , która informuje kompilator, *jak* generować specjalizację, jeden z:
  - `intrinsic`, co oznacza, że specjalizacja jest udostępniana przez maszynę docelową.
  - `distribute`, które mogą być używane z `controlled` `controlled adjoint` specjalizacjami i.
    Gdy jest używany z `controlled` , wskazuje, że kompilator powinien obliczyć specjalizację, stosując `Controlled` do wszystkich operacji w `body` .
    Gdy jest używany z `controlled adjoint` , wskazuje, że kompilator powinien obliczyć specjalizację przez zastosowanie `Controlled` do wszystkich operacji w `adjoint` specjalizacji.
  - `invert`, co oznacza, że kompilator powinien obliczyć `adjoint` specjalizację, odwracając `body` , tj. odwracanie kolejności operacji i stosując sąsiednie do każdego z nich.
    Gdy jest używany z `adjoint controlled` , oznacza to, że kompilator powinien obliczyć specjalizację, odwracając `controlled` specjalizację.
  - `self`, aby wskazać, że podległych specjalizacji jest taka sama jak `body` specjalizacja.
    Jest to dozwolone dla `adjoint` `adjoint controlled` specjalizacji i.
    W przypadku programu `adjoint controlled` `self` oznacza, że `adjoint controlled` specjalizacja jest taka sama jak `controlled` specjalizacja.
  - `auto`, aby wskazać, że kompilator powinien wybrać odpowiednią dyrektywę, która ma zostać zastosowana.
    `auto`nie można użyć dla `body` specjalizacji.

Dyrektywy i `auto` wszystkie wymagają zamykającego średnika `;` .
`auto`Dyrektywa jest rozpoznawana jako następująca dyrektywa generacji, jeśli określono jawną deklarację `body` :

- `adjoint`Specjalizacja jest generowana zgodnie z dyrektywą `invert` .
- `controlled`Specjalizacja jest generowana zgodnie z dyrektywą `distribute` .
- `adjoint controlled`Specjalizacja jest generowana zgodnie z dyrektywą `invert` , jeśli jawna Deklaracja dla `controlled` jest podano, ale nie dla `adjoint` , i `distribute` w inny sposób.

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

Kod w `PrepareEntangledPair` powyższym przykładzie jest odpowiednikiem poniższego kodu zawierającego jawne deklaracje specjalizacji: 

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

Jeśli kompilator nie może automatycznie wygenerować implementacji dla konkretnej specjalizacji lub można określić bardziej wydajną implementację, implementacja może być również zdefiniowana ręcznie.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
W powyższym przykładzie `adjoint invert;` wskazuje, że jest generowana podległych specjalizacji, odwracając implementację treści, i `controlled adjoint invert;` wskazuje, że kontrolowana podległych specjalizacji ma być generowana przez odwrócenie danej implementacji kontrolowanej specjalizacji.

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

Istnieje możliwość określenia operacji bez wersji sąsiednich lub kontrolowanych. Na przykład operacje pomiarów nie mają żadnego z nich, ponieważ nie są odwracalna ani nie są kontrolowane.

Operacja obsługuje `Adjoint` i/lub funktory, `Controlled` Jeśli jej deklaracja zawiera niejawną lub jawną deklarację odpowiednich specjalizacji.

Jawne zadeklarowane, sąsiadujące/kontrolowane specjalizacje implikuje istnienie podległych/kontrolowanej specjalizacji. 

Dla operacji, której treść zawiera pętle REPEAT-until-Success, Set instrukcje, pomiary, instrukcje Return lub wywołania do innych operacji, które nie obsługują `Adjoint` Funktor, nie jest możliwe wygenerowanie przyległych specjalizacji po `invert` dyrektywie lub `auto` .

Dla operacji, której treść zawiera wywołania do innych operacji, które nie obsługują `Controlled` Funktor, nie jest możliwe wygenerowanie kontrolowanej specjalizacji po `distribute` `auto` dyrektywie lub.

#### <a name="controlled-adjoint"></a>Kontrolowane sąsiadująco

Kontrolowana sąsiadująca wersja operacji określa, jak jest zaimplementowana przeprowadzona przez Quantum wersja sąsiadującej operacji.
Istnieje możliwość określenia operacji bez kontrolowanej wersji sąsiadującej; na przykład operacje pomiarów nie mają kontrolowanej wersji sąsiadującej, ponieważ nie są ani odwracalnae ani nie są dostępne.

Kontrolowana podległych specjalizacji dla operacji musi istnieć, jeśli i tylko wtedy, gdy istnieje zarówno przyległych, jak i kontrolowanych specjalizacji. W takim przypadku istnienie kontrolowanej specjalizacji jest wnioskowane, a odpowiednia specjalizacja jest generowana przez kompilator, jeśli żadna implementacja nie została jawnie zdefiniowana. 

Dla operacji, której treść zawiera wywołania do innych operacji, które nie mają kontrolowanej sąsiedniej wersji, Wygeneruj ponownie podległych specjalizacji po `invert` `distribute` `auto` dyrektywie lub nie jest możliwe.


### <a name="type-compatibility"></a>Zgodność typów

Operacja z dodatkowymi obsługiwanymi funktory może być używana wszędzie tam, gdzie operacja jest mniejsza niż funktory, ale oczekiwano tego samego podpisu.
Na przykład operacja typu `(Qubit => Unit is Adj)` może być używana wszędzie tam, gdzie `(Qubit => Unit)` oczekiwana jest operacja typu.

Q # jest *współwariantem* w odniesieniu do możliwego do zwrócenia typu zwracanego: wywoływany, który zwraca typ `'A` jest zgodny z tym samym typem danych wejściowych i typem wyniku, który `'A` jest zgodny z.

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

spełnione są następujące kwestie:

- Funkcja `ConjugateInvertWith` może zostać wywołana z `inner` argumentem `Invert` lub `ApplyUnitary` .
- Funkcja `ConjugateUnitaryWith` może zostać wywołana z `inner` argumentem `ApplyUnitary` , ale nie `Invert` .
- Wartość typu `(Qubit[] => Unit is Adj + Ctl)` może być zwracana z elementu `ConjugateInvertWith` .

> [!IMPORTANT]
> Q # 0,3 wprowadza znaczną różnicę w zachowaniu typów zdefiniowanych przez użytkownika.

Typy zdefiniowane przez użytkownika są traktowane jako opakowana wersja typu podstawowego, a nie jako podtyp.
Oznacza to, że wartość typu zdefiniowanego przez użytkownika nie jest użyteczna, gdy oczekiwana jest wartość typu podstawowego.


### <a name="conjugations"></a>Liczby sprzężone

W przeciwieństwie do klasycznych bitów zwalnianie pamięci Quantum jest nieco bardziej zamierzone, ponieważ niequbitse Resetowanie może mieć niepożądane skutki dla pozostałych obliczeń, jeśli qubits nadal Entangled. Można to uniknąć przez prawidłowe wykonanie obliczeń przed zwolnieniem pamięci. Typowym wzorcem przetwarzania Quantum jest następujące: 

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

Począwszy od naszego 0,9ej wersji, obsługujemy instrukcję sprzężenia, która implementuje przekształcenie powyżej. Korzystając z tej instrukcji, `ApplyWith` można zaimplementować operację w następujący sposób:

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
Taka instrukcja sprzężona oczywiście jest znacznie bardziej użyteczna, jeśli transformacja zewnętrzna i wewnętrzna nie jest łatwo dostępna jako operacje, ale są bardziej wygodne do opisania przez blok składający się z kilku instrukcji. 

Przekształcenie odwrotne dla instrukcji zdefiniowanych w bloku jest automatycznie generowane przez kompilator i wykonywane po zakończeniu stosu Apply.
Ponieważ żadne zmienne modyfikowalne używane jako część wewnątrz bloku nie mogą być ponownie powiązane w bloku Apply, wygenerowane przekształcenie jest gwarantowane jako sąsiadujące obliczenie w bloku. 


## <a name="defining-new-functions"></a>Definiowanie nowych funkcji

Funkcje są całkowicie deterministyczne, klasyczne procedury w Q #, które różnią się od operacji w tym, że nie mogą mieć żadnych efektów poza obliczaniem wartości wyjściowej.
W szczególności funkcje nie mogą wywoływać operacji; Działaj na, alokuj lub zażycz qubits; Przykładowe liczby losowe; lub w inny sposób zależy od stanu poza wartością wejściową do funkcji.
W związku z tym funkcje Q # są *czyste*, w tym przypadku zawsze mapują te same wartości wejściowe na te same wartości wyjściowe.
Dzięki temu kompilator Q # może bezpiecznie zmienić kolejność i czas wywoływania funkcji podczas generowania specjalizacji operacji.

Każdy plik źródłowy Q # może definiować dowolną liczbę funkcji.
Nazwy funkcji muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktu z nazwami operacji lub typów.

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

Za każdym razem, gdy jest to możliwe, warto napisać klasyczną logikę pod kątem funkcji, a nie operacji, dzięki czemu można łatwiej używać jej w ramach operacji.
Na przykład, jeśli `Square` podano wyżej deklarację jako *operację*, kompilator nie może zagwarantowania, że wywołanie go z tym samym elementem wejściowym spowoduje spójne generowanie tych samych danych wyjściowych.

Aby podkreślić różnicę między funkcjami i operacjami, należy wziąć pod uwagę problem z próbkami klasycznymi losowych, z poziomu operacji Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Za każdym razem `U` , gdy jest wywoływana, będzie ona mieć inną akcję `target` .
W szczególności kompilator nie może zagwarantować, że jeśli dodaliśmy `adjoint auto` deklarację specjalizacji do `U` , `U(target); Adjoint U(target);` działa jako tożsamość (to oznacza, że jako No-op).
Jest to naruszone w przypadku [wektorów i macierzy](xref:microsoft.quantum.concepts.vectors), takich jak automatyczne generowanie przyległych specjalizacji w operacji, w której wywołano operację, <xref:microsoft.quantum.math.randomreal> spowodowałoby to przerwanie gwarancji dostarczonych przez kompilator; <xref:microsoft.quantum.math.randomreal> jest operacją, dla której nie istnieje przyległych lub kontrolowana wersja.

Z drugiej strony, co pozwala na bezpieczne wywoływanie funkcji `Square` , w którym kompilator może mieć pewność, że tylko należy zachować dane wejściowe, aby `Square` zachować trwałość danych wyjściowych.
W ten sposób izolowanie możliwie największej logiki w ramach funkcji pozwala łatwo ponownie wykorzystać tę logikę w innych funkcjach i operacjach.


## <a name="generic-type-parameterized-callables"></a>Typy ogólne (sparametryzowane od typu)

Wiele funkcji i operacji, które firma Microsoft może chcieć zdefiniować, nie opiera się na typach ich danych wejściowych, ale raczej niejawnie używa ich typów za pośrednictwem innej funkcji lub operacji.
Rozważmy na przykład, że koncepcja *mapy* jest wspólna dla wielu języków funkcjonalnych; dana funkcja $f (x) $ i Kolekcja wartości $ \{ x_1, x_2, \dots, x_n \} $, map zwraca nową kolekcję $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.
W celu zaimplementowania tego zadania w programie Q # można skorzystać z tej funkcji jako pierwszej klasy.
Napiszmy do krótkiego przykładu `Map` , używając ★ jako symbolu zastępczego, a my powiemy, jakich typów potrzebujemy.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Należy zauważyć, że ta funkcja wygląda bardzo podobnie niezależnie od tego, jakie rzeczywiste typy zostały zastąpione.
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

W zasadzie można napisać wersję `Map` dla każdej pary typów, które napotykamy, ale wprowadzamy wiele problemów.
Na przykład jeśli znajdziesz usterkę w programie `Map` , musimy upewnić się, że poprawka jest stosowana jednolicie we wszystkich wersjach programu `Map` .
Ponadto, jeśli tworzymy nową spójną krotkę lub UDT, musimy teraz utworzyć nową, `Map` Aby przejść do nowego typu.
Chociaż jest to pozyskanie dla niewielkiej liczby takich funkcji, ponieważ zbieramy więcej i więcej funkcji tego samego formularza co `Map` , koszt wprowadzenia nowych typów stanie się nieuzasadniony w bardzo krótkim czasie.

Większość tego rodzaju trudności wynika jednak z tego, że kompilator nie udostępnił informacji niezbędnych do rozpoznania, w jaki sposób `Map` są powiązane różne wersje.
Efektywnie, chcemy, aby kompilator traktował `Map` jako rodzaj funkcji matematycznej z *typów* q # do funkcji q #.

Pojęcie to jest formalne przez umożliwienie funkcjom i operacjom posiadania *parametrów typu*, a także ich zwykłych parametrów krotek.
W powyższych przykładach chcemy traktować `Map` jako parametry typu `Int, Pauli` w pierwszym przypadku i `Double, String` w drugim przypadku.
W większości przypadków te parametry typu mogą być używane tak, jakby były typami zwyczajnymi: używamy wartości parametrów typu do wprowadzania tablic i krotek, wywoływania funkcji i operacji oraz przypisywania do zmiennych normalnych lub modyfikowalnych.

> [!NOTE]
> Największą sytuacją pośrednią jest to, że qubits, w którym program Q # nie może bezpośrednio polegać na strukturze `Qubit` typu, ale **musi** przekazać takie typy do innych operacji i funkcji.

Powracając do powyższego przykładu, możemy zobaczyć, że musimy `Map` mieć parametry typu, jeden do reprezentowania danych wejściowych `fn` i jeden do reprezentowania danych wyjściowych `fn` .
W polu Q # jest to zapisywana przez dodanie nawiasów kątowych ( `<>` nie brakets $ \braket {} $!) po nazwie funkcji lub operacji w jej deklaracji oraz przez wystawienie poszczególnych parametrów typu.
Nazwa każdego parametru typu musi rozpoczynać się od osi `'` , wskazując, że jest parametrem typu, a nie zwykłym typem (znanym także jako *konkretny* typ).
W `Map` tym celu napiszemy:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Należy zauważyć, że definicja `Map<'Input, 'Output>` wygląda bardzo podobna do wersji, które zostały wcześniej napisane.
Jedyną różnicą jest to, że został jawnie poinformowany kompilator, który `Map` nie zależy bezpośrednio od tego `'Input` , co `'Output` jest `fn`
Po zdefiniowaniu `Map<'Input, 'Output>` w ten sposób możemy ją wywoływać, ponieważ była to funkcja zwykła:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Pisanie funkcji ogólnych i operacji to jedno miejsce, w którym "krotka spójna z krotką" to bardzo użyteczny sposób, aby myśleć o funkcjach i operacjach pytań i odpowiedzi.
> Ponieważ każda funkcja przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście, dane wejściowe typu `'T -> 'U` dopasowują *dowolną* funkcję Q #.
> Podobnie każda operacja może zostać przeniesiona do wejściowego typu `'T => 'U` .

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
Alternatywnie, możemy dodać parametry typu do `Compose` , które wskazują, że działa dla *dowolnego* `A` , `B` i `C` , tak długo, jak te parametry są zgodne z oczekiwanymi przez `innerFn` i `outerFn` :

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

Wartość zmiennej `ourH` w powyższym fragmencie kodu jest następnie operacją <xref:microsoft.quantum.intrinsic.h> , która umożliwia wywołanie tej wartości podobnie jak każda inna operacja.
Dzięki temu możemy pisać operacje, które przyjmują operacje w ramach danych wejściowych, tworząc koncepcje przepływu sterowania wyższego rzędu.
Na przykład możemy Wyobraź sobie, że chcemy "kwadratowych" operacji, stosując ją dwa razy do tego samego elementu docelowego qubit.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Zwracanie operacji z funkcji

Podkreślamy, że możemy również zwrócić operacje w ramach danych wyjściowych, dzięki czemu można izolować pewne rodzaje klasycznej logiki warunkowej jako funkcję klasyczną, która zwraca opis programu Quantum w postaci operacji.
W ramach prostego przykładu Rozważmy przykład teleportowego, w którym strona otrzymująca dwubitowy klasyczny komunikat musi użyć komunikatu, aby zdekodować qubit w odpowiedni stan teleportowy.
Możemy napisać to pod względem funkcji, która pobiera te dwa klasyczne bity i zwraca odpowiednią operację dekodowania.

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

Ta nowa funkcja jest w rzeczywistości funkcją, w tym przypadku, gdy wywołamy ją z tymi samymi wartościami `hereBit` i `thereBit` , zawsze będziemy wrócić do tej samej operacji.
W związku z tym dekoder może być bezpiecznie uruchamiany wewnątrz operacji bez powodowania, jak logika dekodowania współdziała z definicjami różnych specjalizacji operacji.
Oznacza to, że w funkcji jest izolowana klasyczna logika, która gwarantuje, że wywołanie funkcji można zmienić przy użyciu impunity, tak długo, jak dane wejściowe są zachowywane.


## <a name="partial-application"></a>Aplikacja częściowa

Możemy znacznie bardziej robić dzięki funkcjom, które zwracają operacje przy użyciu *częściowej aplikacji*, w którym możemy dostarczyć co najmniej jedną część danych wejściowych do funkcji lub operacji bez jej rzeczywistego wywoływania. Na przykład, odwołując się do `ApplyTwice` powyższego przykładu, możemy wskazać, że nie chcemy, aby qubit operacji wejściowej:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

W takim przypadku zmienna lokalna `twiceOp` przechowuje częściowo zastosowaną operację, w `ApplyTwice(op, _)` której części danych wejściowych, które nie zostały jeszcze określone, są wskazywane przez `_` .
Gdy rzeczywiście wywołujemy `twiceOp` w następnym wierszu, przekazujemy jako dane wejściowe do operacji częściowo zastosowanej wszystkie pozostałe części danych wejściowych do oryginalnej operacji.
W związku z tym powyższym fragmentem jest efektywnie identyczny, aby był wywoływany `ApplyTwice(op, target)` bezpośrednio, Zapisz, że wprowadziliśmy nową zmienną lokalną, która pozwala nam opóźniać wywołanie, jednocześnie dostarczając niektóre części danych wejściowych.

Ponieważ operacja, która została częściowo zastosowana, nie jest faktycznie wywoływana do momentu udostępnienia całego danych wejściowych, możemy bezpiecznie zastosować operacje nawet z poziomu funkcji.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

W zasadzie klasyczna logika w ramach `SquareOperation` mogły być znacznie inne, ale nadal jest odizolowana od reszty operacji przez gwarancje, które kompilator może zaoferować na informacje o funkcjach.
Ta metoda zostanie użyta w całej standardowej bibliotece Q # do wyrażenia klasycznego przepływu sterowania w sposób, który może być łatwo używany w ramach programów Quantum.


## <a name="recursion"></a>Rekursja

Liczba wywoływanych Q może być bezpośrednio lub pośrednio cykliczna.
Oznacza to, że operacja lub funkcja może wywołać się sama lub wywołać inne wywołanie, które bezpośrednio lub pośrednio wywołuje operację, którą można wywołać.

Istnieją jednak dwa ważne komentarze dotyczące korzystania z rekursji:

- Użycie rekursji w operacjach może zakłócać pewne optymalizacje.
  Może to mieć znaczny wpływ na czas wykonywania algorytmu.
- W przypadku wykonywania na rzeczywistym urządzeniu Quantum przestrzeń stosu może być ograniczona, a więc Szczegółowa rekursja może prowadzić do błędu czasu wykonywania.
  W szczególności kompilator Q # i środowisko wykonawcze nie identyfikują i nie optymalizują rekursji końcowego.

## <a name="next-steps"></a>Następne kroki

Więcej informacji na temat [zmiennych](xref:microsoft.quantum.guide.variables) w Q #.
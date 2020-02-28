---
title: 'Struktura pliku Q #'
description: 'Dowiedz się, jak struktury przestrzeni nazw, operacji, funkcji i deklaracji typu zdefiniowanego przez użytkownika w programie Q # programy i biblioteki.'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b4bb7d4d70677dbd5d921a9f68313760499a56a1
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907396"
---
# <a name="file-structure"></a>Struktura plików

Plik Q # składa się z sekwencji nazw deklaracji.
Każda deklaracja przestrzeni nazw zawiera deklaracje dla typów, operacji i funkcji zdefiniowanych przez użytkownika.
Deklaracja przestrzeni nazw może zawierać dowolną liczbę typów deklaracji i w dowolnej kolejności.
Jedynym tekstem, który może występować poza deklaracją przestrzeni nazw, jest komentarz.
W szczególności Komentarze do dokumentacji dla przestrzeni nazw poprzedzają deklarację.

## <a name="namespace-declarations"></a>Deklaracje przestrzeni nazw

Plik Q # zazwyczaj ma dokładnie jedną deklarację przestrzeni nazw, ale może mieć wartość None (i być pusty lub zawierać komentarze) lub może zawierać wiele przestrzeni nazw.
Deklaracje przestrzeni nazw nie mogą być zagnieżdżane.

Ta sama przestrzeń nazw może być zadeklarowana w wielu plikach Q #, które są kompilowane razem, o ile nie istnieją deklaracje typu, operacji lub funkcji o tej samej nazwie.
W szczególności nie można zdefiniować tego samego typu w tej samej przestrzeni nazw w wielu plikach, nawet jeśli deklaracje są identyczne.

Deklaracja przestrzeni nazw składa się ze słowa kluczowego `namespace`, a po nim nazwy przestrzeni nazw, otwartego nawiasu `{`klamrowego, deklaracji zawartych w przestrzeni nazw i zamykającego nawiasu klamrowego `}`.
Nazwy przestrzeni nazw są zgodne ze wzorcem .NET sekwencji jednego lub więcej symboli dozwolonych, oddzielonych kropkami `.`.
Na przykład `MyQuantumStuff` i `Microsoft.Quantum.Canon` są prawidłowymi nazwami przestrzeni nazw.
Według Konwencji symbole w nazwie przestrzeni nazw są pisane wielkimi literami, ale nie jest to wymagane.

Deklaracje mogą pojawiać się w dowolnej kolejności w deklaracji przestrzeni nazw.
Odwołania do typów lub wartości, które zostały zadeklarowane w sposób nieokreślony w pliku, są rozwiązywane prawidłowo; nie ma potrzeby składania deklaracji typu, operacji lub funkcji przed odwołaniem do niej.

## <a name="open-directives"></a>Otwarte dyrektywy

W bloku przestrzeni nazw dyrektywa `open` może służyć do zaimportowania wszystkich typów i dożądanych nazw zdefiniowanych w określonym zakresie oraz odwoływania się do nich za pomocą niekwalifikowanej nazwy. 

Taka `open` dyrektywa składa się ze słowa kluczowego `open`, a następnie przestrzeni nazw do otwarcia i kończącego się średnika.

Na przykład,

```qsharp
open Microsoft.Quantum.Canon;
```

Opcjonalnie, krótka nazwa otwartej przestrzeni nazw może być zdefiniowana, tak że wszystkie elementy z tej przestrzeni nazw mogą (i muszą) być kwalifikowane przez zdefiniowaną krótką nazwę. Taka krótka nazwa jest definiowana przez dodanie słowa kluczowego `as`, po którym następuje żądana krótka nazwa przed średnikiem w dyrektywie `open`:

```qsharp
open Microsoft.Quantum.Math as Math;
```

Wszystkie dyrektywy `open` muszą występować przed dowolnymi deklaracjami `function`, `operation`lub `newtype` w bloku przestrzeni nazw.
Dyrektywa `open` ma zastosowanie do całego bloku przestrzeni nazw w pliku.

## <a name="user-defined-type-declarations"></a>Deklaracje typu zdefiniowanego przez użytkownika

Polecenie Q # zapewnia użytkownikom sposób deklarowania nowych typów zdefiniowanych przez użytkownika, zgodnie z opisem w sekcji [model typu Q #](xref:microsoft.quantum.language.type-model) .
Typy zdefiniowane przez użytkownika są różne, nawet jeśli typy podstawowe są identyczne.
W szczególności nie istnieje Automatyczna konwersja między wartościami dwóch typów zdefiniowanych przez użytkownika, nawet jeśli typy bazowe są identyczne.

Deklaracja typu zdefiniowanego przez użytkownika składa się ze słowa kluczowego `newtype`, po którym następuje nazwa typu zdefiniowanego przez użytkownika, `=`, prawidłowej specyfikacji typu i kończącego się średnika.

Na przykład:

```qsharp
newtype PairOfInts = (Int, Int);
```

Każdy plik źródłowy Q # może deklarować dowolną liczbę typów zdefiniowanych przez użytkownika.
Nazwy typów muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktów z nazwami operacji i funkcji.

Nie można definiować zależności cykliczne między typami zdefiniowanymi przez użytkownika. W takim przypadku typy cykliczne nie są w tym przypadku dostępne w programie Q #.

## <a name="operation-declarations"></a>Deklaracje operacji

Operacje są rdzeniem Q #, w przybliżeniu analogiczne do funkcji w innych językach.
Każdy plik źródłowy Q # może definiować dowolną liczbę operacji.

Nazwy operacji muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktów z nazwami typów i funkcji.

Deklaracje operacji składają się ze słowa kluczowego `operation`, po którym występuje symbol, który jest nazwą operacji, spójna kolekcja identyfikatorów, która definiuje argumenty do operacji, dwukropek `:`, adnotację typu opisującą typ wyniku operacji, opcjonalnie adnotację z charakterystykami operacji, otwierającą nawias `{`klamrowy, treść deklaracji operacji i końcowy nawias zamykający `}`.

Treść deklaracji operacji obejmuje domyślną implementację lub listę specjalizacji.
Implementację domyślną można określić bezpośrednio w deklaracji, jeśli tylko implementacja specjalizacji treści domyślnej musi być określona jawnie.
W takim przypadku Adnotacja z charakterystyką operacji w deklaracji jest przydatna do zapewnienia, że kompilator automatycznie generuje inne specjalizacje na podstawie domyślnej implementacji. 

Na przykład 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

Charakterystyki operacji definiują, jakie rodzaje funktory można stosować do zadeklarowanej operacji oraz jaki ma wpływ. Jeśli operacja implementuje transformację jednostkową, można zdefiniować sposób działania operacji przy *adjointed* lub *kontrolowanej*.
Istnienie tych specjalizacji może być zadeklarowane jako część podpisu operacji. Odpowiednia implementacja dla każdej takiej niejawnie zadeklarowanej specjalizacji jest generowana przez kompilator. W powyższym przykładzie, współdzielone, kontrolowane i kontrolowane specjalizacje są generowane przez kompilator. 

W przypadku, gdy implementacja nie może zostać wygenerowana przez kompilator, można ją jawnie określić. Takie jawne deklaracje specjalizacji mogą składać się z odpowiedniej dyrektywy generacji, która wyjaśnia, w jaki sposób można skompilować konkretną specjalizację lub implementację zdefiniowaną przez użytkownika. Kod w `PrepareEntangledPair` powyżej na przykład jest odpowiednikiem poniższego kodu zawierającego jawne deklaracje specjalizacji: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
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
Jeśli kompilator nie może wygenerować implementacji dla określonej specjalizacji bez dalszych instrukcji, takich jak dokładniejsza dyrektywa generacji — lub jeśli można podać bardziej wydajną implementację, implementacja może być również zdefiniowana ręcznie.

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

W powyższym przykładzie `adjoint invert;` wskazuje, że jest generowana podległych specjalizacji, przez odwrócenie implementacji treści, a `controlled adjoint invert;` wskazuje, że kontrolowana podległych specjalizacji ma być generowana przez odwrócenie danej implementacji kontrolowanej specjalizacji.

Aby można było wykonać operację do obsługi aplikacji `Adjoint` i/lub `Controlled` Funktor, jego typ zwracany musi być `Unit`. 


### <a name="explicit-specialization-declarations"></a>Jawne deklaracje specjalizacji

Operacje Q # mogą zawierać następujące jawne deklaracje specjalizacji:

- Specjalizacja `body` określa implementację operacji bez zastosowania funktory.
- Specjalizacja `adjoint` określa implementację operacji z zastosowaniem `Adjoint` Funktor.
- Specjalizacja `controlled` określa implementację operacji z zastosowaniem `Controlled` Funktor.
- Specjalizacja `controlled adjoint` określa implementację operacji z zastosowaniem zarówno `Adjoint`, jak i `Controlled` funktory.
  Ta specjalizacja może być również nazywana `adjoint controlled`, ponieważ dwie funktory.


Specjalizacja operacji składa się z tagu specjalizacji (np. `body`lub `adjoint`itp.), po którym następuje jedno z:

- Jawna deklaracja opisana poniżej.
- Dyrektywa, która informuje kompilator, jak generować specjalizację, jeden z:
  - `intrinsic`, co oznacza, że specjalizacja jest udostępniana przez maszynę docelową.
  - `distribute`, które mogą być używane z specjalizacjami `controlled` i `controlled adjoint`.
    Gdy jest używany z `controlled`, wskazuje, że kompilator powinien obliczyć specjalizację, stosując `Controlled` do wszystkich operacji w `body`.
    Gdy jest używany z `controlled adjoint`, wskazuje, że kompilator powinien obliczyć specjalizację, stosując `Controlled` do wszystkich operacji w `adjoint` specjalizacji.
  - `invert`, który wskazuje, że kompilator powinien obliczyć `adjoint` specjalizacji przez odwrócenie `body`, czyli odwracanie kolejności operacji i stosowanie sąsiadujących do nich.
    Gdy jest używany z `adjoint controlled`, oznacza to, że kompilator powinien obliczyć specjalizację, odwracając specjalizację `controlled`.
  - `self`w celu wskazania, że specjalizacja jest taka sama jak specjalizacja `body`.
    Jest to dozwolone w przypadku specjalizacji `adjoint` i `adjoint controlled`.
    W przypadku `adjoint controlled``self` oznacza, że specjalizacja `adjoint controlled` jest taka sama jak specjalizacja `controlled`.
  - `auto`, aby wskazać, że kompilator powinien wybrać odpowiednią dyrektywę, która ma zostać zastosowana.
    nie można użyć `auto` dla specjalizacji `body`.

Dyrektywy i `auto` wszystkie wymagają zamykającego średnika `;`.
Dyrektywa `auto` jest rozpoznawana jako następująca dyrektywa generacji, jeśli podano jawną deklarację `body`:

- Specjalizacja `adjoint` jest generowana zgodnie z dyrektywą `invert`.
- Specjalizacja `controlled` jest generowana zgodnie z dyrektywą `distribute`.
- Specjalizacja `adjoint controlled` jest generowana zgodnie z dyrektywą `invert`, jeśli jawna Deklaracja dla `controlled` jest podano, ale nie dla `adjoint`, i `distribute` w przeciwnym razie.

> [!TIP]   
> Jeśli operacja jest samodzielna, należy jawnie określić podległych lub kontrolowanej specjalizacji za pośrednictwem dyrektywy Generation `self`, aby umożliwić kompilatorowi użycie tych informacji do celów optymalizacji.

Deklaracja specjalizacji, która zawiera implementację zdefiniowaną przez użytkownika, składa się z krotki argumentu, po której następuje blok instrukcji z kodem Q #, który implementuje specjalizację.
Na liście argumentów `...` jest używany do reprezentowania argumentów zadeklarowanych dla operacji jako całości.
Dla `body` i `adjoint`lista argumentów powinna być zawsze `(...)`; dla `controlled` i `adjoint controlled`lista argumentów powinna być symbolem, który reprezentuje tablicę kontrolki qubits, a następnie `...`ujętą w nawiasy. na przykład `(controls,...)`.

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

### <a name="adjoint"></a>Sąsiadująco

Sąsiadująca operacja określa sposób, w jaki jest zaimplementowana złożona funkcja transpozycji sprzężonej operacji. oznacza to, jak działa operacja, gdy "Uruchom w odwrotnie".
Jest to możliwe, aby określić operację niesąsiadującą; na przykład operacje pomiarów nie mają sąsiadujących, ponieważ nie są odwracalna.
Operacja obsługuje `Adjoint` Funktor, jeśli jej deklaracja zawiera niejawną lub jawną deklarację specjalizacji.
Jawne zadeklarowane, kontrolowane podległych specjalizacji oznacza istnienie podległych specjalizacji. 

Dla operacji, której treść zawiera pętle REPEAT-until-Success, Set instrukcje, pomiary, instrukcje Return lub wywołania do innych operacji, które nie obsługują `Adjoint` Funktor, Autogenerowanie podległych specjalizacji po `invert` lub `auto` dyrektywie nie jest możliwe.

### <a name="controlled"></a>Kontrolowane

Kontrolowana wersja operacji określa, w jaki sposób jest zaimplementowana przeprowadzona przez Quantum wersja operacji, czyli sposób działania operacji po zastosowaniu warunku na stanie rejestru Quantum.
Dokładniejszy opis znajduje się w sekcji [kontrolowanej](xref:microsoft.quantum.language.type-model#controlled) .

Istnieje możliwość określenia operacji bez kontrolowanej wersji; na przykład operacje pomiarów nie mają kontrolowanej wersji, ponieważ nie można ich kontrolować.
Operacja obsługuje `Controlled` Funktor if i tylko wtedy, gdy jej deklaracja zawiera niejawną lub jawną deklarację kontrolowanej specjalizacji.
Jawne zadeklarowane, kontrolowane podległych specjalizacji implikuje istnienie kontrolowanej specjalizacji. 

Dla operacji, której treść zawiera wywołania do innych operacji, które nie obsługują `Controlled` Funktor, nie jest możliwe wygenerowanie kontrolowanej specjalizacji po dyrektywie `distribute` lub `auto`.

### <a name="controlled-adjoint"></a>Kontrolowane sąsiadująco

Kontrolowana sąsiadująca wersja operacji określa, jak jest zaimplementowana przeprowadzona przez Quantum wersja sąsiadującej operacji.
Istnieje możliwość określenia operacji bez kontrolowanej wersji sąsiadującej; na przykład operacje pomiarów nie mają kontrolowanej wersji sąsiadującej, ponieważ nie są ani odwracalnae ani nie są dostępne.

Kontrolowana podległych specjalizacji dla operacji musi istnieć, jeśli i tylko wtedy, gdy istnieje zarówno przyległych, jak i kontrolowanych specjalizacji. W takim przypadku istnienie kontrolowanej specjalizacji jest wnioskowane, a odpowiednia specjalizacja jest generowana przez kompilator, jeśli żadna implementacja nie została jawnie zdefiniowana. 

W przypadku operacji, której treść zawiera wywołania do innych operacji, które nie mają kontrolowanej sąsiedniej wersji, należy ją wygenerować przy użyciu autospecjalizacji następującego po `invert`, `distribute` lub `auto` dyrektywie nie jest możliwe.


### <a name="examples"></a>Przykłady

Deklaracja operacji może być prosta jako następująca, która definiuje pierwotną operację Pauli X:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

Poniżej definiuje operację teleport.

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>Deklaracje funkcji

Funkcje są czysto klasycznymi procedurami w Q #.
Każdy plik źródłowy Q # może definiować dowolną liczbę funkcji.

Deklaracja funkcji składa się z `function`słowa kluczowego, po którym następuje symbol, który jest nazwą funkcji, krotką o identyfikatorze wpisanej, adnotacją typu opisującą typ zwracany funkcji i blokiem instrukcji opisującym implementację funkcji.

Blok instrukcji definiujący funkcję musi być ujęty w `{` i `}` jak każdy inny blok instrukcji.

Nazwy funkcji muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktu z nazwami operacji i typów.
Funkcje nie mogą przydzielić ani zażyczyć qubits lub wywoływać operacji. Częściowe stosowanie operacji lub przekazywanie wartości z wartościami z określonym typem operacji jest dokładne.

Na przykład:

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

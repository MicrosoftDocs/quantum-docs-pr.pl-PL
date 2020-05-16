---
title: 'Zmienne w Q #'
description: Opis wypełnienia
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430904"
---
# <a name="variables-in-q"></a>Zmienne w Q #

Polecenie Q # rozróżnia symbole modyfikowalne i zmienne, czyli "zmienne", które są powiązane/przypisane do wyrażeń.
Ogólnie rzecz biorąc, zaleca się użycie niezmiennych symboli, ponieważ umożliwia kompilatorowi wykonywanie większej optymalizacji.

Lewa strona powiązania składa się z krotki symboli i prawej strony wyrażenia.

## <a name="immutable-variables"></a>Zmienne niezmienne

Wartość dowolnego typu w Q # można przypisać do zmiennej do ponownego użycia w ramach operacji lub funkcji za pomocą `let` słowa kluczowego.

Niezmienne powiązanie składa się ze słowa kluczowego `let` , a po nim symbolu lub krotki symboli, znaku równości `=` , wyrażenia służącego do powiązania symboli z i kończącego się średnika.

Przykład:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Przypisuje określoną tablicę operatorów Pauli do nazwy zmiennej (lub "symbol"), `measurementOperator` .

> [!NOTE]
> Nie trzeba jawnie określać typu naszej nowej zmiennej, ponieważ wyrażenie po prawej stronie `let` instrukcji jest niejednoznaczne i typ jest wnioskowany przez kompilator. 

Zmienne zdefiniowane przy użyciu `let` są *niezmienne*, co oznacza, że po jego zdefiniowaniu nie można już zmieniać w jakikolwiek sposób.
Pozwala to na kilka optymalizacji, w tym optymalizację klasycznej logiki działającej na zmienne, które mają być zmieniane w celu zastosowania `Adjoint` wariantu operacji.

## <a name="mutable-variables"></a>Zmienne modyfikowalne

Alternatywnie, aby utworzyć zmienną za pomocą `let` `mutable` słowa kluczowego, zostanie utworzona zmienna modyfikowalna, którą *można* ponownie powiązać po jej początkowym utworzeniu za pomocą `set` słowa kluczowego.

Symbole zadeklarowane i powiązane jako część `mutable` instrukcji mogą być ponownie powiązane z inną wartością w kodzie. Jeśli symbol zostanie powiązana później w kodzie, jego typ nie ulegnie zmianie, a nowo związana wartość musi być zgodna z tym typem.

### <a name="rebinding-of-mutable-symbols"></a>Ponowne wiązanie modyfikowalnych symboli

Zmienna modyfikowalna może być powiązana przy użyciu `set` instrukcji.
Takie ponowne powiązanie składa się ze słowa kluczowego `set` , po którym następuje ciąg lub krotka symboli, znak równości `=` , wyrażenie służące do ponownego powiązania symboli z i kończący średnik.

Tutaj udostępniamy niektóre możliwe przykłady technik rebind instrukcji

### <a name="apply-and-reassign-statements"></a>Instrukcje Apply i Reassign

Szczególnym rodzajem `set` instrukcji, do których odwołuje się jako instrukcja *apply-and-Reassign* , stanowi wygodny sposób łączenia, jeśli prawa strona składa się z aplikacji operatora binarnego, a wynik jest przełączany do lewego argumentu operatora. Na przykład:
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
zwiększa wartość licznika `counter` w każdej iteracji `for` pętli. Powyższy kod jest równoważny z 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Podobne instrukcje są dostępne dla wszystkich operatorów binarnych, w których typ po lewej stronie jest zgodny z typem wyrażenia. Pozwala to na przykład wygodny sposób na gromadzenie wartości.

Załóżmy na przykład, że `qubits` jest to REGSITER qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a>Instrukcje Update-and-Reassign

Podobne łączenie istnieje dla [wyrażeń Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) po prawej stronie.
Istnieją odpowiednie instrukcje *Update-and-Reassign* dla *nazwanych elementów* w typach zdefiniowanych przez użytkownika, a także dla *elementów tablicy*.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

W przypadku tablic [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) w naszych bibliotekach standardowych dostępne są niezbędne narzędzia do wykonywania wielu typowych operacji inicjowania tablic i manipulowania nimi, co pozwala uniknąć konieczności aktualizowania elementów tablicy w pierwszym miejscu. 

Instrukcje Update-and-Reassign oferują alternatywę w razie konieczności:

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

Za pomocą narzędzi biblioteki dla tablic dostępnych w programie [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) możemy na przykład łatwo zdefiniować funkcję zwracającą tablicę Paul, gdzie Pauli przy indeksie `i` przyjmuje daną wartość, a wszystkie inne wpisy są tożsamością.

Poniżej przedstawiono dwie definicje takich funkcji, a drugie korzystanie z narzędzi na tym etapie.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

Zamiast przeiterować każdy indeks w tablicy i warunkowo ustawić go na `PauliI` lub `Pauli` , zamiast tego można użyć `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) do tworzenia tablicy `PauliI` , a następnie po prostu zwrócić wyrażenie Copy-and-Update, w którym zmieniono wartość specifc w indeksie `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Dekonstrukcja krotki

Oprócz przypisywania pojedynczej zmiennej `let` i `mutable` słów kluczowych---lub w rzeczywistości każda inna konstrukcja powiązania, taka jak `set` opisana poniżej),---również zezwalać na rozpakowywanie zawartości [typu krotki](xref:microsoft.quantum.guide.types#tuple-types).
Przypisanie tego formularza jest określane w celu *odtworzenia* elementów tej krotki.

Jeśli po prawej stronie powiązania jest krotka, ta krotka może zostać rozbudowana po przypisaniu.
Takie dekonstrukcji mogą dotyczyć krotek zagnieżdżonych, a każda pełna lub częściowa dekonstrukcja jest prawidłowa, o ile kształt krotki po prawej stronie jest zgodny z kształtem krotki symboli.

Przykład:

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>Zakresy powiązań

Ogólnie rzecz biorąc, powiązania symboli wykraczają poza zakres i stają się nieaktywne na końcu bloku instrukcji, w którym występują.
Istnieją dwa wyjątki od tej reguły:

- Powiązanie zmiennej pętli `for` pętli jest w zakresie dla treści pętli for, ale nie po końcu pętli.
- Wszystkie trzy części `repeat` / `until` pętli (treść, test i naprawa) są traktowane jako pojedynczy zakres, dlatego symbole, które są powiązane z treścią, są dostępne w teście i w naprawie.

W przypadku obu typów pętli każdy przechodzi przez pętlę do własnego zakresu, dlatego powiązania z wcześniejszych przebiegów nie są dostępne w późniejszym przebiegu.
Szczegółowe informacje o tych pętlach można znaleźć w [przepływie sterowania](xref:microsoft.quantum.guide.controlflow).

Powiązania symboli z bloków zewnętrznych są dziedziczone przez bloki wewnętrzne.
Symbol może być powiązany tylko raz na blok; nie można zdefiniować symbolu o takiej samej nazwie jak inny symbol znajdujący się w zakresie (bez "przesłaniania").
Następujące sekwencje byłyby dozwolone:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

oraz

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

Może to jednak być niedozwolone:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

w takim przypadku:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="whats-next"></a>Co dalej?
Dowiedz się więcej na temat [pracy z Qubits w usłudze](xref:microsoft.quantum.guide.qubits) Q #.
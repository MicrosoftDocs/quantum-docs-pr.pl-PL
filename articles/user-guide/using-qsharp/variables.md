---
title: 'Zmienne w Q #'
description: Opis wypełnienia
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 08301f408dcb2211ba25c582a5e5aa43310b714a
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885284"
---
# <a name="variables-in-q"></a>Zmienne w Q #

Polecenie Q # rozróżnia symbole modyfikowalne i niezmienne, czyli *zmienne*, które są powiązane/przypisane do wyrażeń.
Ogólnie rzecz biorąc, zaleca się użycie niezmiennych symboli, ponieważ umożliwia kompilatorowi wykonywanie większej optymalizacji.

Lewa strona powiązania składa się z krotki symboli i prawej strony wyrażenia.

## <a name="immutable-variables"></a>Zmienne niezmienne

Można przypisać wartość dowolnego typu w Q # do zmiennej do ponownego użycia w ramach operacji lub funkcji za pomocą `let` słowa kluczowego. 

Niezmienne powiązanie składa się ze słowa kluczowego `let` , a po nim symbolu lub krotki symboli, znaku równości `=` , wyrażenia służącego do powiązania symboli z i kończącego się średnika.

Przykład:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Przypisuje określoną tablicę operatorów Pauli do nazwy zmiennej (lub "symbol"), `measurementOperator` .

> [!NOTE]
> W poprzednim przykładzie nie ma potrzeby jawnego określania typu nowej zmiennej, ponieważ wyrażenie po prawej stronie `let` instrukcji jest niejednoznaczne, a kompilator wnioskuje właściwy typ. 

Zmienne zdefiniowane przy użyciu `let` są *niezmienne*, co oznacza, że po jego zdefiniowaniu nie można już zmieniać w żaden sposób.
Pozwala to na kilka optymalizacji, w tym optymalizację klasycznej logiki, która działa na zmiennych do zmiany kolejności w przypadku zastosowania `Adjoint` wariantu operacji.

## <a name="mutable-variables"></a>Zmienne modyfikowalne

Jako alternatywę do tworzenia zmiennej przy użyciu `let` `mutable` słowa kluczowego tworzy zmienną modyfikowalną, którą *można* powiązać po jej początkowym utworzeniu za pomocą `set` słowa kluczowego.

Można ponownie powiązać symbole zadeklarowane i powiązane jako część `mutable` instrukcji z inną wartością w dalszej części kodu. Jeśli symbol zostanie powiązana później w kodzie, jego typ nie zmieni się, a nowo związana wartość musi być zgodna z tym typem.

### <a name="rebinding-of-mutable-symbols"></a>Ponowne wiązanie modyfikowalnych symboli

Można ponownie powiązać modyfikowalną zmienną przy użyciu `set` instrukcji.
Takie ponowne powiązanie składa się ze słowa kluczowego `set` , po którym następuje ciąg lub krotka symboli, znak równości `=` , wyrażenie służące do ponownego powiązania symboli z i kończący średnik.

Poniżej przedstawiono kilka przykładów technik rebind instrukcji.

#### <a name="apply-and-reassign-statements"></a>Instrukcje Apply i Reassign

Szczególnym rodzajem instrukcji `set` , instrukcja *apply-and-Reassign* , zapewnia wygodny sposób łączenia, jeśli po prawej stronie składa się operator binarny, a wynik ma zostać Przewiązany do lewego argumentu operatora. Na przykład

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
zwiększa wartość licznika `counter` w każdej iteracji `for` pętli. Poprzedni kod jest równoważny z 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Podobne instrukcje są dostępne dla wszystkich operatorów binarnych, w których typ lewej strony jest zgodny z typem wyrażenia. Te instrukcje zapewniają wygodny sposób na gromadzenie wartości.

Załóżmy na przykład, że `qubits` jest to rejestr qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>Instrukcje Update-and-Reassign

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

W przypadku tablic [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) w standardowej bibliotece Q # dostępne są niezbędne narzędzia do obsługi wielu typowych operacji inicjowania tablic i manipulowania nimi, co pozwala uniknąć konieczności aktualizowania elementów tablicy w pierwszym miejscu. 

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

Za pomocą narzędzi biblioteki dla tablic dostępnych w programie [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) można na przykład łatwo zdefiniować funkcję zwracającą tablicę `Pauli` typów, w których element w indeksie `i` przyjmuje daną `Pauli` wartość, a wszystkie inne wpisy są tożsamością ( `PauliI` ).

Poniżej przedstawiono dwie definicje takich funkcji, a drugie korzystanie z narzędzi na tym etapie.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

Zamiast przeiterować każdy indeks w tablicy i warunkowo ustawić go na `PauliI` lub dane `pauli` , można zamiast tego użyć z programu, `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) Aby utworzyć tablicę `PauliI` typów, a następnie po prostu zwrócić wyrażenie Copy-and-Update, w którym zmieniono określoną wartość przy indeksie `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Dekonstrukcja krotki

Oprócz przypisywania pojedynczej zmiennej można użyć `let` `mutable` słów kluczowych i innych konstrukcji powiązań, takich jak `set` — do rozpakowania zawartości [typu krotki](xref:microsoft.quantum.guide.types#tuple-types).
Przypisanie tego formularza jest określane w celu *odtworzenia* elementów tej krotki.

Jeśli po prawej stronie powiązania jest krotka, można ją dekonstruować po przypisaniu.
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
- Wszystkie trzy części `repeat` / `until` pętli (treść, test i naprawa) działają jako pojedynczy zakres, dlatego symbole, które są powiązane z treścią są dostępne w teście i naprawie.

W przypadku obu typów pętli każdy przebieg przez pętlę działa we własnym zakresie, dlatego powiązania z wcześniejszego przebiegu nie są dostępne w późniejszym przebiegu.
Aby uzyskać więcej informacji na temat tych pętli, zobacz [Flow Control](xref:microsoft.quantum.guide.controlflow).

Bloki wewnętrzne dziedziczą powiązania symboli z bloków zewnętrznych.
Można powiązać symbol tylko raz na blok; nie można zdefiniować symbolu o takiej samej nazwie jak inny symbol znajdujący się w zakresie (bez "przesłaniania").
Następujące sekwencje są dozwolone:

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

## <a name="next-steps"></a>Następne kroki

Dowiedz się więcej na temat [pracy z Qubits w usłudze](xref:microsoft.quantum.guide.qubits) Q #.
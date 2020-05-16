---
title: 'Przepływ sterowania w p #'
description: Pętle, warunkowe itd.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: c534e016fcb8b50e66c11ca29c253ba0512acc6e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430955"
---
# <a name="control-flow-in-q"></a>Przepływ sterowania w p #

W ramach operacji lub funkcji każda instrukcja jest wykonywana w kolejności, podobnie jak w przypadku najczęściej używanych języków klasycznych.
Ten przepływ sterowania można jednak zmodyfikować na trzy różne sposoby:

- `if`zatwierdzeni
- `for`pętli
- `repeat`-`until`pętli

W dalszej części [znajdziesz poniższe](#repeat-until-success-loop)Omówienie.
`if` `for` Konstrukcje przepływu sterowania i są jednak bardziej zrozumiałe dla większości klasycznych języków programowania.

Należy pamiętać, że `for` pętle i `if` instrukcje mogą być nawet używane w operacjach, dla których specjalizacje są generowane automatycznie. W takim przypadku sąsiadująca `for` Pętla odwraca kierunek i przyjmuje sąsiadujące poszczególne iteracje.
Ta zasada jest zgodna z zasadą "buty i-SOCKS": Jeśli chcesz cofnąć umieszczanie w ramach SOCKS, a następnie odbuty, musisz cofnąć umieszczanie na butów, a następnie cofnąć umieszczenie w usłudze SOCKS.
Decidedly mniej dobrze, aby wypróbować i podjąć Twoje SOCKS, gdy będziesz nadal korzystać z swoich oddziałów.

## <a name="if-else-if-else"></a>If, Else-IF, else

`if`Instrukcja obsługuje wykonywanie warunkowe.
Składa się ze słowa kluczowego `if` , otwartego nawiasu, `(` wyrażenia logicznego, nawiasu zamykającego `)` i bloku instrukcji (bloku _then_ ).
Może to być dowolna liczba klauzul innych niż, z których każda składa się ze słowa kluczowego `elif` , otwierającego nawiasu `(` , wyrażenia logicznego, zamykającego nawiasu `)` i bloku instrukcji (bloku _else-if_ ).
Na koniec instrukcja może opcjonalnie zakończyć z klauzulą else, która składa się ze słowa kluczowego, `else` po którym następuje inny blok instrukcji (blok _else_ ).

`if`Warunek jest obliczany, a jeśli ma wartość true, zostaje wykonany blok then.
Jeśli warunek ma wartość false, zostanie obliczony pierwszy warunek else-if; Jeśli wartość jest równa true, ten blok else-IF jest wykonywany.
W przeciwnym razie drugi blok else-if zostanie przetestowany, a następnie trzeci i tak dalej, dopóki nie zostanie napotkana klauzula z prawdziwym warunkiem lub nie ma żadnych klauzul else-IF.
Jeśli oryginalny warunek if i wszystkie klauzule else-if mają wartość false, blok else jest wykonywany, jeśli został podany.

Należy zauważyć, że każdy blok jest wykonywany we własnym zakresie.
Powiązania wykonane wewnątrz elementu `if` , `elif` lub `else` bloku nie są widoczne po jego zakończeniu.

Na przykład:

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
lub
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>Pętla for

`for`Instrukcja obsługuje iterację w zakresie liczb całkowitych lub za pośrednictwem tablicy.
Instrukcja składa się ze słowa kluczowego `for` , otwartego nawiasu `(` , po którym występuje krotka symbol lub symbol, słowo kluczowe `in` , wyrażenie typu `Range` lub tablicy, nawias zamykający `)` i blok instrukcji.

Blok instrukcji (treść pętli) jest wykonywany wielokrotnie ze zdefiniowanymi symbolami (zmienne pętli) powiązane z każdą wartością w zakresie lub tablicy.
Należy pamiętać, że jeśli wyrażenie zakresu szacuje pusty zakres lub tablicę, treść nie zostanie wykonana.
Wyrażenie jest w pełni oceniane przed wprowadzeniem pętli i nie zmienia się podczas wykonywania pętli.

Zmienna pętla jest powiązana z każdym wejściem do treści pętli i niezależna na końcu treści.
W szczególności zmienna Loop nie jest powiązana po zakończeniu pętli for.
Powiązanie zadeklarowanych symboli jest niezmienne i zgodne z tymi samymi regułami, co inne powiązania zmiennych. 

W przypadku niektórych przykładów Załóżmy, że `qubits` jest to rejestr qubits (tj. typu `Qubit[]` ), 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
Należy pamiętać, że na końcu wykorzystujemy operator binarny z przesunięciem w lewo, `<<<` szczegóły, które można znaleźć w [wyrażeniach liczbowych](xref:microsoft.quantum.guide.expressions#numeric-expressions) .


## <a name="repeat-until-success-loop"></a>Pętla REPEAT-until-Success

Język Q # zezwala, aby klasyczny przepływ sterowania był zależny od wyników pomiaru qubits.
Ta funkcja z kolei umożliwia wdrażanie zaawansowanych probabilistyczneych gadżetów, które mogą zmniejszyć koszt obliczeniowy wdrożenia unitaries.
Przykładowo można łatwo zaimplementować wzorce " *REPEAT-until-Success* " (jednostek ru) w programie Q #.
Te wzorce jednostek ru są programami probabilistyczne, które mają *przewidywane* niskie koszty w zakresie bram elementarnych, ale dla których rzeczywisty koszt zależy od rzeczywistego przebiegu i rzeczywiste odchodzenie między różnymi możliwymi gałęziami.

Aby ułatwić wzorce powtarzania do sukcesu (jednostek ru), Q # obsługuje konstrukcje

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

gdzie `expression` jest dowolnym prawidłowym wyrażeniem, którego wynikiem jest wartość typu `Bool` .
Zostanie wykonana treść pętli, a następnie warunek jest obliczany.
Jeśli warunek ma wartość true, instrukcja zostanie zakończona; w przeciwnym razie nastąpi wykonanie naprawy, a instrukcja jest wykonywana ponownym uruchomieniem, rozpoczynając od treści pętli.

Wszystkie trzy części pętli REPEAT/until (treść, test i naprawa) są traktowane jako pojedynczy zakres *dla każdego powtórzenia*, dlatego symbole, które są powiązane z treścią, są dostępne w teście i w naprawie.
Jednak Kończenie wykonywania naprawy kończy zakres instrukcji, tak aby powiązania symboli wykonane podczas treści lub naprawy nie były dostępne w kolejnych powtórzeniach.

Ponadto `fixup` instrukcja jest często przydatna, ale nie zawsze jest konieczna.
W przypadkach, gdy nie jest to konieczne, konstrukcja
```qsharp
repeat {
    // do stuff
}
until (expression);
```
jest również prawidłowym wzorcem jednostek ru.

W dolnej części tej strony przedstawiamy kilka [przykładów pętli jednostek ru](#repeat-until-success-examples).

> [!TIP]   
> Unikaj używania pętli REPEAT-until-Success wewnątrz funkcji. Odpowiednie funkcje są udostępniane przez pętle w funkcjach. 

## <a name="while-loop"></a>While — pętla

Wzorce REPEAT-until-Success mają bardzo connotation specyficzny dla Quantum. Są one powszechnie używane w określonych klasach algorytmów Quantum — a tym samym — dedykowana konstrukcja języka w Q #. Jednak pętle, które są przerywane w zależności od warunku, a długość wykonywania jest w tym przypadku nieznana w czasie kompilacji, muszą być obsługiwane z uwzględnieniem szczególnych informacji w środowisku uruchomieniowym Quantum. Ich użycie w ramach funkcji z drugiej strony jest nieproblematyczne, ponieważ tylko zawierają kod, który będzie wykonywany na konwencjonalnym sprzęcie (innym niż Quantum). 

W związku z tym funkcja Q # obsługuje używanie pętli while tylko wewnątrz funkcji. `while`Instrukcja składa się ze słowa kluczowego `while` , otwartego nawiasu `(` , warunku (tj. wyrażenia logicznego), zamykającego nawiasu `)` i bloku instrukcji.
Blok instrukcji (treść pętli) jest wykonywany tak długo, jak warunek jest obliczany `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Return, instrukcja

Instrukcja return kończąca wykonywanie operacji lub funkcji i zwraca wartość do obiektu wywołującego.
Składa się ze słowa kluczowego `return` , po którym następuje wyrażenie odpowiedniego typu i kończącego się średnika.

Wywoływany, który zwraca pustą krotkę, nie `()` wymaga instrukcji return.
Jeśli pożądane jest wczesne wyjście, można `return ()` go użyć w tym przypadku.
Możliwe do zwrócenia wszystkie inne typy wymagają końcowej instrukcji return.

W obrębie operacji nie ma maksymalnej liczby instrukcji return.
Kompilator może emitować ostrzeżenie, jeśli instrukcje są zgodne z instrukcją Return w bloku.

Na przykład:
```qsharp
return 1;
```
lub
```qsharp
return ();
```
lub
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>Instrukcja zakończony niepowodzeniem

Instrukcja Fail kończy wykonywanie operacji i zwraca wartość błędu do obiektu wywołującego.
Składa się ze słowa kluczowego `fail` , po którym następuje ciąg i kończący się średnik.
Ten ciąg jest zwracany do klasycznego sterownika jako komunikat o błędzie.

W obrębie operacji nie ma ograniczeń dotyczących liczby instrukcji zakończonych niepowodzeniem.
Kompilator może emitować ostrzeżenie, jeśli instrukcje obserwują instrukcję Fail w bloku.

Na przykład:
```qsharp
fail $"Impossible state reached";
```
lub korzystając z [ciągów interpolowanych](xref:microsoft.quantum.guide.expressions#interpolated-strings),
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Przykłady powtarzania do sukcesu

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>Wzorzec jednostek ru dla pojedynczego obrotu qubit o osi niewymiernej 

W typowym przypadku użycia Następująca operacja Q # implementuje obrót wokół osi niewymiernej $ (I + 2i Z)/\sqrt {5} $ w sferze Bloch. Jest to realizowane przy użyciu znanego wzorca jednostek ru:

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-mutable-variable-in-scope"></a>Pętla jednostek ru z modyfikowalną zmienną w zakresie

Ten przykład pokazuje użycie zmiennej modyfikowalnej, `finished` która znajduje się w zakresie całej pętli REPEAT-until-Naprawa i która zostaje zainicjowana przed pętlą i zaktualizowaną w kroku naprawy.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a>JEDNOSTEK ru bez`fixup`

Na przykład poniższy kod jest obwodem usługi probabilistyczne, który implementuje ważną bramę rotacji $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ przy `H` użyciu `T` bram i.
Pętla kończy się na wartościach $ \frac {8} {5} $.
Zobacz [*powtarzanie-do-sukces: Niedeterministyczny dekompozycja qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick i Svore, 2014), aby uzyskać więcej szczegółów.

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a>JEDNOSTEK ru przygotowania stanu Quantum

Na koniec pokazujemy przykład wzorca jednostek ru, aby przygotować stan Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, rozpoczynając od stanu $ \ket{+} $.
Zobacz również [przykład testowania jednostkowego w standardowej bibliotece](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

Istotne funkcje programistyczne przedstawione w tej operacji to bardziej skomplikowana `fixup` część pętli, która obejmuje operacje Quantum i użycie `AssertProb` instrukcji w celu ustalenia prawdopodobieństwa mierzenia stanu Quantum w określonych punktach w programie.
Więcej informacji na temat operacji i można znaleźć w temacie [testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging) [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) .


## <a name="whats-next"></a>Co dalej?
Więcej informacji na temat [testowania i debugowania](xref:microsoft.quantum.guide.testingdebugging) w programie Q #.
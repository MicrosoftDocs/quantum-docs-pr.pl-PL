---
title: Przepływ sterowania w Q#
description: Pętle, warunkowe itd.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: eca37202e5fe9b48dcfdec4eeb4ba6cafaac8723
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691088"
---
# <a name="control-flow-in-no-locq"></a>Przepływ sterowania w Q#

W ramach operacji lub funkcji każda instrukcja jest uruchamiana w kolejności, podobnie jak w przypadku innych typowych języków, których to dotyczy.
Można jednak zmodyfikować przepływ kontroli na trzy różne sposoby:

* `if` zatwierdzeni
* `for` pętli
* `repeat-until-success` pętli
* liczby sprzężone ( `apply-within` instrukcje)

`if` `for` Konstrukcje przepływu sterowania i są realizowane w dobrze znanym znaczeniu dla większości klasycznych języków programowania. [`Repeat-until-success`](#repeat-until-success-loop) pętle i [sprzężenia](#conjugations) zostały omówione w dalszej części tego artykułu.

Należy pamiętać, że `for` pętle i `if` instrukcje mogą być używane w operacjach, dla których [specjalizacje](xref:microsoft.quantum.guide.operationsfunctions) są generowane automatycznie. W tym scenariuszu sąsiadująca `for` Pętla odwraca kierunek i przyjmuje sąsiadujące poszczególne iteracje.
Ta akcja jest zgodna z zasadą "buty i-SOCKS": Jeśli chcesz cofnąć umieszczenie w usłudze SOCKS, a następnie kliknij pozycję Wycofaj w odniesieniu do butów, a następnie Cofnij umieszczenie w obszarze SOCKS. 

## <a name="if-else-if-else"></a>If, Else-IF, else

`if`Instrukcja obsługuje przetwarzanie warunkowe.
Składa się ze słowa kluczowego `if` , wyrażenia logicznego w nawiasach i bloku instrukcji (bloku _then_ ).
Opcjonalnie można wykonać dowolną liczbę klauzul else-IF, z których każdy składa się ze słowa kluczowego `elif` , wyrażenia logicznego w nawiasach i bloku instrukcji (bloku _else-if_ ).
Na koniec instrukcja może opcjonalnie zakończyć z klauzulą else, która składa się ze słowa kluczowego, `else` po którym następuje inny blok instrukcji (blok _else_ ).

`if`Warunek jest obliczany, a jeśli ma *wartość true* , blok *then* jest uruchamiany.
Jeśli warunek ma *wartość false* , zostanie obliczony pierwszy warunek else-if; Jeśli ma wartość true, blok *else-if* jest uruchamiany.
W przeciwnym razie drugi blok else-IF jest obliczany, a następnie trzeci i tak dalej, dopóki nie zostanie napotkana klauzula z prawdziwym warunkiem lub nie ma żadnych klauzul else-IF.
Jeśli oryginalny warunek *if* i wszystkie klauzule else-if mają *wartość false* , blok *else* jest uruchamiany, jeśli jest podany.

Należy zauważyć, że w zależności od tego, czy blokowane są uruchomienia, działa w ramach własnego zakresu.
Powiązania wykonane wewnątrz elementu `if` , `elif` lub `else` bloku nie są widoczne po zakończeniu bloku.

Przykład:

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

`for`Instrukcja obsługuje iterację w zakresie liczb całkowitych lub tablicy.
Instrukcja składa się ze słowa kluczowego `for` , po którym następuje symbol lub krotka symboli, słowo kluczowe `in` i wyrażenie typu `Range` lub tablicy, wszystkie w nawiasach i bloku instrukcji.

Blok instrukcji (treść pętli) jest uruchamiany wielokrotnie, ze zdefiniowanym symbolem (zmienna pętli) powiązaną z każdą wartością z zakresu lub tablicy.
Należy zauważyć, że jeśli wyrażenie zakresu szacuje pusty zakres lub tablicę, treść nie jest w ogóle uruchomiona.
Wyrażenie jest w pełni oceniane przed wprowadzeniem pętli i nie zmienia się, gdy pętla jest uruchomiona.

Zmienna pętla jest powiązana z każdym wejściem do treści pętli i jest niepowiązana na końcu treści.
Zmienna Loop nie jest powiązana po zakończeniu pętli for.
Powiązanie zmiennej pętli jest niezmienne i jest zgodne z tymi samymi regułami, co inne powiązania zmiennych. 

W tych przykładach `qubits` jest rejestrem qubits (tj. typu `Qubit[]` ), 

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

Należy pamiętać, że na końcu wykorzystujemy operator binarny z przesunięciem w lewo z lewej strony `<<<` . Aby uzyskać więcej informacji, zobacz [wyrażenia liczbowe](xref:microsoft.quantum.guide.expressions#numeric-expressions).

## <a name="repeat-until-success-loop"></a>Pętla REPEAT-until-Success

Q#Język pozwala, aby klasyczny przepływ sterowania był zależny od wyników pomiaru qubits.
Ta funkcja z kolei umożliwia wdrażanie zaawansowanych probabilistyczneych gadżetów, które mogą zmniejszyć koszt obliczeniowy wdrożenia unitaries.
Przykładami są wzorce *powtarzania do sukcesu* (jednostek ru) w programie Q# .
Te wzorce jednostek ru są programami probabilistyczne, które mają *przewidywane* niskie koszty w zakresie bram elementarnych; poniesiony koszt zależy od rzeczywistego przebiegu i przeplotu wielu możliwych rozgałęzień.

Aby ułatwić wzorce powtarzania do sukcesu (jednostek ru), Q# obsługuje konstrukcje

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
Zostanie uruchomiona pętla, a następnie warunek jest obliczany.
Jeśli warunek ma wartość true, instrukcja zostanie zakończona; w przeciwnym razie przebiega naprawy i instrukcja zostanie ponownie uruchomiona, rozpoczynając od treści pętli.

Wszystkie trzy części pętli jednostek ru (treść, test i naprawa) są traktowane jako pojedynczy zakres *dla każdego powtórzenia* , dlatego symbole, które są powiązane w treści są dostępne zarówno w teście, jak i w naprawie.
Jednak ukończenie przebiegu naprawy kończy zakres instrukcji, tak aby powiązania symboli wykonane podczas treści lub naprawy nie były dostępne w kolejnych powtórzeniach.

Ponadto `fixup` instrukcja jest często przydatna, ale nie zawsze jest konieczna.
W przypadkach, gdy nie jest to konieczne, konstrukcja

```qsharp
repeat {
    // do stuff
}
until (expression);
```

jest również prawidłowym wzorcem jednostek ru.

Aby uzyskać więcej przykładów i szczegółów, zobacz [przykłady powtarzania do sukcesu](#repeat-until-success-examples) w tym artykule.

> [!TIP]   
> Unikaj używania pętli REPEAT-until-Success wewnątrz funkcji. Użyj *while* pętle, aby zapewnić odpowiednie funkcje wewnątrz funkcji. 

## <a name="while-loop"></a>Pętla while

Wzorce REPEAT-until-Success mają bardzo connotation specyficzny dla Quantum. Są one powszechnie używane w określonych klasach algorytmów Quantum — dlatego w przypadku dedykowanego języka konstrukcja w Q# . Jednak pętle, które są przerywane w zależności od stanu i długość przebiegu są nieznane w czasie kompilacji, są obsługiwane z szczególnym uwzględnieniem w środowisku uruchomieniowym Quantum. Jednak ich użycie w funkcjach nie działa, ponieważ pętle zawierają tylko kod, który jest uruchamiany na sprzęcie konwencjonalnym (innym niż Quantum). 

Q#w związku z tym obsługuje używanie pętli while tylko w obrębie funkcji.
`while`Instrukcja składa się z słowa kluczowego `while` , wyrażenia logicznego w nawiasach i bloku instrukcji.
Blok instrukcji (treść pętli) działa tak długo, jak warunek zostanie obliczony `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a>Liczby sprzężone

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

Q# obsługuje instrukcję sprzężenia implementującą poprzednią transformację. Korzystając z tej instrukcji, `ApplyWith` można zaimplementować operację w następujący sposób:

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
Taka instrukcja sprzężona jest przydatna, jeśli zewnętrzne i wewnętrzne przekształcenia nie są łatwo dostępne jako operacje, ale są bardziej wygodne do opisania przez blok składający się z kilku instrukcji. 

Przekształcenie odwrotne dla instrukcji zdefiniowanych w bloku jest automatycznie generowane przez kompilator i uruchamiane po zakończeniu zastosowania instrukcji.
Ponieważ żadne zmienne modyfikowalne używane jako część wewnątrz bloku nie mogą być ponownie powiązane w bloku Apply, wygenerowane przekształcenie jest gwarantowane jako sąsiadujące obliczenie w bloku. 

## <a name="return-statement"></a>Return, instrukcja

Instrukcja return zamyka przebieg operacji lub funkcji i zwraca wartość do obiektu wywołującego.
Składa się ze słowa kluczowego `return` , po którym następuje wyrażenie odpowiedniego typu i kończącego się średnika.

Przykład:
```qsharp
return 1;
```
lub
```qsharp
return (results, qubits);
```

* Wywoływany, który zwraca pustą krotkę, nie `()` wymaga instrukcji return.
* Aby określić wczesne wyjście z operacji lub funkcji, użyj polecenia `return ();` .
Możliwe do zwrócenia wszystkie inne typy wymagają końcowej instrukcji return.
* W obrębie operacji nie ma maksymalnej liczby instrukcji return.
Kompilator może emitować ostrzeżenie, jeśli instrukcje są zgodne z instrukcją Return w bloku.

   
## <a name="fail-statement"></a>Instrukcja zakończony niepowodzeniem

Instrukcja Fail kończy wykonywanie operacji i zwraca wartość błędu do obiektu wywołującego.
Składa się ze słowa kluczowego `fail` , po którym następuje ciąg i kończący się średnik.
Instrukcja zwraca ciąg do klasycznego sterownika jako komunikat o błędzie.

W obrębie operacji nie ma ograniczeń dotyczących liczby instrukcji zakończonych niepowodzeniem.
Kompilator może emitować ostrzeżenie, jeśli instrukcje obserwują instrukcję Fail w bloku.

Przykład:

```qsharp
fail $"Impossible state reached";
```
lub korzystając z [ciągów interpolowanych](xref:microsoft.quantum.guide.expressions#interpolated-strings),
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Przykłady powtarzania do sukcesu

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>Wzorzec jednostek ru dla obrotu pojedynczej qubit o osi niewymiernej 

W typowym przypadku użycia następująca Q# operacja implementuje obrót wokół osi niewymiernej $ (I + 2i z)/\sqrt {5} $ w sferze Bloch. Implementacja używa znanego wzorca jednostek ru:

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>Pętla jednostek ru z zmienną modyfikowalną w zakresie

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

### <a name="rus-without-fixup"></a>JEDNOSTEK ru bez `fixup`

Ten przykład pokazuje pętlę jednostek ru bez kroku naprawy. Kod jest obwodem usługi probabilistyczne, który implementuje ważną bramę rotacji $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ przy użyciu `H` `T` bram i.
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

Na koniec przedstawiono przykład wzorca jednostek ru, aby przygotować stan Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, rozpoczynając od stanu $ \ket{+} $.

Istotne funkcje programistyczne wyświetlane w tej operacji to:

* Bardziej złożona `fixup` część pętli, która obejmuje operacje Quantum. 
* Użycie `AssertMeasurementProbability` instrukcji w celu ustalenia prawdopodobieństwa mierzenia stanu Quantum w określonych punktach w programie.

Aby uzyskać więcej informacji na [`AssertMeasurement`](xref:Microsoft.Quantum.Diagnostics.assertmeasurement) temat [`AssertMeasurementProbability`](xref:Microsoft.Quantum.Diagnostics.assertmeasurementprobability) operacji i, zobacz [testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging).

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

Aby uzyskać więcej informacji, zobacz [przykładowe testy jednostkowe dostępne w bibliotece standardowej](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

## <a name="next-steps"></a>Następne kroki

Więcej informacji na temat [testowania i debugowania](xref:microsoft.quantum.guide.testingdebugging) w programie Q# .

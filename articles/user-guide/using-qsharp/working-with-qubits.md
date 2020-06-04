---
title: Praca z kubitami
description: Opis wypełnienia
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 0deb0729a88c49798f32a22a943b935d383c570b
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327547"
---
# <a name="working-with-qubits"></a>Praca z kubitami

Po zapoznaniu się z różnymi częściami języka Q # poinformuj nas o tym, jak korzystać z samych qubits.

Należy zauważyć, że żadna z tych instrukcji nie jest dozwolona w treści funkcji.
Są one prawidłowe tylko w obrębie operacji.

## <a name="allocating-qubits"></a>Alokowanie Qubits

### <a name="clean-qubits"></a>Wyczyść qubits

`using`Instrukcja jest używana do *przydzielania* nowych qubits do użycia w bloku instrukcji.

Instrukcja składa się ze słowa kluczowego `using` , po którym następuje otwarty nawias `(` , powiązanie, nawias zamykający `)` i blok instrukcji, w ramach którego qubits będzie dostępny.
Powiązanie jest zgodne z tym samym wzorcem co `let` : pojedynczym symbolem lub krotką symboli, po którym następuje znak równości `=` oraz jedną wartością lub zgodną krotką *inicjatorów*.

Inicjatory są dostępne dla jednego qubit, wskazanego jako `Qubit()` lub tablicy qubits, `Qubit[n]` , gdzie `n` jest `Int` wyrażeniem.
Na przykład

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Wszystkie qubits przydzieloną w ten sposób zaczynają się w stanie $ \ket {0} $; w powyższym przykładzie `register` jest to w stanie $ \ket {00000} = \ket \otimes \ket \otimes \cdots \otimes \ket {0} {0} {0} $.
Na końcu `using` bloku wszystkie qubits przydzielone przez ten blok są natychmiast cofane i nie można ich użyć.

> [!WARNING]
> Maszyny docelowe oczekują, że qubits są w stanie $ \ket {0} $ bezpośrednio przed cofnięciem alokacji, dzięki czemu mogą być ponownie używane i dostępne dla innych `using` bloków alokacji.
> Jeśli to możliwe, użyj operacji jednostkowych, aby zwrócić wszystkie przydzieloną qubits do $ \ket {0} $.
> W razie potrzeby @"microsoft.quantum.intrinsic.reset" operacja może służyć do mierzenia qubit zamiast tego, i do użycia tego wyniku pomiaru, aby upewnić się, że pomiar qubit jest zwracany do $ \ket {0} $. Takie pomiar spowoduje zniszczenie wszelkich Entanglement z pozostałymi qubits i w związku z tym ma wpływ na obliczenia.


### <a name="borrowed-qubits"></a>Zapożyczony Qubits

`borrowing`Instrukcja jest używana do udostępnienia qubits do tymczasowego użytku, które nie muszą być w określonym stanie.

Mechanizm pożyczania umożliwia alokację qubits, która może być używana jako miejsce do rozliczania podczas obliczeń.
Te qubits zazwyczaj nie są w stanie czystym, tzn. nie muszą być inicjowane w znanym stanie, takim jak $ \ket {0} $.
Są one często określane jako "zanieczyszczone" qubits, ponieważ ich stan jest nieznany i może nawet być Entangled z innymi częściami pamięci komputera Quantum.

Powiązanie jest zgodne z tym samym wzorcem i regułami, co w `using` instrukcji.
Na przykład
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
Zapożyczone qubits znajdują się w nieznanym stanie i wykracza poza zakres na końcu bloku instrukcji.
Pożyczkobiorca zatwierdzi, aby opuszczał qubits w tym samym stanie, w którym były zapożyczone, tj. ich stan na początku i na końcu bloku instrukcji powinien być taki sam.
Ten stan w szczególności nie jest stanem klasycznym, takim jak w większości przypadków, zakresy pożyczek nie powinny zawierać pomiarów. 

Podczas pożyczania qubits system najpierw spróbuje wypełnić żądanie z qubits, które są używane, ale nie są używane w treści `borrowing` instrukcji.
Jeśli nie ma wystarczającej ilości takich qubits, przydzieli nowe qubits do wykonania żądania.


Wśród znanych przypadków użycia zanieczyszczonych qubits są implementacje bram CNOT z wieloma kontrolowanymi żądaniami, które wymagają tylko bardzo małej liczby qubits i implementacji przyrostów.
Zapoznaj się z poniższym [przykładem pożyczek Qubits](#borrowing-qubits-example) , aby zobaczyć przykład ich użycia w pytaniach Q #, lub w [*oparciu o 2n + 2 Qubits with Toffoli modułowe mnożenia*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler i Svore 2017) dla algorytmu, który wykorzystuje pożyczone Qubits.


## <a name="intrinsic-operations"></a>Operacje wewnętrzne

Po przydzieleniu qubit można następnie przesłać do funkcji i operacji.
W niektórych przypadkach jest to wszystko, że program Q # może wykonać qubit, ponieważ wszystkie akcje, które można podjąć, są zdefiniowane jako operacje.
Te operacje są bardziej szczegółowe w [operacjach i funkcjach wewnętrznych](xref:microsoft.quantum.libraries.standard.prelude), ale teraz wspominamy kilka przydatnych operacji, których można użyć do współpracy z qubits.

Najpierw operatory Single-qubit Pauli $X $, $Y $ i $Z $ są reprezentowane w Q # przez operacje wewnętrzne `X` , `Y` i `Z` , z których każdy ma typ `(Qubit => Unit is Adj + Ctl)` .
Zgodnie z opisem w [wewnętrznych operacjach i funkcjach](xref:microsoft.quantum.libraries.standard.prelude), można myśleć o $X $ i w związku z tym, że `X` jest to operacja bitowa lub niebrama.
`X`Operacja pozwala nam przygotować Stany w postaci $ \ket{s_0 s_1 \dots s_n} $ dla niektórych klasycznych ciągów bitowych $s $:

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> Później zobaczymy bardziej kompaktowe sposoby zapisywania tej operacji, które nie wymagają ręcznego sterowania przepływem.

Możemy również przygotować takie Stany jak $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ i $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt $ przy {2} użyciu Hadamard Transform $H $, który jest reprezentowany w Q # przez operację wewnętrzną `H : (Qubit => Unit is Adj + Ctl)` :

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Miary

Przy użyciu `Measure` operacji, która jest wbudowaną wewnętrzną operacją niebędącą jednostką, możemy wyodrębnić klasyczne informacje z obiektu typu `Qubit` i przypisać wartość klasyczną w wyniku, który ma typ zarezerwowany `Result` , co oznacza, że wynik nie jest już stanem Quantum.
Dane wejściowe `Measure` to oś Pauli w sferze Bloch, reprezentowana przez wartość typu `Pauli` (na przykład `PauliX` ) i wartość typu `Qubit` .

Prostym przykładem jest następująca operacja, która przydziela jeden qubit w stanie $ \ket {0} $, a następnie stosuje do niego operację Hadamard `H` i mierzy wynik `PauliZ` .

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

Nieco bardziej skomplikowany przykład jest podany w następującej operacji, która zwraca wartość logiczną, `true` Jeśli wszystkie qubits w rejestrze typu `Qubit[]` znajdują się w stanie zero, gdy jest mierzony w określonej Pauli i która zwraca w `false` przeciwnym razie.

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

## <a name="borrowing-qubits-example"></a>Przykład pożyczania Qubits

W programie Canon istnieją przykłady, które używają `borrowing` słowa kluczowego, na przykład funkcja `MultiControlledXBorrow` zdefiniowana poniżej.
W przypadku `controls` określenia qubits kontrolki, która powinna zostać dodana do `X` operacji, `Length(controls)-2` w tej implementacji zostanie dodana ogólna liczba zanieczyszczonych ancillas.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

Należy zauważyć, że rozległe użycie `With` combinator---w swojej formie, która ma zastosowanie do operacji, które obsługują sąsiednie, tj., `WithA` ---zostało wykonane w tym przykładzie.
Jest to dobry styl programowania, ponieważ dodawanie kontroli do struktur obejmujących `With` propagowanie kontroli tylko do operacji wewnętrznej.
Należy również pamiętać, że w tym miejscu oprócz `body` operacji, implementacja `controlled` treści operacji została jawnie udostępniona, a nie do `controlled auto` instrukcji.
Przyczyną tego jest fakt, że wiemy ze struktury obwodu, jak łatwo dodać dalsze kontrolki, które są korzystne w porównaniu z dodawaniem kontroli do poszczególnych bram i każdej bramy w `body` . 

Należy poinstruować o porównaniu tego kodu z inną funkcją firmy Canon, `MultiControlledXClean` która osiąga ten sam cel implementacji `X` operacji mnożenia, ale używa kilku czystych qubits przy użyciu `using` mechanizmu. 

## <a name="next-steps"></a>Następne kroki

Więcej informacji na temat [przepływu sterowania](xref:microsoft.quantum.guide.controlflow) w programie Q #.
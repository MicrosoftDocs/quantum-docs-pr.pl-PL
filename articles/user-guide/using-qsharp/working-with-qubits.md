---
title: Praca z kubitami
description: Dowiedz się więcej o pracy z usługą qubits w programie Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: aa942a61280553ae4e51cd5ddcc85c0df935dab1
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835863"
---
# <a name="working-with-qubits"></a>Praca z kubitami

Qubits to podstawowy obiekt informacji w ramach przetwarzania Quantum. Aby zapoznać się z ogólnym wprowadzeniem do qubits, zobacz temat [Omówienie przetwarzania Quantum](xref:microsoft.quantum.overview.understanding)i aby uzyskać bardziej szczegółowe informacje na temat szczegółowe, zobacz [qubit](xref:microsoft.quantum.concepts.qubit). 

W tym artykule przedstawiono sposób użycia programu i pracy z programem qubits w Q# programie. 

> [!IMPORTANT]
>Żadna z instrukcji omówionych w tym artykule nie jest prawidłowa w treści funkcji. Są one prawidłowe tylko w obrębie operacji.

## <a name="allocating-qubits"></a>Alokowanie Qubits

Ponieważ fizyczne qubits to cenny zasób na komputerze z systemem Quantum, część zadania kompilatora polega na tym, że są one używane tak efektywnie, jak to możliwe.
W związku z tym należy poinformować Q# o *przydzieleniu* qubits do użycia w ramach określonego bloku instrukcji.
Możesz przydzielić qubits jako pojedynczy qubit lub jako tablicę qubits, znaną jako *Rejestr*. 

### <a name="clean-qubits"></a>Wyczyść qubits

Użyj `using` instrukcji, aby przydzielić nowe qubits do użycia w bloku instrukcji.

Instrukcja składa się ze słowa kluczowego `using` , po którym następuje powiązanie zawarte w nawiasach `( )` i blok instrukcji, w ramach którego qubits są dostępne.
Powiązanie jest zgodne z tym samym wzorcem co `let` : pojedynczym symbolem lub krotką symboli, po którym następuje znak równości `=` oraz jedną wartością lub zgodną krotką *inicjatorów*.

Inicjatory są dostępne dla jednego qubit, wskazanego jako `Qubit()` lub tablicy qubits, `Qubit[n]` , gdzie `n` jest `Int` wyrażeniem.
Przykład:

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Wszystkie qubits przydzieloną w ten sposób zaczynają się w stanie $ \ket {0} $. Tak więc w poprzednim przykładzie, `auxiliary` jest pojedynczym qubit w stanie $ \ket {0} $ i `register` jest w pięciu qubit stan $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $.
Na końcu `using` bloku wszystkie qubits przydzielone przez ten blok są natychmiast cofane i nie można ich użyć.

> [!WARNING]
> Maszyny docelowe mogą ponownie użyć cofniętej alokacji qubits i zaoferować je innym `using` blokom do przydzielenia. W związku z tym maszyna docelowa oczekuje, że qubits są w stanie $ \ket {0} $ bezpośrednio przed cofnięciem alokacji.
> Jeśli to możliwe, użyj operacji jednostkowych, aby zwrócić wszystkie przydzieloną qubits do $ \ket {0} $.
> W razie potrzeby można użyć @"microsoft.quantum.intrinsic.reset" operacji, która zwraca qubit do $ \ket {0} $ przez zmierzenie i warunkowe wykonywanie operacji w oparciu o wynik. Takie pomiary niszczy wszelkie Entanglement z pozostałymi qubits i w związku z tym mają wpływ na obliczenia.


### <a name="borrowed-qubits"></a>Zapożyczony Qubits

Użyj `borrowing` instrukcji, aby alokować qubits do tymczasowego użytku, które nie muszą znajdować się w określonym stanie.

Podczas obliczeń można użyć zapożyczonej qubits jako miejsca do wypisania.
Te qubits zazwyczaj nie są w stanie czystym, oznacza to, że nie muszą być inicjowane w znanym stanie, takim jak $ \ket {0} $.
Są one często określane jako "zanieczyszczone" qubits, ponieważ ich stan jest nieznany i może nawet być Entangled z innymi częściami pamięci komputera Quantum.

Powiązanie jest zgodne z tym samym wzorcem i regułami, co `using` instrukcja.
Przykład:
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
Zapożyczone qubits znajdują się w nieznanym stanie i wykracza poza zakres na końcu bloku instrukcji.
Pożyczkobiorca zobowiązuje się do opuszczenia qubits w tym samym stanie, w którym znajdowały się one po ich zażyczeniu; oznacza to, że ich stan na początku i końcu bloku instrukcji powinien być taki sam.
Ponieważ ten stan nie jest stanem klasycznym, w większości przypadków zakresy pożyczek nie powinny zawierać pomiarów. 

W przypadku zaciągania qubits system najpierw próbuje wypełnić żądanie z qubits, które są używane, ale nie jest dostępne w treści `borrowing` instrukcji.
Jeśli nie ma wystarczającej ilości takich qubits, przydziela nowe qubits do wykonania żądania.

Wśród znanych przypadków użycia zanieczyszczonych qubits są implementacje bram CNOT z wieloma kontrolowanymi żądaniami, które wymagają tylko bardzo małej liczby qubits i implementacji przyrostów.
Aby zapoznać się z przykładem ich użycia w programie Q# , zobacz artykuł dotyczący [zaciągania Qubits](#borrowing-qubits-example) w tym artykule, a także wykorzystanie papieru [*2n + 2 Qubits z Toffoli modularnym*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler i Svore 2017) dla algorytmu, który używa pożyczek Qubits.

## <a name="intrinsic-operations"></a>Operacje wewnętrzne

Po przydzieleniu można przekazać qubit do funkcji i operacji.
W pewnym sensie jest to wszystko, że Q# program może wykonać qubit, ponieważ wszystkie akcje, które można podjąć, są zdefiniowane jako operacje.

W tym artykule omówiono kilka przydatnych Q# operacji, których można użyć do współdziałania z qubits.
Aby uzyskać więcej informacji na temat tych i innych [funkcji, zobacz wewnętrzne operacje i funkcje](xref:microsoft.quantum.libraries.standard.prelude). 

Najpierw operatory Single-qubit Pauli $X $, $Y $ i $Z $ są reprezentowane Q# przez operacje wewnętrzne [`X`](xref:microsoft.quantum.intrinsic.x) , [`Y`](xref:microsoft.quantum.intrinsic.y) , i [`Z`](xref:microsoft.quantum.intrinsic.z) , z których każdy ma typ `(Qubit => Unit is Adj + Ctl)` .

Zgodnie z opisem w [czynnościach i funkcjach wewnętrznych](xref:microsoft.quantum.libraries.standard.prelude)należy wziąć pod uwagę $X $ i w związku z tym, że `X` jest to operacja bitowa lub nie brama.
Za pomocą tej `X` operacji można przygotować Stany w postaci $ \ket{s_0 s_1 \dots s_n} $ dla niektórych klasycznych ciągów bitowych $s $:

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
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> Później zobaczysz bardziej kompaktowe sposoby zapisywania tej operacji, które nie wymagają ręcznego przepływu sterowania.

Możesz również przygotować takie Stany jak $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ i $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt $ przy {2} użyciu Hadamard Transform $H $, który jest reprezentowany Q# przez operację wewnętrzną [`H`](xref:microsoft.quantum.intrinsic.h) (również typ (qubit => Unit to przymiotnik + CTL) "):

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Miary

Pomiary poszczególnych qubits można wykonywać w różnych bazach, z których każda jest reprezentowana przez oś Pauli w [sferze Bloch](xref:microsoft.quantum.glossary#bloch-sphere).
*Podstawa obliczeniowa* odnosi się do `PauliZ` podstawy i jest najbardziej powszechną podstawą do pomiaru.

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>Mierzenie pojedynczej qubit w `PauliZ` oparciu o

Użyj [`M`](xref:microsoft.quantum.intrinsic.m) operacji, która jest wbudowaną wewnętrzną operacją niebędącą jednostką, do pomiaru pojedynczej qubit na `PauliZ` podstawę i przypisz wartość klasyczną do wyniku.
`M` ma zarezerwowany typ zwracany, `Result` który może przyjmować tylko wartości `Zero` lub `One` odpowiadające mierzonym stanom $ \ket {0} $ lub $ \ket {1} $-wskazującą, że wynik nie jest już stanem Quantum.

Prostym przykładem jest następująca operacja, która przydziela jeden qubit w stanie $ \ket {0} $, a następnie stosuje do niego operację Hadamard `H` i mierzy wynik `PauliZ` .

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>Mierzenie co najmniej jednego qubits w określonych bazach

Aby zmierzyć tablicę co najmniej jednego qubits w określonych bazach, można użyć [`Measure`](xref:microsoft.quantum.intrinsic.measure) operacji.

Dane wejściowe `Measure` są tablicą `Pauli` typów (na przykład `[PauliX, PauliZ, PauliZ]` ) i tablicą qubits.

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

Należy zauważyć, że ten przykład nadal wykonuje się tylko `Measure` na pojedynczych qubits po jednej naraz, ale operacja może zostać rozszerzona na wspólne pomiary na wielu qubitsach.

## <a name="borrowing-qubits-example"></a>Przykład pożyczania Qubits

Istnieją przykłady w formacie Canon, który używa `borrowing` słowa kluczowego, takiego jak następująca funkcja `MultiControlledXBorrow` . Jeśli `controls` określa, że kontrolka qubits ma zostać dodana do `X` operacji, liczba zanieczyszczonych [ancillas](xref:microsoft.quantum.glossary#ancilla) dodana przez tę implementację jest równa `Length(controls)-2` .

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

Należy zauważyć, że w tym przykładzie używane jest szerokie użycie `With` Combinator w postaci, która ma zastosowanie do operacji, które obsługują sąsiednie, na przykład `WithA` .
Jest to dobry styl programowania, ponieważ dodawanie kontroli do struktur obejmujących `With` propagowanie kontroli tylko do operacji wewnętrznej.
Należy również zauważyć, że oprócz `body` czynności, implementacja `controlled` treści operacji została jawnie dostarczona, a nie do `controlled auto` instrukcji.
Przyczyną tego jest to, że ze względu na strukturę obwodu można łatwo dodać dalsze kontrolki, które są korzystne w porównaniu z dodawaniem kontroli do poszczególnych bram w `body` . 

Należy poinstruować o porównaniu tego kodu z inną funkcją firmy Canon, `MultiControlledXClean` która osiąga ten sam cel implementacji `X` operacji mnożenia, ale używa kilku czystych qubits przy użyciu `using` mechanizmu. 

## <a name="next-steps"></a>Następne kroki

Więcej informacji na temat [przepływu sterowania](xref:microsoft.quantum.guide.controlflow) w programie Q# .
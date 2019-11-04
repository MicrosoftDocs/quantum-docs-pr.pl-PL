---
title: Praca z Qubits | Microsoft Docs
description: Praca z Qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: d1a8ccc9423a9a04e12bc98e3783790232b2f5d8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183475"
---
# <a name="working-with-qubits"></a>Praca z Qubits #

Po zapoznaniu się z różnymi częściami języka Q # poinformuj nas o tym, jak korzystać z samych qubits.

## <a name="allocating-qubits"></a>Alokowanie Qubits ##

Najpierw, aby uzyskać qubit, którego można użyć w Q #, *przydzielmy* qubits w bloku `using`:

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

Wszelkie qubits przydzielono w ten sposób, zaczynają się w stanie $ \ket{0}$; w powyższym przykładzie `register` jest w stanie $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.
Na końcu bloku `using` wszystkie qubits przydzielone przez ten blok są natychmiast cofane i nie można ich użyć.

> [!WARNING]
> Maszyny docelowe oczekują, że qubits znajdują się w stanie $ \ket{0}$ bezpośrednio przed cofnięciem alokacji, dzięki czemu mogą być ponownie używane i dostępne dla innych bloków `using` do alokacji.
> Jeśli to możliwe, użyj operacji jednostkowych, aby zwrócić wszystkie przydzieloną qubits do $ \ket{0}$.
> W razie potrzeby operacja @"microsoft.quantum.intrinsic.reset" może służyć do mierzenia qubit zamiast tego, i do użycia tego wyniku pomiaru, aby zapewnić, że mierzone qubit jest zwracany do $ \ket{0}$. Takie pomiar spowoduje zniszczenie wszelkich Entanglement z pozostałymi qubits i w związku z tym ma wpływ na obliczenia. 

## <a name="intrinsic-operations"></a>Operacje wewnętrzne ##

Po przydzieleniu qubit można następnie przesłać do funkcji i operacji.
W niektórych przypadkach jest to wszystko, że program Q # może wykonać qubit, ponieważ wszystkie akcje, które można podjąć, są zdefiniowane jako operacje.
Te operacje są bardziej szczegółowe w [operacjach i funkcjach wewnętrznych](xref:microsoft.quantum.libraries.standard.prelude), ale teraz wspominamy kilka przydatnych operacji, których można użyć do współpracy z qubits.

Najpierw operatory Single-qubit Pauli $X $, $Y $ i $Z $ są reprezentowane w Q # przez operacje wewnętrzne `X`, `Y`i `Z`, z których każdy ma typ `(Qubit => Unit is Adj + Ctl)`.
Zgodnie z opisem w [wewnętrznych operacjach i funkcjach](xref:microsoft.quantum.libraries.standard.prelude), można myśleć o $X $ i z tego powodu, aby `X` jako niezależna operacja.
Pozwala to nam przygotować Stany formularza $ \ket{s_0 s_1 \dots s_n} $ dla niektórych klasycznych ciągów bitowych $s $:

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

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> Później zobaczymy bardziej kompaktowe sposoby zapisywania tej operacji, które nie wymagają ręcznego sterowania przepływem.

Możemy również przygotować takie Stany jak $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ i $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ przy użyciu Hadamard Transform $H $ , która jest reprezentowana w Q # przez operację wewnętrzną `H : (Qubit => Unit is Adj + Ctl)`:

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

## <a name="measurements"></a>Miary ##

Za pomocą `Measure` operacji, która jest wbudowana w wewnętrznej operacji nienależącej do jednostki, możemy wyodrębnić klasyczne informacje z obiektu typu `Qubit` i przypisać wartość klasyczną w wyniku, który ma typ zastrzeżony `Result`, co oznacza, że wynik nie jest dłuższym stanem Quantum. Dane wejściowe do `Measure` to oś Pauli w sferze Bloch, reprezentowana przez obiekt typu `Pauli` (tj. na przykład `PauliX`) i obiekt typu `Qubit`. 

Prostym przykładem jest następująca operacja, która tworzy jeden qubit w stanie $ \ket{0}$, a następnie stosuje do niego bramę Hadamard ``H``, a następnie mierzy wynik w `PauliZ`. 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
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

Nieco bardziej skomplikowany przykład jest podany w następującej operacji, która zwraca wartość logiczną `true`, jeśli wszystkie qubits w rejestrze typu `Qubit[]` znajdują się w stanie zero, kiedy mierzone są określone Pauli i `false` w inny sposób. 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

Język Q # umożliwia zależności przepływu klasycznej kontroli nad wynikami pomiaru qubits. To z kolei umożliwia zaimplementowanie zaawansowanych probabilistyczneych gadżetów, które mogą zmniejszyć koszt obliczeniowy wdrożenia unitaries. Przykładowo można łatwo zaimplementować tak zwanego powtarzające się- *do-sukcesu* w Q #, które są obwodami probabilistyczne, które mają *przewidywane* niskie koszty w zakresie bram elementarnych, ale dla których rzeczywisty koszt zależy od rzeczywistego przebiegu i rzeczywiste odchodzenie między różnymi możliwymi gałęziami. 

Aby ułatwić wzorce powtarzania do sukcesu (jednostek ru), Q # obsługuje konstrukcję
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
gdzie `statementBlock1` i `statementBlock2` to zero lub więcej instrukcji Q # i `expression` dowolnym prawidłowym wyrażeniu, którego wynikiem jest wartość typu `Bool`. W typowym przypadku użycia następujący obwód implementuje obrót wokół osi niewymiernej $ (I + 2i Z)/\sqrt{5}$ w sferze Bloch. Jest to realizowane przy użyciu znanego wzorca jednostek ru: 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

W tym przykładzie pokazano użycie modyfikowalnej zmiennej `finished`, która jest w zakresie całej pętli REPEAT-until-Naprawa i która zostaje zainicjowana przed pętlą i zaktualizowaną w kroku naprawy.

Na koniec pokazujemy przykład wzorca jednostek ru, aby przygotować stan Quantum $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, rozpoczynając od stanu $ \ket{+} $. Zobacz również [przykład testowania jednostkowego w standardowej bibliotece](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs): 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
Istotne funkcje programistyczne przedstawione w tej operacji są bardziej skomplikowane `fixup` część pętli, która obejmuje operacje Quantum i użycie instrukcji `AssertProb` do ustalenia prawdopodobieństwa mierzenia stanu Quantum w określonych punktach w Program. Więcej informacji na temat `Assert` i `AssertProb` instrukcji można znaleźć w temacie [testowanie i debugowanie](xref:microsoft.quantum.techniques.testing-and-debugging) . 

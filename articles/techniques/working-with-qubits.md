---
title: Praca z Qubits
description: Dowiedz się, jak alokować qubits, używać ich w operacjach i funkcjach oraz mierzyć wyniki.
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 1aa2432996dda61d099e3b5bb4db78379ce43d97
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907651"
---
# <a name="working-with-qubits"></a><span data-ttu-id="7e991-103">Praca z Qubits</span><span class="sxs-lookup"><span data-stu-id="7e991-103">Working with Qubits</span></span>

<span data-ttu-id="7e991-104">Po zapoznaniu się z różnymi częściami języka Q # poinformuj nas o tym, jak korzystać z samych qubits.</span><span class="sxs-lookup"><span data-stu-id="7e991-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="7e991-105">Alokowanie Qubits</span><span class="sxs-lookup"><span data-stu-id="7e991-105">Allocating Qubits</span></span>

<span data-ttu-id="7e991-106">Najpierw, aby uzyskać qubit, którego można użyć w Q #, *przydzielmy* qubits w bloku `using`:</span><span class="sxs-lookup"><span data-stu-id="7e991-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="7e991-107">Wszelkie qubits przydzielono w ten sposób, zaczynają się w stanie $ \ket{0}$; w powyższym przykładzie `register` jest w stanie $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="7e991-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="7e991-108">Na końcu bloku `using` wszystkie qubits przydzielone przez ten blok są natychmiast cofane i nie można ich użyć.</span><span class="sxs-lookup"><span data-stu-id="7e991-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="7e991-109">Maszyny docelowe oczekują, że qubits znajdują się w stanie $ \ket{0}$ bezpośrednio przed cofnięciem alokacji, dzięki czemu mogą być ponownie używane i dostępne dla innych bloków `using` do alokacji.</span><span class="sxs-lookup"><span data-stu-id="7e991-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="7e991-110">Jeśli to możliwe, użyj operacji jednostkowych, aby zwrócić wszystkie przydzieloną qubits do $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="7e991-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="7e991-111">W razie potrzeby operacja @"microsoft.quantum.intrinsic.reset" może służyć do mierzenia qubit zamiast tego, i do użycia tego wyniku pomiaru, aby zapewnić, że mierzone qubit jest zwracany do $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="7e991-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="7e991-112">Takie pomiar spowoduje zniszczenie wszelkich Entanglement z pozostałymi qubits i w związku z tym ma wpływ na obliczenia.</span><span class="sxs-lookup"><span data-stu-id="7e991-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="7e991-113">Operacje wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="7e991-113">Intrinsic Operations</span></span>

<span data-ttu-id="7e991-114">Po przydzieleniu qubit można następnie przesłać do funkcji i operacji.</span><span class="sxs-lookup"><span data-stu-id="7e991-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="7e991-115">W niektórych przypadkach jest to wszystko, że program Q # może wykonać qubit, ponieważ wszystkie akcje, które można podjąć, są zdefiniowane jako operacje.</span><span class="sxs-lookup"><span data-stu-id="7e991-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="7e991-116">Te operacje są bardziej szczegółowe w [operacjach i funkcjach wewnętrznych](xref:microsoft.quantum.libraries.standard.prelude), ale teraz wspominamy kilka przydatnych operacji, których można użyć do współpracy z qubits.</span><span class="sxs-lookup"><span data-stu-id="7e991-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="7e991-117">Najpierw operatory Single-qubit Pauli $X $, $Y $ i $Z $ są reprezentowane w Q # przez operacje wewnętrzne `X`, `Y`i `Z`, z których każdy ma typ `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="7e991-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7e991-118">Zgodnie z opisem w [wewnętrznych operacjach i funkcjach](xref:microsoft.quantum.libraries.standard.prelude), można myśleć o $X $ i z tego powodu, aby `X` jako niezależna operacja.</span><span class="sxs-lookup"><span data-stu-id="7e991-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="7e991-119">Operacja `X` pozwala nam przygotować Stany w postaci $ \ket{s_0 s_1 \dots s_n} $ dla niektórych klasycznych ciągów bitowych $s $:</span><span class="sxs-lookup"><span data-stu-id="7e991-119">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="7e991-120">Później zobaczymy bardziej kompaktowe sposoby zapisywania tej operacji, które nie wymagają ręcznego sterowania przepływem.</span><span class="sxs-lookup"><span data-stu-id="7e991-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="7e991-121">Możemy również przygotować takie Stany jak $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ i $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ przy użyciu Hadamard Transform $H $, który jest reprezentowany przez Q # przez operację wewnętrzną `H : (Qubit => Unit is Adj + Ctl)`:</span><span class="sxs-lookup"><span data-stu-id="7e991-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="7e991-122">Miary</span><span class="sxs-lookup"><span data-stu-id="7e991-122">Measurements</span></span>

<span data-ttu-id="7e991-123">Przy użyciu operacji `Measure`, która jest wbudowaną wewnętrzną operacją niebędącą jednostką, możemy wyodrębnić klasyczne informacje z obiektu typu `Qubit` i przypisać wartość klasyczną w wyniku, który ma typ zarezerwowany `Result`, co oznacza, że wynik nie jest już stanem Quantum.</span><span class="sxs-lookup"><span data-stu-id="7e991-123">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="7e991-124">Dane wejściowe do `Measure` to oś Pauli w sferze Bloch, reprezentowana przez wartość typu `Pauli` (na przykład `PauliX`) i wartość typu `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="7e991-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="7e991-125">Prostym przykładem jest następująca operacja, która przydziela jeden qubit w stanie $ \ket{0}$, a następnie stosuje do niej `H` operację Hadamard i mierzy wynik `PauliZ`.</span><span class="sxs-lookup"><span data-stu-id="7e991-125">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="7e991-126">Nieco bardziej skomplikowany przykład jest podany w następującej operacji, która zwraca wartość logiczną `true`, jeśli wszystkie qubits w rejestrze typu `Qubit[]` są w stanie zero, gdy są mierzone w określonej Pauli, i które zwraca `false` w przeciwnym razie.</span><span class="sxs-lookup"><span data-stu-id="7e991-126">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="7e991-127">Język Q # zezwala, aby klasyczny przepływ sterowania był zależny od wyników pomiaru qubits.</span><span class="sxs-lookup"><span data-stu-id="7e991-127">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="7e991-128">Ta funkcja z kolei umożliwia wdrażanie zaawansowanych probabilistyczneych gadżetów, które mogą zmniejszyć koszt obliczeniowy wdrożenia unitaries.</span><span class="sxs-lookup"><span data-stu-id="7e991-128">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="7e991-129">Przykładowo można łatwo zaimplementować wzorce " *REPEAT-until-Success* " (jednostek ru) w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="7e991-129">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="7e991-130">Te wzorce jednostek ru są programami probabilistyczne, które mają *przewidywane* niskie koszty w zakresie bram elementarnych, ale dla których rzeczywisty koszt zależy od rzeczywistego przebiegu i rzeczywiste odchodzenie między różnymi możliwymi gałęziami.</span><span class="sxs-lookup"><span data-stu-id="7e991-130">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="7e991-131">Aby ułatwić wzorce powtarzania do sukcesu (jednostek ru), Q # obsługuje konstrukcję</span><span class="sxs-lookup"><span data-stu-id="7e991-131">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

<span data-ttu-id="7e991-132">gdzie `statementBlock1` i `statementBlock2` to zero lub więcej instrukcji Q # i `expression` dowolnym prawidłowym wyrażeniu, którego wynikiem jest wartość typu `Bool`.</span><span class="sxs-lookup"><span data-stu-id="7e991-132">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="7e991-133">W typowym przypadku użycia Następująca operacja Q # implementuje obrót wokół osi niewymiernej $ (I + 2i Z)/\sqrt{5}$ w sferze Bloch.</span><span class="sxs-lookup"><span data-stu-id="7e991-133">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="7e991-134">Jest to realizowane przy użyciu znanego wzorca jednostek ru:</span><span class="sxs-lookup"><span data-stu-id="7e991-134">This is accomplished by using a known RUS pattern:</span></span>

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

<span data-ttu-id="7e991-135">W tym przykładzie pokazano użycie modyfikowalnej zmiennej `finished`, która jest w zakresie całej pętli REPEAT-until-Naprawa i która zostaje zainicjowana przed pętlą i zaktualizowaną w kroku naprawy.</span><span class="sxs-lookup"><span data-stu-id="7e991-135">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="7e991-136">Na koniec pokazujemy przykład wzorca jednostek ru, aby przygotować stan Quantum $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, rozpoczynając od stanu $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="7e991-136">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="7e991-137">Zobacz również [przykład testowania jednostkowego w standardowej bibliotece](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="7e991-137">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
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

<span data-ttu-id="7e991-138">Istotne funkcje programistyczne przedstawione w tej operacji są bardziej skomplikowane `fixup` częścią pętli, która obejmuje operacje Quantum i użycie instrukcji `AssertProb` do ustalenia prawdopodobieństwa mierzenia stanu Quantum w określonych punktach w programie.</span><span class="sxs-lookup"><span data-stu-id="7e991-138">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="7e991-139">Więcej informacji na temat [`Assert`](xref:microsoft.quantum.intrinsic.assert) i [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operacji można znaleźć w temacie [testowanie i debugowanie](xref:microsoft.quantum.techniques.testing-and-debugging) .</span><span class="sxs-lookup"><span data-stu-id="7e991-139">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>

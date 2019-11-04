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
# <a name="working-with-qubits"></a><span data-ttu-id="90546-103">Praca z Qubits</span><span class="sxs-lookup"><span data-stu-id="90546-103">Working with Qubits</span></span> #

<span data-ttu-id="90546-104">Po zapoznaniu się z różnymi częściami języka Q # poinformuj nas o tym, jak korzystać z samych qubits.</span><span class="sxs-lookup"><span data-stu-id="90546-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="90546-105">Alokowanie Qubits</span><span class="sxs-lookup"><span data-stu-id="90546-105">Allocating Qubits</span></span> ##

<span data-ttu-id="90546-106">Najpierw, aby uzyskać qubit, którego można użyć w Q #, *przydzielmy* qubits w bloku `using`:</span><span class="sxs-lookup"><span data-stu-id="90546-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="90546-107">Wszelkie qubits przydzielono w ten sposób, zaczynają się w stanie $ \ket{0}$; w powyższym przykładzie `register` jest w stanie $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="90546-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="90546-108">Na końcu bloku `using` wszystkie qubits przydzielone przez ten blok są natychmiast cofane i nie można ich użyć.</span><span class="sxs-lookup"><span data-stu-id="90546-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="90546-109">Maszyny docelowe oczekują, że qubits znajdują się w stanie $ \ket{0}$ bezpośrednio przed cofnięciem alokacji, dzięki czemu mogą być ponownie używane i dostępne dla innych bloków `using` do alokacji.</span><span class="sxs-lookup"><span data-stu-id="90546-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="90546-110">Jeśli to możliwe, użyj operacji jednostkowych, aby zwrócić wszystkie przydzieloną qubits do $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="90546-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="90546-111">W razie potrzeby operacja @"microsoft.quantum.intrinsic.reset" może służyć do mierzenia qubit zamiast tego, i do użycia tego wyniku pomiaru, aby zapewnić, że mierzone qubit jest zwracany do $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="90546-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="90546-112">Takie pomiar spowoduje zniszczenie wszelkich Entanglement z pozostałymi qubits i w związku z tym ma wpływ na obliczenia.</span><span class="sxs-lookup"><span data-stu-id="90546-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span> 

## <a name="intrinsic-operations"></a><span data-ttu-id="90546-113">Operacje wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="90546-113">Intrinsic Operations</span></span> ##

<span data-ttu-id="90546-114">Po przydzieleniu qubit można następnie przesłać do funkcji i operacji.</span><span class="sxs-lookup"><span data-stu-id="90546-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="90546-115">W niektórych przypadkach jest to wszystko, że program Q # może wykonać qubit, ponieważ wszystkie akcje, które można podjąć, są zdefiniowane jako operacje.</span><span class="sxs-lookup"><span data-stu-id="90546-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="90546-116">Te operacje są bardziej szczegółowe w [operacjach i funkcjach wewnętrznych](xref:microsoft.quantum.libraries.standard.prelude), ale teraz wspominamy kilka przydatnych operacji, których można użyć do współpracy z qubits.</span><span class="sxs-lookup"><span data-stu-id="90546-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="90546-117">Najpierw operatory Single-qubit Pauli $X $, $Y $ i $Z $ są reprezentowane w Q # przez operacje wewnętrzne `X`, `Y`i `Z`, z których każdy ma typ `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="90546-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="90546-118">Zgodnie z opisem w [wewnętrznych operacjach i funkcjach](xref:microsoft.quantum.libraries.standard.prelude), można myśleć o $X $ i z tego powodu, aby `X` jako niezależna operacja.</span><span class="sxs-lookup"><span data-stu-id="90546-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="90546-119">Pozwala to nam przygotować Stany formularza $ \ket{s_0 s_1 \dots s_n} $ dla niektórych klasycznych ciągów bitowych $s $:</span><span class="sxs-lookup"><span data-stu-id="90546-119">This lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="90546-120">Później zobaczymy bardziej kompaktowe sposoby zapisywania tej operacji, które nie wymagają ręcznego sterowania przepływem.</span><span class="sxs-lookup"><span data-stu-id="90546-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="90546-121">Możemy również przygotować takie Stany jak $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ i $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ przy użyciu Hadamard Transform $H $ , która jest reprezentowana w Q # przez operację wewnętrzną `H : (Qubit => Unit is Adj + Ctl)`:</span><span class="sxs-lookup"><span data-stu-id="90546-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="90546-122">Miary</span><span class="sxs-lookup"><span data-stu-id="90546-122">Measurements</span></span> ##

<span data-ttu-id="90546-123">Za pomocą `Measure` operacji, która jest wbudowana w wewnętrznej operacji nienależącej do jednostki, możemy wyodrębnić klasyczne informacje z obiektu typu `Qubit` i przypisać wartość klasyczną w wyniku, który ma typ zastrzeżony `Result`, co oznacza, że wynik nie jest dłuższym stanem Quantum.</span><span class="sxs-lookup"><span data-stu-id="90546-123">Using the `Measure` operation, which is a built in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span> <span data-ttu-id="90546-124">Dane wejściowe do `Measure` to oś Pauli w sferze Bloch, reprezentowana przez obiekt typu `Pauli` (tj. na przykład `PauliX`) i obiekt typu `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="90546-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by an object of type `Pauli` (i.e., for instance `PauliX`) and an object of type `Qubit`.</span></span> 

<span data-ttu-id="90546-125">Prostym przykładem jest następująca operacja, która tworzy jeden qubit w stanie $ \ket{0}$, a następnie stosuje do niego bramę Hadamard ``H``, a następnie mierzy wynik w `PauliZ`.</span><span class="sxs-lookup"><span data-stu-id="90546-125">A simple example is the following operation which creates one qubit in the $\ket{0}$ state, then applies a Hadamard gate ``H`` to it and then measures the result in the `PauliZ` basis.</span></span> 

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

<span data-ttu-id="90546-126">Nieco bardziej skomplikowany przykład jest podany w następującej operacji, która zwraca wartość logiczną `true`, jeśli wszystkie qubits w rejestrze typu `Qubit[]` znajdują się w stanie zero, kiedy mierzone są określone Pauli i `false` w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="90546-126">A slightly more complicated example is given by the following operation which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero, when measured in a specified Pauli basis and `false` otherwise.</span></span> 

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

<span data-ttu-id="90546-127">Język Q # umożliwia zależności przepływu klasycznej kontroli nad wynikami pomiaru qubits.</span><span class="sxs-lookup"><span data-stu-id="90546-127">The Q# language allows dependencies of classical control flow on measurement results of qubits.</span></span> <span data-ttu-id="90546-128">To z kolei umożliwia zaimplementowanie zaawansowanych probabilistyczneych gadżetów, które mogą zmniejszyć koszt obliczeniowy wdrożenia unitaries.</span><span class="sxs-lookup"><span data-stu-id="90546-128">This in turn enables to implement powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span> <span data-ttu-id="90546-129">Przykładowo można łatwo zaimplementować tak zwanego powtarzające się- *do-sukcesu* w Q #, które są obwodami probabilistyczne, które mają *przewidywane* niskie koszty w zakresie bram elementarnych, ale dla których rzeczywisty koszt zależy od rzeczywistego przebiegu i rzeczywiste odchodzenie między różnymi możliwymi gałęziami.</span><span class="sxs-lookup"><span data-stu-id="90546-129">As an example, it is easy to implement so-called *Repeat-Until-Success* in Q# which are probabilistic circuits that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span> 

<span data-ttu-id="90546-130">Aby ułatwić wzorce powtarzania do sukcesu (jednostek ru), Q # obsługuje konstrukcję</span><span class="sxs-lookup"><span data-stu-id="90546-130">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
<span data-ttu-id="90546-131">gdzie `statementBlock1` i `statementBlock2` to zero lub więcej instrukcji Q # i `expression` dowolnym prawidłowym wyrażeniu, którego wynikiem jest wartość typu `Bool`.</span><span class="sxs-lookup"><span data-stu-id="90546-131">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span> <span data-ttu-id="90546-132">W typowym przypadku użycia następujący obwód implementuje obrót wokół osi niewymiernej $ (I + 2i Z)/\sqrt{5}$ w sferze Bloch.</span><span class="sxs-lookup"><span data-stu-id="90546-132">In a typical use case, the following circuit implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="90546-133">Jest to realizowane przy użyciu znanego wzorca jednostek ru:</span><span class="sxs-lookup"><span data-stu-id="90546-133">This is accomplished by using a known RUS pattern:</span></span> 

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

<span data-ttu-id="90546-134">W tym przykładzie pokazano użycie modyfikowalnej zmiennej `finished`, która jest w zakresie całej pętli REPEAT-until-Naprawa i która zostaje zainicjowana przed pętlą i zaktualizowaną w kroku naprawy.</span><span class="sxs-lookup"><span data-stu-id="90546-134">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="90546-135">Na koniec pokazujemy przykład wzorca jednostek ru, aby przygotować stan Quantum $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, rozpoczynając od stanu $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="90546-135">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span> <span data-ttu-id="90546-136">Zobacz również [przykład testowania jednostkowego w standardowej bibliotece](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="90546-136">See also the [unit testing sample provided with the standard library](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs):</span></span> 

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
 
<span data-ttu-id="90546-137">Istotne funkcje programistyczne przedstawione w tej operacji są bardziej skomplikowane `fixup` część pętli, która obejmuje operacje Quantum i użycie instrukcji `AssertProb` do ustalenia prawdopodobieństwa mierzenia stanu Quantum w określonych punktach w Program.</span><span class="sxs-lookup"><span data-stu-id="90546-137">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span> <span data-ttu-id="90546-138">Więcej informacji na temat `Assert` i `AssertProb` instrukcji można znaleźć w temacie [testowanie i debugowanie](xref:microsoft.quantum.techniques.testing-and-debugging) .</span><span class="sxs-lookup"><span data-stu-id="90546-138">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about `Assert` and `AssertProb` statements.</span></span> 

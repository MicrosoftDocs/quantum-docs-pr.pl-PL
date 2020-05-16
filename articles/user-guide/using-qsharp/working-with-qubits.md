---
title: Praca z kubitami
description: Opis wypełnienia
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430938"
---
# <a name="working-with-qubits"></a><span data-ttu-id="c5387-103">Praca z kubitami</span><span class="sxs-lookup"><span data-stu-id="c5387-103">Working with qubits</span></span>

<span data-ttu-id="c5387-104">Po zapoznaniu się z różnymi częściami języka Q # poinformuj nas o tym, jak korzystać z samych qubits.</span><span class="sxs-lookup"><span data-stu-id="c5387-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="c5387-105">Należy zauważyć, że żadna z tych instrukcji nie jest dozwolona w treści funkcji.</span><span class="sxs-lookup"><span data-stu-id="c5387-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="c5387-106">Są one prawidłowe tylko w obrębie operacji.</span><span class="sxs-lookup"><span data-stu-id="c5387-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="c5387-107">Alokowanie Qubits</span><span class="sxs-lookup"><span data-stu-id="c5387-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="c5387-108">Wyczyść qubits</span><span class="sxs-lookup"><span data-stu-id="c5387-108">Clean qubits</span></span>

<span data-ttu-id="c5387-109">`using`Instrukcja jest używana do *przydzielania* nowych qubits do użycia w bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c5387-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="c5387-110">Instrukcja składa się ze słowa kluczowego `using` , po którym następuje otwarty nawias `(` , powiązanie, nawias zamykający `)` i blok instrukcji, w ramach którego qubits będzie dostępny.</span><span class="sxs-lookup"><span data-stu-id="c5387-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="c5387-111">Powiązanie jest zgodne z tym samym wzorcem co `let` : pojedynczym symbolem lub krotką symboli, po którym następuje znak równości `=` oraz jedną wartością lub zgodną krotką *inicjatorów*.</span><span class="sxs-lookup"><span data-stu-id="c5387-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="c5387-112">Inicjatory są dostępne dla jednego qubit, wskazanego jako `Qubit()` lub tablicy qubits, `Qubit[n]` , gdzie `n` jest `Int` wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="c5387-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="c5387-113">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="c5387-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="c5387-114">Wszystkie qubits przydzieloną w ten sposób zaczynają się w stanie $ \ket {0} $; w powyższym przykładzie `register` jest to w stanie $ \ket {00000} = \ket \otimes \ket \otimes \cdots \otimes \ket {0} {0} {0} $.</span><span class="sxs-lookup"><span data-stu-id="c5387-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="c5387-115">Na końcu `using` bloku wszystkie qubits przydzielone przez ten blok są natychmiast cofane i nie można ich użyć.</span><span class="sxs-lookup"><span data-stu-id="c5387-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="c5387-116">Maszyny docelowe oczekują, że qubits są w stanie $ \ket {0} $ bezpośrednio przed cofnięciem alokacji, dzięki czemu mogą być ponownie używane i dostępne dla innych `using` bloków alokacji.</span><span class="sxs-lookup"><span data-stu-id="c5387-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="c5387-117">Jeśli to możliwe, użyj operacji jednostkowych, aby zwrócić wszystkie przydzieloną qubits do $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="c5387-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="c5387-118">W razie potrzeby @"microsoft.quantum.intrinsic.reset" operacja może służyć do mierzenia qubit zamiast tego, i do użycia tego wyniku pomiaru, aby upewnić się, że pomiar qubit jest zwracany do $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="c5387-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="c5387-119">Takie pomiar spowoduje zniszczenie wszelkich Entanglement z pozostałymi qubits i w związku z tym ma wpływ na obliczenia.</span><span class="sxs-lookup"><span data-stu-id="c5387-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="c5387-120">Zapożyczony Qubits</span><span class="sxs-lookup"><span data-stu-id="c5387-120">Borrowed Qubits</span></span>

<span data-ttu-id="c5387-121">`borrowing`Instrukcja jest używana do udostępnienia qubits do tymczasowego użytku, które nie muszą być w określonym stanie.</span><span class="sxs-lookup"><span data-stu-id="c5387-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="c5387-122">Mechanizm pożyczania umożliwia alokację qubits, która może być używana jako miejsce do rozliczania podczas obliczeń.</span><span class="sxs-lookup"><span data-stu-id="c5387-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="c5387-123">Te qubits zazwyczaj nie są w stanie czystym, tzn. nie muszą być inicjowane w znanym stanie, takim jak $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="c5387-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="c5387-124">Są one często określane jako "zanieczyszczone" qubits, ponieważ ich stan jest nieznany i może nawet być Entangled z innymi częściami pamięci komputera Quantum.</span><span class="sxs-lookup"><span data-stu-id="c5387-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="c5387-125">Powiązanie jest zgodne z tym samym wzorcem i regułami, co w `using` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c5387-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="c5387-126">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="c5387-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="c5387-127">Zapożyczone qubits znajdują się w nieznanym stanie i wykracza poza zakres na końcu bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c5387-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="c5387-128">Pożyczkobiorca zatwierdzi, aby opuszczał qubits w tym samym stanie, w którym były zapożyczone, tj. ich stan na początku i na końcu bloku instrukcji powinien być taki sam.</span><span class="sxs-lookup"><span data-stu-id="c5387-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="c5387-129">Ten stan w szczególności nie jest stanem klasycznym, takim jak w większości przypadków, zakresy pożyczek nie powinny zawierać pomiarów.</span><span class="sxs-lookup"><span data-stu-id="c5387-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="c5387-130">Podczas pożyczania qubits system najpierw spróbuje wypełnić żądanie z qubits, które są używane, ale nie są używane w treści `borrowing` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c5387-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="c5387-131">Jeśli nie ma wystarczającej ilości takich qubits, przydzieli nowe qubits do wykonania żądania.</span><span class="sxs-lookup"><span data-stu-id="c5387-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="c5387-132">Wśród znanych przypadków użycia zanieczyszczonych qubits są implementacje bram CNOT z wieloma kontrolowanymi żądaniami, które wymagają tylko bardzo małej liczby qubits i implementacji przyrostów.</span><span class="sxs-lookup"><span data-stu-id="c5387-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="c5387-133">Zapoznaj się z poniższym [przykładem pożyczek Qubits](#borrowing-qubits-example) , aby zobaczyć przykład ich użycia w pytaniach Q #, lub w [*oparciu o 2n + 2 Qubits with Toffoli modułowe mnożenia*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler i Svore 2017) dla algorytmu, który wykorzystuje pożyczone Qubits.</span><span class="sxs-lookup"><span data-stu-id="c5387-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="c5387-134">Operacje wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="c5387-134">Intrinsic Operations</span></span>

<span data-ttu-id="c5387-135">Po przydzieleniu qubit można następnie przesłać do funkcji i operacji.</span><span class="sxs-lookup"><span data-stu-id="c5387-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="c5387-136">W niektórych przypadkach jest to wszystko, że program Q # może wykonać qubit, ponieważ wszystkie akcje, które można podjąć, są zdefiniowane jako operacje.</span><span class="sxs-lookup"><span data-stu-id="c5387-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="c5387-137">Te operacje są bardziej szczegółowe w [operacjach i funkcjach wewnętrznych](xref:microsoft.quantum.libraries.standard.prelude), ale teraz wspominamy kilka przydatnych operacji, których można użyć do współpracy z qubits.</span><span class="sxs-lookup"><span data-stu-id="c5387-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="c5387-138">Najpierw operatory Single-qubit Pauli $X $, $Y $ i $Z $ są reprezentowane w Q # przez operacje wewnętrzne `X` , `Y` i `Z` , z których każdy ma typ `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="c5387-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="c5387-139">Zgodnie z opisem w [wewnętrznych operacjach i funkcjach](xref:microsoft.quantum.libraries.standard.prelude), można myśleć o $X $ i w związku z tym, że `X` jest to operacja bitowa lub niebrama.</span><span class="sxs-lookup"><span data-stu-id="c5387-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="c5387-140">`X`Operacja pozwala nam przygotować Stany w postaci $ \ket{s_0 s_1 \dots s_n} $ dla niektórych klasycznych ciągów bitowych $s $:</span><span class="sxs-lookup"><span data-stu-id="c5387-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="c5387-141">Później zobaczymy bardziej kompaktowe sposoby zapisywania tej operacji, które nie wymagają ręcznego sterowania przepływem.</span><span class="sxs-lookup"><span data-stu-id="c5387-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="c5387-142">Możemy również przygotować takie Stany jak $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ i $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt $ przy {2} użyciu Hadamard Transform $H $, który jest reprezentowany w Q # przez operację wewnętrzną `H : (Qubit => Unit is Adj + Ctl)` :</span><span class="sxs-lookup"><span data-stu-id="c5387-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="c5387-143">Miary</span><span class="sxs-lookup"><span data-stu-id="c5387-143">Measurements</span></span>

<span data-ttu-id="c5387-144">Przy użyciu `Measure` operacji, która jest wbudowaną wewnętrzną operacją niebędącą jednostką, możemy wyodrębnić klasyczne informacje z obiektu typu `Qubit` i przypisać wartość klasyczną w wyniku, który ma typ zarezerwowany `Result` , co oznacza, że wynik nie jest już stanem Quantum.</span><span class="sxs-lookup"><span data-stu-id="c5387-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="c5387-145">Dane wejściowe `Measure` to oś Pauli w sferze Bloch, reprezentowana przez wartość typu `Pauli` (na przykład `PauliX` ) i wartość typu `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="c5387-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="c5387-146">Prostym przykładem jest następująca operacja, która przydziela jeden qubit w stanie $ \ket {0} $, a następnie stosuje do niego operację Hadamard `H` i mierzy wynik `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="c5387-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="c5387-147">Nieco bardziej skomplikowany przykład jest podany w następującej operacji, która zwraca wartość logiczną, `true` Jeśli wszystkie qubits w rejestrze typu `Qubit[]` znajdują się w stanie zero, gdy jest mierzony w określonej Pauli i która zwraca w `false` przeciwnym razie.</span><span class="sxs-lookup"><span data-stu-id="c5387-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

## <a name="borrowing-qubits-example"></a><span data-ttu-id="c5387-148">Przykład pożyczania Qubits</span><span class="sxs-lookup"><span data-stu-id="c5387-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="c5387-149">W programie Canon istnieją przykłady, które używają `borrowing` słowa kluczowego, na przykład funkcja `MultiControlledXBorrow` zdefiniowana poniżej.</span><span class="sxs-lookup"><span data-stu-id="c5387-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="c5387-150">W przypadku `controls` określenia qubits kontrolki, która powinna zostać dodana do `X` operacji, `Length(controls)-2` w tej implementacji zostanie dodana ogólna liczba zanieczyszczonych ancillas.</span><span class="sxs-lookup"><span data-stu-id="c5387-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="c5387-151">Należy zauważyć, że rozległe użycie `With` combinator---w swojej formie, która ma zastosowanie do operacji, które obsługują sąsiednie, tj., `WithA` ---zostało wykonane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c5387-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="c5387-152">Jest to dobry styl programowania, ponieważ dodawanie kontroli do struktur obejmujących `With` propagowanie kontroli tylko do operacji wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="c5387-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="c5387-153">Należy również pamiętać, że w tym miejscu oprócz `body` operacji, implementacja `controlled` treści operacji została jawnie udostępniona, a nie do `controlled auto` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c5387-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="c5387-154">Przyczyną tego jest fakt, że wiemy ze struktury obwodu, jak łatwo dodać dalsze kontrolki, które są korzystne w porównaniu z dodawaniem kontroli do poszczególnych bram i każdej bramy w `body` .</span><span class="sxs-lookup"><span data-stu-id="c5387-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="c5387-155">Należy poinstruować o porównaniu tego kodu z inną funkcją firmy Canon, `MultiControlledXClean` która osiąga ten sam cel implementacji `X` operacji mnożenia, ale używa kilku czystych qubits przy użyciu `using` mechanizmu.</span><span class="sxs-lookup"><span data-stu-id="c5387-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="whats-next"></a><span data-ttu-id="c5387-156">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="c5387-156">What's Next?</span></span>
<span data-ttu-id="c5387-157">Więcej informacji na temat [przepływu sterowania](xref:microsoft.quantum.guide.controlflow) w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="c5387-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>
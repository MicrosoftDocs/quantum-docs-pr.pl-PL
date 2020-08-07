---
title: Praca z kubitami
description: Opis wypełnienia
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6808a852ee0de7d3a38ea44e9637eeaa6bea382a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867866"
---
# <a name="working-with-qubits"></a><span data-ttu-id="275a6-103">Praca z kubitami</span><span class="sxs-lookup"><span data-stu-id="275a6-103">Working with qubits</span></span>

<span data-ttu-id="275a6-104">Qubits to podstawowy obiekt informacji w ramach przetwarzania Quantum.</span><span class="sxs-lookup"><span data-stu-id="275a6-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="275a6-105">Aby zapoznać się z ogólnym wprowadzeniem do qubits, zobacz temat [Omówienie przetwarzania Quantum](xref:microsoft.quantum.overview.understanding)i aby uzyskać bardziej szczegółowe informacje na temat szczegółowe, zobacz [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="275a6-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="275a6-106">W tym artykule przedstawiono sposób użycia programu i pracy z programem qubits w Q# programie.</span><span class="sxs-lookup"><span data-stu-id="275a6-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="275a6-107">Żadna z instrukcji omówionych w tym artykule nie jest prawidłowa w treści funkcji.</span><span class="sxs-lookup"><span data-stu-id="275a6-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="275a6-108">Są one prawidłowe tylko w obrębie operacji.</span><span class="sxs-lookup"><span data-stu-id="275a6-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="275a6-109">Alokowanie Qubits</span><span class="sxs-lookup"><span data-stu-id="275a6-109">Allocating Qubits</span></span>

<span data-ttu-id="275a6-110">Ponieważ fizyczne qubits to cenny zasób na komputerze z systemem Quantum, część zadania kompilatora polega na tym, że są one używane tak efektywnie, jak to możliwe.</span><span class="sxs-lookup"><span data-stu-id="275a6-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="275a6-111">W związku z tym należy poinformować Q# o *przydzieleniu* qubits do użycia w ramach określonego bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="275a6-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="275a6-112">Możesz przydzielić qubits jako pojedynczy qubit lub jako tablicę qubits, znaną jako *Rejestr*.</span><span class="sxs-lookup"><span data-stu-id="275a6-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register*.</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="275a6-113">Wyczyść qubits</span><span class="sxs-lookup"><span data-stu-id="275a6-113">Clean qubits</span></span>

<span data-ttu-id="275a6-114">Użyj `using` instrukcji, aby przydzielić nowe qubits do użycia w bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="275a6-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="275a6-115">Instrukcja składa się ze słowa kluczowego `using` , po którym następuje powiązanie zawarte w nawiasach `( )` i blok instrukcji, w ramach którego qubits są dostępne.</span><span class="sxs-lookup"><span data-stu-id="275a6-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="275a6-116">Powiązanie jest zgodne z tym samym wzorcem co `let` : pojedynczym symbolem lub krotką symboli, po którym następuje znak równości `=` oraz jedną wartością lub zgodną krotką *inicjatorów*.</span><span class="sxs-lookup"><span data-stu-id="275a6-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="275a6-117">Inicjatory są dostępne dla jednego qubit, wskazanego jako `Qubit()` lub tablicy qubits, `Qubit[n]` , gdzie `n` jest `Int` wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="275a6-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="275a6-118">Przykład:</span><span class="sxs-lookup"><span data-stu-id="275a6-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="275a6-119">Wszystkie qubits przydzieloną w ten sposób zaczynają się w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="275a6-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="275a6-120">Tak więc w poprzednim przykładzie, `auxiliary` jest pojedynczym qubit w stanie $ \ket {0} $ i `register` jest w pięciu qubit stan $ \ket {00000} = \ket {0} \otimes \ket {0} \otimes \cdots \otimes \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="275a6-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="275a6-121">Na końcu `using` bloku wszystkie qubits przydzielone przez ten blok są natychmiast cofane i nie można ich użyć.</span><span class="sxs-lookup"><span data-stu-id="275a6-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="275a6-122">Maszyny docelowe mogą ponownie użyć cofniętej alokacji qubits i zaoferować je innym `using` blokom do przydzielenia.</span><span class="sxs-lookup"><span data-stu-id="275a6-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="275a6-123">W związku z tym maszyna docelowa oczekuje, że qubits są w stanie $ \ket {0} $ bezpośrednio przed cofnięciem alokacji.</span><span class="sxs-lookup"><span data-stu-id="275a6-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="275a6-124">Jeśli to możliwe, użyj operacji jednostkowych, aby zwrócić wszystkie przydzieloną qubits do $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="275a6-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="275a6-125">W razie potrzeby można użyć @"microsoft.quantum.intrinsic.reset" operacji, która zwraca qubit do $ \ket {0} $ przez zmierzenie i warunkowe wykonywanie operacji w oparciu o wynik.</span><span class="sxs-lookup"><span data-stu-id="275a6-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="275a6-126">Takie pomiary niszczy wszelkie Entanglement z pozostałymi qubits i w związku z tym mają wpływ na obliczenia.</span><span class="sxs-lookup"><span data-stu-id="275a6-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="275a6-127">Zapożyczony Qubits</span><span class="sxs-lookup"><span data-stu-id="275a6-127">Borrowed Qubits</span></span>

<span data-ttu-id="275a6-128">Użyj `borrowing` instrukcji, aby alokować qubits do tymczasowego użytku, które nie muszą znajdować się w określonym stanie.</span><span class="sxs-lookup"><span data-stu-id="275a6-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="275a6-129">Podczas obliczeń można użyć zapożyczonej qubits jako miejsca do wypisania.</span><span class="sxs-lookup"><span data-stu-id="275a6-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="275a6-130">Te qubits zazwyczaj nie są w stanie czystym, oznacza to, że nie muszą być inicjowane w znanym stanie, takim jak $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="275a6-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="275a6-131">Są one często określane jako "zanieczyszczone" qubits, ponieważ ich stan jest nieznany i może nawet być Entangled z innymi częściami pamięci komputera Quantum.</span><span class="sxs-lookup"><span data-stu-id="275a6-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="275a6-132">Powiązanie jest zgodne z tym samym wzorcem i regułami, co `using` instrukcja.</span><span class="sxs-lookup"><span data-stu-id="275a6-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="275a6-133">Przykład:</span><span class="sxs-lookup"><span data-stu-id="275a6-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="275a6-134">Zapożyczone qubits znajdują się w nieznanym stanie i wykracza poza zakres na końcu bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="275a6-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="275a6-135">Pożyczkobiorca zobowiązuje się do opuszczenia qubits w tym samym stanie, w którym znajdowały się one po ich zażyczeniu; oznacza to, że ich stan na początku i końcu bloku instrukcji powinien być taki sam.</span><span class="sxs-lookup"><span data-stu-id="275a6-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="275a6-136">Ponieważ ten stan nie jest stanem klasycznym, w większości przypadków zakresy pożyczek nie powinny zawierać pomiarów.</span><span class="sxs-lookup"><span data-stu-id="275a6-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="275a6-137">W przypadku zaciągania qubits system najpierw próbuje wypełnić żądanie z qubits, które są używane, ale nie jest dostępne w treści `borrowing` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="275a6-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="275a6-138">Jeśli nie ma wystarczającej ilości takich qubits, przydziela nowe qubits do wykonania żądania.</span><span class="sxs-lookup"><span data-stu-id="275a6-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="275a6-139">Wśród znanych przypadków użycia zanieczyszczonych qubits są implementacje bram CNOT z wieloma kontrolowanymi żądaniami, które wymagają tylko bardzo małej liczby qubits i implementacji przyrostów.</span><span class="sxs-lookup"><span data-stu-id="275a6-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="275a6-140">Aby zapoznać się z przykładem ich użycia w programie Q# , zobacz artykuł dotyczący [zaciągania Qubits](#borrowing-qubits-example) w tym artykule, a także wykorzystanie papieru [*2n + 2 Qubits z Toffoli modularnym*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler i Svore 2017) dla algorytmu, który używa pożyczek Qubits.</span><span class="sxs-lookup"><span data-stu-id="275a6-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="275a6-141">Operacje wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="275a6-141">Intrinsic Operations</span></span>

<span data-ttu-id="275a6-142">Po przydzieleniu można przekazać qubit do funkcji i operacji.</span><span class="sxs-lookup"><span data-stu-id="275a6-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="275a6-143">W pewnym sensie jest to wszystko, że Q# program może wykonać qubit, ponieważ wszystkie akcje, które można podjąć, są zdefiniowane jako operacje.</span><span class="sxs-lookup"><span data-stu-id="275a6-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="275a6-144">W tym artykule omówiono kilka przydatnych Q# operacji, których można użyć do współdziałania z qubits.</span><span class="sxs-lookup"><span data-stu-id="275a6-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="275a6-145">Aby uzyskać więcej informacji na temat tych i innych [funkcji, zobacz wewnętrzne operacje i funkcje](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="275a6-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="275a6-146">Najpierw operatory Single-qubit Pauli $X $, $Y $ i $Z $ są reprezentowane Q# przez operacje wewnętrzne [`X`](xref:microsoft.quantum.intrinsic.x) , [`Y`](xref:microsoft.quantum.intrinsic.y) , i [`Z`](xref:microsoft.quantum.intrinsic.z) , z których każdy ma typ `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="275a6-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:microsoft.quantum.intrinsic.x), [`Y`](xref:microsoft.quantum.intrinsic.y), and [`Z`](xref:microsoft.quantum.intrinsic.z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="275a6-147">Zgodnie z opisem w [czynnościach i funkcjach wewnętrznych](xref:microsoft.quantum.libraries.standard.prelude)należy wziąć pod uwagę $X $ i w związku z tym, że `X` jest to operacja bitowa lub nie brama.</span><span class="sxs-lookup"><span data-stu-id="275a6-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="275a6-148">Za pomocą tej `X` operacji można przygotować Stany w postaci $ \ket{s_0 s_1 \dots s_n} $ dla niektórych klasycznych ciągów bitowych $s $:</span><span class="sxs-lookup"><span data-stu-id="275a6-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="275a6-149">Później zobaczysz bardziej kompaktowe sposoby zapisywania tej operacji, które nie wymagają ręcznego przepływu sterowania.</span><span class="sxs-lookup"><span data-stu-id="275a6-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="275a6-150">Możesz również przygotować takie Stany jak $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ i $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\sqrt $ przy {2} użyciu Hadamard Transform $H $, który jest reprezentowany Q# przez operację wewnętrzną [`H`](xref:microsoft.quantum.intrinsic.h) (również typ (qubit => Unit to przymiotnik + CTL) "):</span><span class="sxs-lookup"><span data-stu-id="275a6-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:microsoft.quantum.intrinsic.h) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

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

## <a name="measurements"></a><span data-ttu-id="275a6-151">Miary</span><span class="sxs-lookup"><span data-stu-id="275a6-151">Measurements</span></span>

<span data-ttu-id="275a6-152">Pomiary poszczególnych qubits można wykonywać w różnych bazach, z których każda jest reprezentowana przez oś Pauli w [sferze Bloch](xref:microsoft.quantum.glossary#bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="275a6-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="275a6-153">*Podstawa obliczeniowa* odnosi się do `PauliZ` podstawy i jest najbardziej powszechną podstawą do pomiaru.</span><span class="sxs-lookup"><span data-stu-id="275a6-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="275a6-154">Mierzenie pojedynczej qubit w `PauliZ` oparciu o</span><span class="sxs-lookup"><span data-stu-id="275a6-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="275a6-155">Użyj [`M`](xref:microsoft.quantum.intrinsic.m) operacji, która jest wbudowaną wewnętrzną operacją niebędącą jednostką, do pomiaru pojedynczej qubit na `PauliZ` podstawę i przypisz wartość klasyczną do wyniku.</span><span class="sxs-lookup"><span data-stu-id="275a6-155">Use the [`M`](xref:microsoft.quantum.intrinsic.m) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="275a6-156">`M`ma zarezerwowany typ zwracany, `Result` który może przyjmować tylko wartości `Zero` lub `One` odpowiadające mierzonym stanom $ \ket {0} $ lub $ \ket {1} $-wskazującą, że wynik nie jest już stanem Quantum.</span><span class="sxs-lookup"><span data-stu-id="275a6-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="275a6-157">Prostym przykładem jest następująca operacja, która przydziela jeden qubit w stanie $ \ket {0} $, a następnie stosuje do niego operację Hadamard `H` i mierzy wynik `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="275a6-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="275a6-158">Mierzenie co najmniej jednego qubits w określonych bazach</span><span class="sxs-lookup"><span data-stu-id="275a6-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="275a6-159">Aby zmierzyć tablicę co najmniej jednego qubits w określonych bazach, można użyć [`Measure`](xref:microsoft.quantum.intrinsic.measure) operacji.</span><span class="sxs-lookup"><span data-stu-id="275a6-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:microsoft.quantum.intrinsic.measure) operation.</span></span>

<span data-ttu-id="275a6-160">Dane wejściowe `Measure` są tablicą `Pauli` typów (na przykład `[PauliX, PauliZ, PauliZ]` ) i tablicą qubits.</span><span class="sxs-lookup"><span data-stu-id="275a6-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="275a6-161">Nieco bardziej skomplikowany przykład jest podany w następującej operacji, która zwraca wartość logiczną, `true` Jeśli wszystkie qubits w rejestrze typu `Qubit[]` znajdują się w stanie zero, gdy jest mierzony w określonej Pauli i która zwraca w `false` przeciwnym razie.</span><span class="sxs-lookup"><span data-stu-id="275a6-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="275a6-162">Należy zauważyć, że ten przykład nadal wykonuje się tylko `Measure` na pojedynczych qubits po jednej naraz, ale operacja może zostać rozszerzona na wspólne pomiary na wielu qubitsach.</span><span class="sxs-lookup"><span data-stu-id="275a6-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="275a6-163">Przykład pożyczania Qubits</span><span class="sxs-lookup"><span data-stu-id="275a6-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="275a6-164">Istnieją przykłady w formacie Canon, który używa `borrowing` słowa kluczowego, takiego jak następująca funkcja `MultiControlledXBorrow` .</span><span class="sxs-lookup"><span data-stu-id="275a6-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="275a6-165">Jeśli `controls` określa, że kontrolka qubits ma zostać dodana do `X` operacji, liczba zanieczyszczonych [ancillas](xref:microsoft.quantum.glossary#ancilla) dodana przez tę implementację jest równa `Length(controls)-2` .</span><span class="sxs-lookup"><span data-stu-id="275a6-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

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

<span data-ttu-id="275a6-166">Należy zauważyć, że w tym przykładzie używane jest szerokie użycie `With` Combinator w postaci, która ma zastosowanie do operacji, które obsługują sąsiednie, na przykład `WithA` .</span><span class="sxs-lookup"><span data-stu-id="275a6-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="275a6-167">Jest to dobry styl programowania, ponieważ dodawanie kontroli do struktur obejmujących `With` propagowanie kontroli tylko do operacji wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="275a6-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="275a6-168">Należy również zauważyć, że oprócz `body` czynności, implementacja `controlled` treści operacji została jawnie dostarczona, a nie do `controlled auto` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="275a6-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="275a6-169">Przyczyną tego jest to, że ze względu na strukturę obwodu można łatwo dodać dalsze kontrolki, które są korzystne w porównaniu z dodawaniem kontroli do poszczególnych bram w `body` .</span><span class="sxs-lookup"><span data-stu-id="275a6-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="275a6-170">Należy poinstruować o porównaniu tego kodu z inną funkcją firmy Canon, `MultiControlledXClean` która osiąga ten sam cel implementacji `X` operacji mnożenia, ale używa kilku czystych qubits przy użyciu `using` mechanizmu.</span><span class="sxs-lookup"><span data-stu-id="275a6-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="275a6-171">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="275a6-171">Next steps</span></span>

<span data-ttu-id="275a6-172">Więcej informacji na temat [przepływu sterowania](xref:microsoft.quantum.guide.controlflow) w programie Q# .</span><span class="sxs-lookup"><span data-stu-id="275a6-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>
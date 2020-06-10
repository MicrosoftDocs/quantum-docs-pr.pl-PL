---
title: 'Operacje i funkcje w funkcji Q #'
description: Jak definiować i wywoływać operacje i funkcje, a także wyspecjalizowane specjalizacje operacji.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 6cfc1b14d86e86a1cbf0109d5e81dfe50c3a80bf
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630211"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="ad70d-103">Operacje i funkcje w funkcji Q #</span><span class="sxs-lookup"><span data-stu-id="ad70d-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="ad70d-104">Definiowanie nowych operacji</span><span class="sxs-lookup"><span data-stu-id="ad70d-104">Defining New Operations</span></span>

<span data-ttu-id="ad70d-105">Operacje są rdzeniem Q #.</span><span class="sxs-lookup"><span data-stu-id="ad70d-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="ad70d-106">Po zadeklarowaniu można je wywołać z klasycznej aplikacji .NET, np. przy użyciu symulatora lub innych operacji w ramach Q #.</span><span class="sxs-lookup"><span data-stu-id="ad70d-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="ad70d-107">Każda operacja zdefiniowana w Q # może następnie wywołać dowolną liczbę innych operacji, łącznie z wbudowanymi operacjami wewnętrznymi zdefiniowanymi przez język.</span><span class="sxs-lookup"><span data-stu-id="ad70d-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="ad70d-108">Określony sposób, w jaki te operacje wewnętrzne są zdefiniowane, zależy od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="ad70d-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="ad70d-109">Po skompilowaniu każda operacja jest reprezentowana jako typ klasy .NET, który można dostarczyć dla maszyn docelowych.</span><span class="sxs-lookup"><span data-stu-id="ad70d-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="ad70d-110">Każdy plik źródłowy Q # może definiować dowolną liczbę operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="ad70d-111">Nazwy operacji muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktów z nazwami typów lub funkcji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="ad70d-112">Deklaracja operacji składa się ze słowa kluczowego `operation` , po którym występuje symbol, który jest nazwą operacji, spójna kolekcja identyfikatorów, która definiuje argumenty do operacji, dwukropek `:` , adnotację typu opisującą typ wyniku operacji, opcjonalnie adnotację z charakterystykami operacji, otwierającym nawiasem klamrowym `{` , treścią deklaracji operacji i końcowym nawiasem zamykającym `}` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="ad70d-113">Każda operacja przyjmuje dane wejściowe, tworzy dane wyjściowe i określa Implementację dla co najmniej jednej specjalizacji operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="ad70d-114">Możliwe specjalizacje oraz sposób definiowania/wywoływania ich, są szczegółowo opisane poniżej.</span><span class="sxs-lookup"><span data-stu-id="ad70d-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="ad70d-115">Na razie Rozważmy następujące operacje, które definiują tylko domyślną specjalizację treści i pobierają pojedyncze qubit jako dane wejściowe, a następnie wywołują wbudowaną <xref:microsoft.quantum.intrinsic.x> operację na tym wejściu:</span><span class="sxs-lookup"><span data-stu-id="ad70d-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="ad70d-116">Słowo kluczowe `operation` rozpoczyna definicję operacji, a po niej następuje nazwa; tutaj, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="ad70d-117">Następnie typ danych wejściowych jest zdefiniowany jako `Qubit` , wraz z nazwą `target` odwołującą się do danych wejściowych w ramach nowej operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="ad70d-118">Podobnie definiuje, `Unit` że dane wyjściowe operacji są puste.</span><span class="sxs-lookup"><span data-stu-id="ad70d-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="ad70d-119">Jest to podobne do `void` języka C# i innych języków nieużywanych i jest równoważne `unit` w języku F # i innych językach funkcjonalnych.</span><span class="sxs-lookup"><span data-stu-id="ad70d-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="ad70d-120">Operacje mogą również zwracać bardziej interesujące typy niż `Unit` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="ad70d-121">Na przykład <xref:microsoft.quantum.intrinsic.m> operacja zwraca dane wyjściowe typu `Result` , reprezentujący wykonywanie pomiaru.</span><span class="sxs-lookup"><span data-stu-id="ad70d-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="ad70d-122">Możemy przekazać dane wyjściowe z operacji do innej operacji lub użyć jej przy użyciu `let` słowa kluczowego, aby zdefiniować nową zmienną.</span><span class="sxs-lookup"><span data-stu-id="ad70d-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="ad70d-123">Pozwala to na reprezentowanie klasycznego obliczenia, które współdziała z operacjami Quantum na niskim poziomie, na przykład w przypadku [kodowania w stojaku](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="ad70d-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="ad70d-124">Każda operacja w funkcji Q # przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.</span><span class="sxs-lookup"><span data-stu-id="ad70d-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="ad70d-125">Dane wejściowe i wyjściowe są następnie reprezentowane przy użyciu *krotek*, które zbierają wiele wartości w jedną wartość.</span><span class="sxs-lookup"><span data-stu-id="ad70d-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="ad70d-126">Nieformalnie Załóżmy, że Q # to język "Krotka w poziomie".</span><span class="sxs-lookup"><span data-stu-id="ad70d-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="ad70d-127">Postępując zgodnie z tym pojęciem, `()` należy go odczytać jako spójną krotkę, która ma typ `Unit` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="ad70d-128">Operacje kontrolowane i sąsiadujące</span><span class="sxs-lookup"><span data-stu-id="ad70d-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="ad70d-129">Jeśli operacja implementuje transformację jednostkową, podobnie jak w przypadku wielu operacji w Q #, można zdefiniować sposób działania operacji podczas *adjointed* lub *kontrolowania*.</span><span class="sxs-lookup"><span data-stu-id="ad70d-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="ad70d-130">*Podległych* specjalizacji operacji określa sposób działania "odwrotności" operacji, podczas gdy *kontrolowana* specjalizacja określa, jak działa operacja, gdy jej aplikacja jest kondycjonowana na stanie określonego rejestru Quantum.</span><span class="sxs-lookup"><span data-stu-id="ad70d-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="ad70d-131">Adjoints operacji Quantum są kluczowe dla wielu aspektów przetwarzania Quantum.</span><span class="sxs-lookup"><span data-stu-id="ad70d-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="ad70d-132">Dokładniej poniżej, w sekcji [sprzężenia](#conjugations) znajdziesz jedną taką sytuację omówioną wraz z użyteczną techniką programowania Q #.</span><span class="sxs-lookup"><span data-stu-id="ad70d-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="ad70d-133">Kontrolowana wersja operacji jest nową operacją, która efektywnie stosuje operację podstawową tylko wtedy, gdy wszystkie kontrolki qubits są w określonym stanie.</span><span class="sxs-lookup"><span data-stu-id="ad70d-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="ad70d-134">Jeśli kontrolka qubits znajduje się w położeniu, wówczas podstawowa operacja jest stosowana spójnie z odpowiednią częścią położenia.</span><span class="sxs-lookup"><span data-stu-id="ad70d-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="ad70d-135">W ten sposób kontrolowane operacje są często używane do generowania Entanglement.</span><span class="sxs-lookup"><span data-stu-id="ad70d-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="ad70d-136">W naturalny sposób *kontrolowanego* obszaru specjalizacji może istnieć również określenie kontrolowanej aplikacji sąsiadującej operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="ad70d-137">Jeśli $U $ to transformacja jednostkowa zaimplementowana przez operację `U` , `Adjoint U` reprezentuje ona transformację jednostkową $U ^ \dagger $, która jest złożonym transpozycję sprzężonej sprzężenia.</span><span class="sxs-lookup"><span data-stu-id="ad70d-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="ad70d-138">Po zastosowaniu operacji, a następnie jej współdziałaniu do stanu pozostawia stan niezmieniony, tak jak pokazano to jest fakt, że $UU ^ \dagger = U ^ \dagger U = \id $, macierz tożsamości.</span><span class="sxs-lookup"><span data-stu-id="ad70d-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="ad70d-139">Reprezentacja jednostkowa kontrolowanej operacji jest nieco bardziej złożonych, ale można znaleźć więcej szczegółów na temat [koncepcji przetwarzania Quantum: wielu qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="ad70d-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="ad70d-140">W poniższej sekcji opisano, jak wywoływać różne specjalizacje w kodzie Q.</span><span class="sxs-lookup"><span data-stu-id="ad70d-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="ad70d-141">Poniżej szczegółowo opisano sposób definiowania operacji do ich obsługi.</span><span class="sxs-lookup"><span data-stu-id="ad70d-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="ad70d-142">Wywoływanie specjalizacji operacji</span><span class="sxs-lookup"><span data-stu-id="ad70d-142">Calling operation specializations</span></span>

<span data-ttu-id="ad70d-143">*Funktor* w Q # to fabryka, która definiuje nową operację z innej operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="ad70d-144">Dwa standardowe funktory w pytaniach Q # są `Adjoint` i `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="ad70d-145">Funktory mają dostęp do implementacji operacji podstawowej podczas definiowania implementacji nowej operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="ad70d-146">W ten sposób funktory może wykonywać bardziej złożone funkcje niż tradycyjne funkcje wyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="ad70d-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="ad70d-147">Funktory nie ma reprezentacji w systemie typu Q #.</span><span class="sxs-lookup"><span data-stu-id="ad70d-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="ad70d-148">Obecnie nie można powiązać ich ze zmienną lub przekazać ich jako argumenty.</span><span class="sxs-lookup"><span data-stu-id="ad70d-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="ad70d-149">Funktor jest używany przez zastosowanie go do operacji, zwracając nową operację.</span><span class="sxs-lookup"><span data-stu-id="ad70d-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="ad70d-150">Na przykład operacja będąca wynikiem zastosowania `Adjoint` Funktor do `Y` operacji jest zapisywana jako `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="ad70d-151">Nowa operacja może następnie zostać wywołana jak każda inna operacja.</span><span class="sxs-lookup"><span data-stu-id="ad70d-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="ad70d-152">Aby operacja obsługiwała zastosowanie `Adjoint` i/lub `Controlled` funktory, jego typ zwracany musi być `Unit` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="ad70d-153">`Adjoint`Funktor</span><span class="sxs-lookup"><span data-stu-id="ad70d-153">`Adjoint` functor</span></span>

<span data-ttu-id="ad70d-154">W tym celu program `Adjoint Y(q1)` stosuje Funktor sąsiadujący do `Y` operacji w celu wygenerowania nowej operacji i stosuje tę nową operację do `q1` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="ad70d-155">Nowa operacja ma ten sam podpis i typ co operacja podstawowa `Y` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="ad70d-156">W szczególności Nowa operacja zezwala również na `Adjoint` użycie i tylko wtedy, `Controlled` gdy operacja podstawowa zakończyła się.</span><span class="sxs-lookup"><span data-stu-id="ad70d-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="ad70d-157">Sąsiadujący Funktor jest własnym odwrotnością; oznacza to, że `Adjoint Adjoint Op` jest zawsze taka sama jak `Op` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="ad70d-158">`Controlled`Funktor</span><span class="sxs-lookup"><span data-stu-id="ad70d-158">`Controlled` functor</span></span>

<span data-ttu-id="ad70d-159">Podobnie program `Controlled X(controls, target)` stosuje kontrolowane Funktor do `X` operacji w celu wygenerowania nowej operacji i stosuje tę nową operację do `controls` i `target` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="ad70d-160">W programie Q # kontrolowane wersje zawsze pobierają tablicę qubits kontroli, a określony stan jest zawsze przeznaczony dla wszystkich kontrolek qubits, które mają być w stanie obliczeniowym ( `PauliZ` ) `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="ad70d-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="ad70d-161">Kontrolę w oparciu o inne Stany można osiągnąć przez zastosowanie odpowiedniej operacji jednostkowej do kontrolki qubits przed operacją kontrolowanej, a następnie zastosowanie odwrotności operacji jednostkowej po kontrolowanej operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="ad70d-162">Na przykład zastosowanie `X` operacji do kontrolki qubit przed i po kontrolowanej operacji spowoduje, że operacja kontroluje `Zero` stan ($ \ket {0} $) dla tego qubit; stosowanie `H` operacji przed i po kontroli `PauliX` `One` stanu, czyli-1 eigenvalue Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $, a nie w `PauliZ` `One` stanie.</span><span class="sxs-lookup"><span data-stu-id="ad70d-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="ad70d-163">Po otrzymaniu wyrażenia operacji nowe wyrażenie operacji może być utworzone przy użyciu `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="ad70d-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="ad70d-164">Sygnatura nowej operacji jest oparta na podpisie oryginalnej operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="ad70d-165">Typ wyniku jest taki sam, ale typ danych wejściowych jest krotką dwukrotną z tablicą qubit, która przechowuje qubit kontrolki jako pierwszy element i argumenty oryginalnej operacji jako drugi element.</span><span class="sxs-lookup"><span data-stu-id="ad70d-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="ad70d-166">Nowa operacja obsługuje `Controlled` i będzie obsługiwać funkcję `Adjoint` if i tylko wtedy, gdy oryginalna operacja zakończyła się.</span><span class="sxs-lookup"><span data-stu-id="ad70d-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="ad70d-167">Jeśli oryginalna Operacja trwała tylko z pojedynczym argumentem, w tym miejscu będzie można odtwarzać pojedynczej korelacji krotek.</span><span class="sxs-lookup"><span data-stu-id="ad70d-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="ad70d-168">Na przykład `Controlled X` jest kontrolowana wersja `X` operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="ad70d-169">`X`ma typ `(Qubit => Unit is Adj + Ctl)` , więc `Controlled X` ma typ `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; ze względu na równoważność spójnej kolekcji, jest to taka sama jak `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="ad70d-170">Jeśli operacja podstawowa wymagała kilku argumentów, pamiętaj, aby ująć odpowiednie argumenty kontrolowanej wersji operacji w nawiasach, aby przekonwertować je na krotkę.</span><span class="sxs-lookup"><span data-stu-id="ad70d-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="ad70d-171">Na przykład `Controlled Rz` jest kontrolowana wersja `Rz` operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="ad70d-172">`Rz`ma typ `((Double, Qubit) => Unit is Adj + Ctl)` , więc `Controlled Rz` ma typ `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="ad70d-173">W rezultacie będzie `Controlled Rz(controls, (0.1, target))` to poprawne wywołanie `Controlled Rz` (należy zwrócić uwagę na nawiasy `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="ad70d-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="ad70d-174">Innym przykładem `CNOT(control, target)` może być implementacja `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="ad70d-175">Jeśli element docelowy powinien być kontrolowany przez 2 Control qubits (CCNOT), możemy użyć `Controlled X([control1, control2], target)` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="ad70d-176">`Controlled`I `Adjoint` funktory się, więc nie ma różnicy między stosowaniem `Controlled Adjoint Op` lub `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="ad70d-177">Definiowanie kontrolowanych i sąsiadujących implementacji</span><span class="sxs-lookup"><span data-stu-id="ad70d-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="ad70d-178">W pierwszym przykładzie deklaracji operacji, operacje `BitFlip` i `DecodeSuperdense` zostały zdefiniowane z podpisami `(Qubit => Unit)` i `((Qubit, Qubit) => (Result, Result))` odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="ad70d-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="ad70d-179">Jak `DecodeSuperdense` obejmuje pomiary, nie jest operacją jednostkową i w związku z tym nie może istnieć żadne kontrolowane niesąsiadujące specjalizacje (odwołaj powiązane wymaganie, aby ta operacja zwracała `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="ad70d-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="ad70d-180">Jednak `BitFlip` po prostu wykonuje operację jednostkową <xref:microsoft.quantum.intrinsic.x> , możemy ją zdefiniować przy użyciu obu specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="ad70d-181">W tym miejscu szczegółowo opisano, jak uwzględnić istnienie specjalizacji w deklaracjach operacji Q #, dzięki czemu można je wywołać w połączeniu z `Adjoint` i/lub `Controlled` funktory.</span><span class="sxs-lookup"><span data-stu-id="ad70d-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="ad70d-182">[Poniżej](#circumstances-for-validly-defining-specializations)opisano niektóre sytuacje, w których jest to prawidłowe lub nieprawidłowe, aby zadeklarować specjalizacje.</span><span class="sxs-lookup"><span data-stu-id="ad70d-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="ad70d-183">Charakterystyki operacji definiują, jakie rodzaje funktory można stosować do zadeklarowanej operacji oraz jaki ma wpływ.</span><span class="sxs-lookup"><span data-stu-id="ad70d-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="ad70d-184">Istnienie tych specjalizacji może być zadeklarowane jako część podpisu operacji, w odniesieniu do adnotacji z charakterystyką operacji: `is Adj` , `is Ctl` lub `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="ad70d-185">Rzeczywista implementacja każdej specjalizacji może być *jawnie* lub *jawnie* zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="ad70d-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="ad70d-186">Niejawnie Określanie implementacji</span><span class="sxs-lookup"><span data-stu-id="ad70d-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="ad70d-187">W takim przypadku treść deklaracji operacji składa się wyłącznie z implementacji domyślnej.</span><span class="sxs-lookup"><span data-stu-id="ad70d-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="ad70d-188">Przykład:</span><span class="sxs-lookup"><span data-stu-id="ad70d-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="ad70d-189">W tym miejscu odpowiednia implementacja dla każdej takiej niejawnie zadeklarowanej specjalizacji jest automatycznie generowana przez kompilator, która ma zostać wykonana w przypadku `Adjoint` `Controlled` użycia lub funktory.</span><span class="sxs-lookup"><span data-stu-id="ad70d-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="ad70d-190">Dlatego wywołanie `Adjoint PrepareEntangledPair` spowodowałaby kompilator implementujący sąsiadujące, `CNOT` a następnie sąsiadująco `H` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="ad70d-191">Te poszczególne operacje są samodzielne, więc wynikiem `Adjoint PrepareEntangledPair` operacji będzie po prostu zastosowanie, `CNOT(here, there)` a następnie `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="ad70d-192">W związku z tym możemy użyć tego `DecodeSuperdense` przykładu, aby napisać w powyższym przykładzie więcej kompaktów, przy użyciu sąsiadującej części `PrepareEntangledPair` do przekształcenia stanu Entangled z powrotem do pary unentangled qubits:</span><span class="sxs-lookup"><span data-stu-id="ad70d-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="ad70d-193">Adnotacja z charakterystyką operacji w deklaracji jest przydatna, aby zapewnić, że kompilator automatycznie generuje inne specjalizacje na podstawie domyślnej implementacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="ad70d-194">Istnieje kilka ważnych ograniczeń, które należy wziąć pod uwagę podczas projektowania operacji do użycia z funktory.</span><span class="sxs-lookup"><span data-stu-id="ad70d-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="ad70d-195">W przypadku niekrytycznej specjalizacji dla operacji korzystającej z wartości wyjściowej żadnej innej operacji *nie może* być automatycznie generowana przez kompilator, ponieważ jest niejednoznaczna w przypadku zmiany kolejności instrukcji w takiej operacji w celu uzyskania tego samego efektu.</span><span class="sxs-lookup"><span data-stu-id="ad70d-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="ad70d-196">W związku z tym często warto jawnie określić różne implementacje.</span><span class="sxs-lookup"><span data-stu-id="ad70d-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="ad70d-197">Jawne określanie implementacji</span><span class="sxs-lookup"><span data-stu-id="ad70d-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="ad70d-198">W przypadku, gdy implementacja nie może zostać wygenerowana przez kompilator, można ją jawnie określić.</span><span class="sxs-lookup"><span data-stu-id="ad70d-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="ad70d-199">Takie jawne deklaracje specjalizacji mogą składać się z odpowiedniej *dyrektywy generacji* lub implementacji zdefiniowanej przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ad70d-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="ad70d-200">Tutaj udostępniamy pełen zakres możliwości, z poniższymi przykładami.</span><span class="sxs-lookup"><span data-stu-id="ad70d-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="ad70d-201">Jawne deklaracje specjalizacji</span><span class="sxs-lookup"><span data-stu-id="ad70d-201">Explicit specialization declarations</span></span>

<span data-ttu-id="ad70d-202">Operacje Q # mogą zawierać następujące jawne deklaracje specjalizacji:</span><span class="sxs-lookup"><span data-stu-id="ad70d-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="ad70d-203">`body`Specjalizacja określa implementację operacji bez zastosowanych funktory.</span><span class="sxs-lookup"><span data-stu-id="ad70d-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="ad70d-204">`adjoint`Specjalizacja określa implementację operacji z `Adjoint` zastosowaniem Funktor.</span><span class="sxs-lookup"><span data-stu-id="ad70d-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="ad70d-205">`controlled`Specjalizacja określa implementację operacji z `Controlled` zastosowaniem Funktor.</span><span class="sxs-lookup"><span data-stu-id="ad70d-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="ad70d-206">`controlled adjoint`Specjalizacja określa implementację operacji z `Adjoint` `Controlled` zastosowaniem zarówno i funktory.</span><span class="sxs-lookup"><span data-stu-id="ad70d-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="ad70d-207">Ta specjalizacja może być również nazywana `adjoint controlled` , ponieważ dwie funktory.</span><span class="sxs-lookup"><span data-stu-id="ad70d-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="ad70d-208">Specjalizacja operacji składa się z tagu specjalizacji (np. `body` , lub `adjoint` itp.), po którym następuje jeden z:</span><span class="sxs-lookup"><span data-stu-id="ad70d-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="ad70d-209">Jawna deklaracja opisana poniżej.</span><span class="sxs-lookup"><span data-stu-id="ad70d-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="ad70d-210">*Dyrektywa* , która informuje kompilator, *jak* generować specjalizację, jeden z:</span><span class="sxs-lookup"><span data-stu-id="ad70d-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="ad70d-211">`intrinsic`, co oznacza, że specjalizacja jest udostępniana przez maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="ad70d-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="ad70d-212">`distribute`, które mogą być używane z `controlled` `controlled adjoint` specjalizacjami i.</span><span class="sxs-lookup"><span data-stu-id="ad70d-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="ad70d-213">Gdy jest używany z `controlled` , wskazuje, że kompilator powinien obliczyć specjalizację, stosując `Controlled` do wszystkich operacji w `body` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="ad70d-214">Gdy jest używany z `controlled adjoint` , wskazuje, że kompilator powinien obliczyć specjalizację przez zastosowanie `Controlled` do wszystkich operacji w `adjoint` specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="ad70d-215">`invert`, co oznacza, że kompilator powinien obliczyć `adjoint` specjalizację, odwracając `body` , tj. odwracanie kolejności operacji i stosując sąsiednie do każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="ad70d-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="ad70d-216">Gdy jest używany z `adjoint controlled` , oznacza to, że kompilator powinien obliczyć specjalizację, odwracając `controlled` specjalizację.</span><span class="sxs-lookup"><span data-stu-id="ad70d-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="ad70d-217">`self`, aby wskazać, że podległych specjalizacji jest taka sama jak `body` specjalizacja.</span><span class="sxs-lookup"><span data-stu-id="ad70d-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="ad70d-218">Jest to dozwolone dla `adjoint` `adjoint controlled` specjalizacji i.</span><span class="sxs-lookup"><span data-stu-id="ad70d-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="ad70d-219">W przypadku programu `adjoint controlled` `self` oznacza, że `adjoint controlled` specjalizacja jest taka sama jak `controlled` specjalizacja.</span><span class="sxs-lookup"><span data-stu-id="ad70d-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="ad70d-220">`auto`, aby wskazać, że kompilator powinien wybrać odpowiednią dyrektywę, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="ad70d-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="ad70d-221">`auto`nie można użyć dla `body` specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="ad70d-222">Dyrektywy i `auto` wszystkie wymagają zamykającego średnika `;` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="ad70d-223">`auto`Dyrektywa jest rozpoznawana jako następująca dyrektywa generacji, jeśli określono jawną deklarację `body` :</span><span class="sxs-lookup"><span data-stu-id="ad70d-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="ad70d-224">`adjoint`Specjalizacja jest generowana zgodnie z dyrektywą `invert` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="ad70d-225">`controlled`Specjalizacja jest generowana zgodnie z dyrektywą `distribute` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="ad70d-226">`adjoint controlled`Specjalizacja jest generowana zgodnie z dyrektywą `invert` , jeśli jawna Deklaracja dla `controlled` jest podano, ale nie dla `adjoint` , i `distribute` w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="ad70d-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="ad70d-227">Jeśli operacja jest samodzielna, należy jawnie określić sąsiadujące lub kontrolowane specjalizację za pomocą dyrektywy generacji, `self` Aby umożliwić kompilatorowi użycie tych informacji do celów optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="ad70d-228">Deklaracja specjalizacji, która zawiera implementację zdefiniowaną przez użytkownika, składa się z krotki argumentu, po której następuje blok instrukcji z kodem Q #, który implementuje specjalizację.</span><span class="sxs-lookup"><span data-stu-id="ad70d-228">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="ad70d-229">Na liście argumentów `...` służy do reprezentowania argumentów zadeklarowanych dla operacji jako całości.</span><span class="sxs-lookup"><span data-stu-id="ad70d-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="ad70d-230">Dla `body` i `adjoint` , lista argumentów powinna być zawsze `(...)` ; dla `controlled` i `adjoint controlled` , lista argumentów powinna być symbolem, który reprezentuje tablicę kontrolki qubits, a następnie `...` ujętą w nawiasy; na przykład `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="ad70d-231">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ad70d-231">Examples</span></span>

<span data-ttu-id="ad70d-232">Deklaracja operacji może być prosta jako następująca, która definiuje pierwotną operację Pauli X:</span><span class="sxs-lookup"><span data-stu-id="ad70d-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="ad70d-233">Należy zauważyć, że sąsiadująca operacja Pauli X została zdefiniowana z dyrektywą, `self` ponieważ według definicji `X` jest jej własnymi oddziałami.</span><span class="sxs-lookup"><span data-stu-id="ad70d-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="ad70d-234">Kod w `PrepareEntangledPair` powyższym przykładzie jest odpowiednikiem poniższego kodu zawierającego jawne deklaracje specjalizacji:</span><span class="sxs-lookup"><span data-stu-id="ad70d-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="ad70d-235">Słowo kluczowe `auto` wskazuje, że kompilator powinien określić sposób generowania implementacji specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="ad70d-236">Implementacja specjalizacji zdefiniowanej przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="ad70d-236">User-defined specialization implementation</span></span>

<span data-ttu-id="ad70d-237">Jeśli kompilator nie może automatycznie wygenerować implementacji dla konkretnej specjalizacji lub można określić bardziej wydajną implementację, implementacja może być również zdefiniowana ręcznie.</span><span class="sxs-lookup"><span data-stu-id="ad70d-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="ad70d-238">W powyższym przykładzie `adjoint invert;` wskazuje, że jest generowana podległych specjalizacji, odwracając implementację treści, i `controlled adjoint invert;` wskazuje, że kontrolowana podległych specjalizacji ma być generowana przez odwrócenie danej implementacji kontrolowanej specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="ad70d-239">Jeśli co najmniej jedna specjalizacja poza treścią domyślną musi być zadeklarowana w sposób jawny, implementacja treści domyślnej musi być opakowana do odpowiedniej deklaracji specjalizacji:</span><span class="sxs-lookup"><span data-stu-id="ad70d-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="ad70d-240">Warunki dotyczące prawidłowej definiowania specjalizacji</span><span class="sxs-lookup"><span data-stu-id="ad70d-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="ad70d-241">Deklaracje operacji z sąsiadującymi/kontrolowanymi</span><span class="sxs-lookup"><span data-stu-id="ad70d-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="ad70d-242">Istnieje możliwość określenia operacji bez wersji sąsiednich lub kontrolowanych.</span><span class="sxs-lookup"><span data-stu-id="ad70d-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="ad70d-243">Na przykład operacje pomiarów nie mają żadnego z nich, ponieważ nie są odwracalna ani nie są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="ad70d-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="ad70d-244">Operacja obsługuje `Adjoint` i/lub funktory, `Controlled` Jeśli jej deklaracja zawiera niejawną lub jawną deklarację odpowiednich specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="ad70d-245">Jawne zadeklarowane, sąsiadujące/kontrolowane specjalizacje implikuje istnienie podległych/kontrolowanej specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="ad70d-246">Dla operacji, której treść zawiera pętle REPEAT-until-Success, Set instrukcje, pomiary, instrukcje Return lub wywołania do innych operacji, które nie obsługują `Adjoint` Funktor, nie jest możliwe wygenerowanie przyległych specjalizacji po `invert` dyrektywie lub `auto` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="ad70d-247">Dla operacji, której treść zawiera wywołania do innych operacji, które nie obsługują `Controlled` Funktor, nie jest możliwe wygenerowanie kontrolowanej specjalizacji po `distribute` `auto` dyrektywie lub.</span><span class="sxs-lookup"><span data-stu-id="ad70d-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="ad70d-248">Kontrolowane sąsiadująco</span><span class="sxs-lookup"><span data-stu-id="ad70d-248">Controlled Adjoint</span></span>

<span data-ttu-id="ad70d-249">Kontrolowana sąsiadująca wersja operacji określa, jak jest zaimplementowana przeprowadzona przez Quantum wersja sąsiadującej operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="ad70d-250">Istnieje możliwość określenia operacji bez kontrolowanej wersji sąsiadującej; na przykład operacje pomiarów nie mają kontrolowanej wersji sąsiadującej, ponieważ nie są ani odwracalnae ani nie są dostępne.</span><span class="sxs-lookup"><span data-stu-id="ad70d-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="ad70d-251">Kontrolowana podległych specjalizacji dla operacji musi istnieć, jeśli i tylko wtedy, gdy istnieje zarówno przyległych, jak i kontrolowanych specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="ad70d-252">W takim przypadku istnienie kontrolowanej specjalizacji jest wnioskowane, a odpowiednia specjalizacja jest generowana przez kompilator, jeśli żadna implementacja nie została jawnie zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="ad70d-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="ad70d-253">Dla operacji, której treść zawiera wywołania do innych operacji, które nie mają kontrolowanej sąsiedniej wersji, Wygeneruj ponownie podległych specjalizacji po `invert` `distribute` `auto` dyrektywie lub nie jest możliwe.</span><span class="sxs-lookup"><span data-stu-id="ad70d-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="ad70d-254">Zgodność typów</span><span class="sxs-lookup"><span data-stu-id="ad70d-254">Type Compatibility</span></span>

<span data-ttu-id="ad70d-255">Operacja z dodatkowymi obsługiwanymi funktory może być używana wszędzie tam, gdzie operacja jest mniejsza niż funktory, ale oczekiwano tego samego podpisu.</span><span class="sxs-lookup"><span data-stu-id="ad70d-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="ad70d-256">Na przykład operacja typu `(Qubit => Unit is Adj)` może być używana wszędzie tam, gdzie `(Qubit => Unit)` oczekiwana jest operacja typu.</span><span class="sxs-lookup"><span data-stu-id="ad70d-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="ad70d-257">Q # jest *współwariantem* w odniesieniu do możliwego do zwrócenia typu zwracanego: wywoływany, który zwraca typ `'A` jest zgodny z tym samym typem danych wejściowych i typem wyniku, który `'A` jest zgodny z.</span><span class="sxs-lookup"><span data-stu-id="ad70d-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="ad70d-258">Q # jest *kontrawariantne* w odniesieniu do typów danych wejściowych: wywoływany typ `'A` jako dane wejściowe jest zgodny z wywoływanym z tym samym typem wyniku i typem danych wejściowych zgodnym z `'A` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="ad70d-259">Oznacza to, że podano następujące definicje:</span><span class="sxs-lookup"><span data-stu-id="ad70d-259">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="ad70d-260">spełnione są następujące kwestie:</span><span class="sxs-lookup"><span data-stu-id="ad70d-260">the following are true:</span></span>

- <span data-ttu-id="ad70d-261">Funkcja `ConjugateInvertWith` może zostać wywołana z `inner` argumentem `Invert` lub `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="ad70d-262">Funkcja `ConjugateUnitaryWith` może zostać wywołana z `inner` argumentem `ApplyUnitary` , ale nie `Invert` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="ad70d-263">Wartość typu `(Qubit[] => Unit is Adj + Ctl)` może być zwracana z elementu `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad70d-264">Q # 0,3 wprowadza znaczną różnicę w zachowaniu typów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ad70d-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="ad70d-265">Typy zdefiniowane przez użytkownika są traktowane jako opakowana wersja typu podstawowego, a nie jako podtyp.</span><span class="sxs-lookup"><span data-stu-id="ad70d-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="ad70d-266">Oznacza to, że wartość typu zdefiniowanego przez użytkownika nie jest użyteczna, gdy oczekiwana jest wartość typu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="ad70d-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="ad70d-267">Liczby sprzężone</span><span class="sxs-lookup"><span data-stu-id="ad70d-267">Conjugations</span></span>

<span data-ttu-id="ad70d-268">W przeciwieństwie do klasycznych bitów zwalnianie pamięci Quantum jest nieco bardziej zamierzone, ponieważ niequbitse Resetowanie może mieć niepożądane skutki dla pozostałych obliczeń, jeśli qubits nadal Entangled.</span><span class="sxs-lookup"><span data-stu-id="ad70d-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="ad70d-269">Można to uniknąć przez prawidłowe wykonanie obliczeń przed zwolnieniem pamięci.</span><span class="sxs-lookup"><span data-stu-id="ad70d-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="ad70d-270">Typowym wzorcem przetwarzania Quantum jest następujące:</span><span class="sxs-lookup"><span data-stu-id="ad70d-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="ad70d-271">Począwszy od naszego 0,9ej wersji, obsługujemy instrukcję sprzężenia, która implementuje przekształcenie powyżej.</span><span class="sxs-lookup"><span data-stu-id="ad70d-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="ad70d-272">Korzystając z tej instrukcji, `ApplyWith` można zaimplementować operację w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="ad70d-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="ad70d-273">Taka instrukcja sprzężona oczywiście jest znacznie bardziej użyteczna, jeśli transformacja zewnętrzna i wewnętrzna nie jest łatwo dostępna jako operacje, ale są bardziej wygodne do opisania przez blok składający się z kilku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="ad70d-274">Przekształcenie odwrotne dla instrukcji zdefiniowanych w bloku jest automatycznie generowane przez kompilator i wykonywane po zakończeniu stosu Apply.</span><span class="sxs-lookup"><span data-stu-id="ad70d-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="ad70d-275">Ponieważ żadne zmienne modyfikowalne używane jako część wewnątrz bloku nie mogą być ponownie powiązane w bloku Apply, wygenerowane przekształcenie jest gwarantowane jako sąsiadujące obliczenie w bloku.</span><span class="sxs-lookup"><span data-stu-id="ad70d-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="ad70d-276">Definiowanie nowych funkcji</span><span class="sxs-lookup"><span data-stu-id="ad70d-276">Defining New Functions</span></span>

<span data-ttu-id="ad70d-277">Funkcje są całkowicie deterministyczne, klasyczne procedury w Q #, które różnią się od operacji w tym, że nie mogą mieć żadnych efektów poza obliczaniem wartości wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="ad70d-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="ad70d-278">W szczególności funkcje nie mogą wywoływać operacji; Działaj na, alokuj lub zażycz qubits; Przykładowe liczby losowe; lub w inny sposób zależy od stanu poza wartością wejściową do funkcji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="ad70d-279">W związku z tym funkcje Q # są *czyste*, w tym przypadku zawsze mapują te same wartości wejściowe na te same wartości wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="ad70d-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="ad70d-280">Dzięki temu kompilator Q # może bezpiecznie zmienić kolejność i czas wywoływania funkcji podczas generowania specjalizacji operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="ad70d-281">Każdy plik źródłowy Q # może definiować dowolną liczbę funkcji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="ad70d-282">Nazwy funkcji muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktu z nazwami operacji lub typów.</span><span class="sxs-lookup"><span data-stu-id="ad70d-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="ad70d-283">Definiowanie funkcji działa podobnie do definiowania operacji, z tą różnicą, że dla funkcji nie można definiować podległych lub kontrolowanych specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="ad70d-284">Przykład:</span><span class="sxs-lookup"><span data-stu-id="ad70d-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="ad70d-285">lub</span><span class="sxs-lookup"><span data-stu-id="ad70d-285">or</span></span> 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="ad70d-286">Klasyczna logika w funkcjach = = dobra</span><span class="sxs-lookup"><span data-stu-id="ad70d-286">Classical logic in functions == good</span></span>

<span data-ttu-id="ad70d-287">Za każdym razem, gdy jest to możliwe, warto napisać klasyczną logikę pod kątem funkcji, a nie operacji, dzięki czemu można łatwiej używać jej w ramach operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="ad70d-288">Na przykład, jeśli `Square` podano wyżej deklarację jako *operację*, kompilator nie może zagwarantowania, że wywołanie go z tym samym elementem wejściowym spowoduje spójne generowanie tych samych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="ad70d-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="ad70d-289">Aby podkreślić różnicę między funkcjami i operacjami, należy wziąć pod uwagę problem z próbkami klasycznymi losowych, z poziomu operacji Q #:</span><span class="sxs-lookup"><span data-stu-id="ad70d-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="ad70d-290">Za każdym razem `U` , gdy jest wywoływana, będzie ona mieć inną akcję `target` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="ad70d-291">W szczególności kompilator nie może zagwarantować, że jeśli dodaliśmy `adjoint auto` deklarację specjalizacji do `U` , `U(target); Adjoint U(target);` działa jako tożsamość (to oznacza, że jako No-op).</span><span class="sxs-lookup"><span data-stu-id="ad70d-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="ad70d-292">Jest to naruszone w przypadku [wektorów i macierzy](xref:microsoft.quantum.concepts.vectors), takich jak automatyczne generowanie przyległych specjalizacji w operacji, w której wywołano operację, <xref:microsoft.quantum.math.randomreal> spowodowałoby to przerwanie gwarancji dostarczonych przez kompilator; <xref:microsoft.quantum.math.randomreal> jest operacją, dla której nie istnieje przyległych lub kontrolowana wersja.</span><span class="sxs-lookup"><span data-stu-id="ad70d-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="ad70d-293">Z drugiej strony, co pozwala na bezpieczne wywoływanie funkcji `Square` , w którym kompilator może mieć pewność, że tylko należy zachować dane wejściowe, aby `Square` zachować trwałość danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="ad70d-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="ad70d-294">W ten sposób izolowanie możliwie największej logiki w ramach funkcji pozwala łatwo ponownie wykorzystać tę logikę w innych funkcjach i operacjach.</span><span class="sxs-lookup"><span data-stu-id="ad70d-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="ad70d-295">Typy ogólne (sparametryzowane od typu)</span><span class="sxs-lookup"><span data-stu-id="ad70d-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="ad70d-296">Wiele funkcji i operacji, które firma Microsoft może chcieć zdefiniować, nie opiera się na typach ich danych wejściowych, ale raczej niejawnie używa ich typów za pośrednictwem innej funkcji lub operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="ad70d-297">Rozważmy na przykład, że koncepcja *mapy* jest wspólna dla wielu języków funkcjonalnych; dana funkcja $f (x) $ i Kolekcja wartości $ \{ x_1, x_2, \dots, x_n \} $, map zwraca nową kolekcję $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="ad70d-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="ad70d-298">W celu zaimplementowania tego zadania w programie Q # można skorzystać z tej funkcji jako pierwszej klasy.</span><span class="sxs-lookup"><span data-stu-id="ad70d-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="ad70d-299">Napiszmy do krótkiego przykładu `Map` , używając ★ jako symbolu zastępczego, a my powiemy, jakich typów potrzebujemy.</span><span class="sxs-lookup"><span data-stu-id="ad70d-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="ad70d-300">Należy zauważyć, że ta funkcja wygląda bardzo podobnie niezależnie od tego, jakie rzeczywiste typy zostały zastąpione.</span><span class="sxs-lookup"><span data-stu-id="ad70d-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="ad70d-301">Mapa z liczb całkowitych na Paul, na przykład, wygląda podobnie jak mapa od liczb zmiennoprzecinkowych do ciągów:</span><span class="sxs-lookup"><span data-stu-id="ad70d-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="ad70d-302">W zasadzie można napisać wersję `Map` dla każdej pary typów, które napotykamy, ale wprowadzamy wiele problemów.</span><span class="sxs-lookup"><span data-stu-id="ad70d-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="ad70d-303">Na przykład jeśli znajdziesz usterkę w programie `Map` , musimy upewnić się, że poprawka jest stosowana jednolicie we wszystkich wersjach programu `Map` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="ad70d-304">Ponadto, jeśli tworzymy nową spójną krotkę lub UDT, musimy teraz utworzyć nową, `Map` Aby przejść do nowego typu.</span><span class="sxs-lookup"><span data-stu-id="ad70d-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="ad70d-305">Chociaż jest to pozyskanie dla niewielkiej liczby takich funkcji, ponieważ zbieramy więcej i więcej funkcji tego samego formularza co `Map` , koszt wprowadzenia nowych typów stanie się nieuzasadniony w bardzo krótkim czasie.</span><span class="sxs-lookup"><span data-stu-id="ad70d-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="ad70d-306">Większość tego rodzaju trudności wynika jednak z tego, że kompilator nie udostępnił informacji niezbędnych do rozpoznania, w jaki sposób `Map` są powiązane różne wersje.</span><span class="sxs-lookup"><span data-stu-id="ad70d-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="ad70d-307">Efektywnie, chcemy, aby kompilator traktował `Map` jako rodzaj funkcji matematycznej z *typów* q # do funkcji q #.</span><span class="sxs-lookup"><span data-stu-id="ad70d-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="ad70d-308">Pojęcie to jest formalne przez umożliwienie funkcjom i operacjom posiadania *parametrów typu*, a także ich zwykłych parametrów krotek.</span><span class="sxs-lookup"><span data-stu-id="ad70d-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="ad70d-309">W powyższych przykładach chcemy traktować `Map` jako parametry typu `Int, Pauli` w pierwszym przypadku i `Double, String` w drugim przypadku.</span><span class="sxs-lookup"><span data-stu-id="ad70d-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="ad70d-310">W większości przypadków te parametry typu mogą być używane tak, jakby były typami zwyczajnymi: używamy wartości parametrów typu do wprowadzania tablic i krotek, wywoływania funkcji i operacji oraz przypisywania do zmiennych normalnych lub modyfikowalnych.</span><span class="sxs-lookup"><span data-stu-id="ad70d-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="ad70d-311">Największą sytuacją pośrednią jest to, że qubits, w którym program Q # nie może bezpośrednio polegać na strukturze `Qubit` typu, ale **musi** przekazać takie typy do innych operacji i funkcji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="ad70d-312">Powracając do powyższego przykładu, możemy zobaczyć, że musimy `Map` mieć parametry typu, jeden do reprezentowania danych wejściowych `fn` i jeden do reprezentowania danych wyjściowych `fn` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="ad70d-313">W polu Q # jest to zapisywana przez dodanie nawiasów kątowych ( `<>` nie brakets $ \braket {} $!) po nazwie funkcji lub operacji w jej deklaracji oraz przez wystawienie poszczególnych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="ad70d-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="ad70d-314">Nazwa każdego parametru typu musi rozpoczynać się od osi `'` , wskazując, że jest parametrem typu, a nie zwykłym typem (znanym także jako *konkretny* typ).</span><span class="sxs-lookup"><span data-stu-id="ad70d-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="ad70d-315">W `Map` tym celu napiszemy:</span><span class="sxs-lookup"><span data-stu-id="ad70d-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="ad70d-316">Należy zauważyć, że definicja `Map<'Input, 'Output>` wygląda bardzo podobna do wersji, które zostały wcześniej napisane.</span><span class="sxs-lookup"><span data-stu-id="ad70d-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="ad70d-317">Jedyną różnicą jest to, że został jawnie poinformowany kompilator, który `Map` nie zależy bezpośrednio od tego `'Input` , co `'Output` jest `fn`</span><span class="sxs-lookup"><span data-stu-id="ad70d-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="ad70d-318">Po zdefiniowaniu `Map<'Input, 'Output>` w ten sposób możemy ją wywoływać, ponieważ była to funkcja zwykła:</span><span class="sxs-lookup"><span data-stu-id="ad70d-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="ad70d-319">Pisanie funkcji ogólnych i operacji to jedno miejsce, w którym "krotka spójna z krotką" to bardzo użyteczny sposób, aby myśleć o funkcjach i operacjach pytań i odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="ad70d-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="ad70d-320">Ponieważ każda funkcja przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście, dane wejściowe typu `'T -> 'U` dopasowują *dowolną* funkcję Q #.</span><span class="sxs-lookup"><span data-stu-id="ad70d-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="ad70d-321">Podobnie każda operacja może zostać przeniesiona do wejściowego typu `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="ad70d-322">W drugim przykładzie należy wziąć pod uwagę wyzwanie napisania funkcji, która zwraca skład dwóch innych funkcji:</span><span class="sxs-lookup"><span data-stu-id="ad70d-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="ad70d-323">W tym miejscu należy określić dokładnie to `A` , co `B` i co `C` to jest, a tym samym znacznie ograniczyć narzędzie do nowej `Compose` funkcji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="ad70d-324">Po wszystko jest `Compose` zależne od `A` , `B` i `C` *przez* `innerFn` i `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="ad70d-325">Alternatywnie, możemy dodać parametry typu do `Compose` , które wskazują, że działa dla *dowolnego* `A` , `B` i `C` , tak długo, jak te parametry są zgodne z oczekiwanymi przez `innerFn` i `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="ad70d-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="ad70d-326">Biblioteki Q # Standard oferują wiele takich operacji i funkcji sparametryzowanych typu, aby ułatwić przepływ sterowania wyższym kolejnością.</span><span class="sxs-lookup"><span data-stu-id="ad70d-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="ad70d-327">Są one omówione bardziej szczegółowo w [przewodniku po bibliotece standardowej Q #](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="ad70d-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="ad70d-328">Możliwy do przełożenia jako wartości pierwszej klasy</span><span class="sxs-lookup"><span data-stu-id="ad70d-328">Callables as First-Class Values</span></span>

<span data-ttu-id="ad70d-329">Jedną z kluczowych technik z przyczyn dotyczących przepływu sterowania i klasycznej logiki przy użyciu funkcji, a nie operacji, jest wykorzystanie tych operacji i funkcji w Q # są *pierwszą klasą*.</span><span class="sxs-lookup"><span data-stu-id="ad70d-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="ad70d-330">Oznacza to, że są to poszczególne wartości w języku we własnym zakresie.</span><span class="sxs-lookup"><span data-stu-id="ad70d-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="ad70d-331">Na przykład, poniżej jest doskonale prawidłowy kod Q #, w przypadku niewielkiego pośrednika:</span><span class="sxs-lookup"><span data-stu-id="ad70d-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="ad70d-332">Wartość zmiennej `ourH` w powyższym fragmencie kodu jest następnie operacją <xref:microsoft.quantum.intrinsic.h> , która umożliwia wywołanie tej wartości podobnie jak każda inna operacja.</span><span class="sxs-lookup"><span data-stu-id="ad70d-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="ad70d-333">Dzięki temu możemy pisać operacje, które przyjmują operacje w ramach danych wejściowych, tworząc koncepcje przepływu sterowania wyższego rzędu.</span><span class="sxs-lookup"><span data-stu-id="ad70d-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="ad70d-334">Na przykład możemy Wyobraź sobie, że chcemy "kwadratowych" operacji, stosując ją dwa razy do tego samego elementu docelowego qubit.</span><span class="sxs-lookup"><span data-stu-id="ad70d-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="ad70d-335">Zwracanie operacji z funkcji</span><span class="sxs-lookup"><span data-stu-id="ad70d-335">Returning operations from a function</span></span>

<span data-ttu-id="ad70d-336">Podkreślamy, że możemy również zwrócić operacje w ramach danych wyjściowych, dzięki czemu można izolować pewne rodzaje klasycznej logiki warunkowej jako funkcję klasyczną, która zwraca opis programu Quantum w postaci operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="ad70d-337">W ramach prostego przykładu Rozważmy przykład teleportowego, w którym strona otrzymująca dwubitowy klasyczny komunikat musi użyć komunikatu, aby zdekodować qubit w odpowiedni stan teleportowy.</span><span class="sxs-lookup"><span data-stu-id="ad70d-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="ad70d-338">Możemy napisać to pod względem funkcji, która pobiera te dwa klasyczne bity i zwraca odpowiednią operację dekodowania.</span><span class="sxs-lookup"><span data-stu-id="ad70d-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="ad70d-339">Ta nowa funkcja jest w rzeczywistości funkcją, w tym przypadku, gdy wywołamy ją z tymi samymi wartościami `hereBit` i `thereBit` , zawsze będziemy wrócić do tej samej operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="ad70d-340">W związku z tym dekoder może być bezpiecznie uruchamiany wewnątrz operacji bez powodowania, jak logika dekodowania współdziała z definicjami różnych specjalizacji operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="ad70d-341">Oznacza to, że w funkcji jest izolowana klasyczna logika, która gwarantuje, że wywołanie funkcji można zmienić przy użyciu impunity, tak długo, jak dane wejściowe są zachowywane.</span><span class="sxs-lookup"><span data-stu-id="ad70d-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="ad70d-342">Aplikacja częściowa</span><span class="sxs-lookup"><span data-stu-id="ad70d-342">Partial Application</span></span>

<span data-ttu-id="ad70d-343">Możemy znacznie bardziej robić dzięki funkcjom, które zwracają operacje przy użyciu *częściowej aplikacji*, w którym możemy dostarczyć co najmniej jedną część danych wejściowych do funkcji lub operacji bez jej rzeczywistego wywoływania.</span><span class="sxs-lookup"><span data-stu-id="ad70d-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="ad70d-344">Na przykład, odwołując się do `ApplyTwice` powyższego przykładu, możemy wskazać, że nie chcemy, aby qubit operacji wejściowej:</span><span class="sxs-lookup"><span data-stu-id="ad70d-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="ad70d-345">W takim przypadku zmienna lokalna `twiceOp` przechowuje częściowo zastosowaną operację, w `ApplyTwice(op, _)` której części danych wejściowych, które nie zostały jeszcze określone, są wskazywane przez `_` .</span><span class="sxs-lookup"><span data-stu-id="ad70d-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="ad70d-346">Gdy rzeczywiście wywołujemy `twiceOp` w następnym wierszu, przekazujemy jako dane wejściowe do operacji częściowo zastosowanej wszystkie pozostałe części danych wejściowych do oryginalnej operacji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="ad70d-347">W związku z tym powyższym fragmentem jest efektywnie identyczny, aby był wywoływany `ApplyTwice(op, target)` bezpośrednio, Zapisz, że wprowadziliśmy nową zmienną lokalną, która pozwala nam opóźniać wywołanie, jednocześnie dostarczając niektóre części danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="ad70d-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="ad70d-348">Ponieważ operacja, która została częściowo zastosowana, nie jest faktycznie wywoływana do momentu udostępnienia całego danych wejściowych, możemy bezpiecznie zastosować operacje nawet z poziomu funkcji.</span><span class="sxs-lookup"><span data-stu-id="ad70d-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="ad70d-349">W zasadzie klasyczna logika w ramach `SquareOperation` mogły być znacznie inne, ale nadal jest odizolowana od reszty operacji przez gwarancje, które kompilator może zaoferować na informacje o funkcjach.</span><span class="sxs-lookup"><span data-stu-id="ad70d-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="ad70d-350">Ta metoda zostanie użyta w całej standardowej bibliotece Q # do wyrażenia klasycznego przepływu sterowania w sposób, który może być łatwo używany w ramach programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="ad70d-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="ad70d-351">Rekursja</span><span class="sxs-lookup"><span data-stu-id="ad70d-351">Recursion</span></span>

<span data-ttu-id="ad70d-352">Liczba wywoływanych Q może być bezpośrednio lub pośrednio cykliczna.</span><span class="sxs-lookup"><span data-stu-id="ad70d-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="ad70d-353">Oznacza to, że operacja lub funkcja może wywołać się sama lub wywołać inne wywołanie, które bezpośrednio lub pośrednio wywołuje operację, którą można wywołać.</span><span class="sxs-lookup"><span data-stu-id="ad70d-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="ad70d-354">Istnieją jednak dwa ważne komentarze dotyczące korzystania z rekursji:</span><span class="sxs-lookup"><span data-stu-id="ad70d-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="ad70d-355">Użycie rekursji w operacjach może zakłócać pewne optymalizacje.</span><span class="sxs-lookup"><span data-stu-id="ad70d-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="ad70d-356">Może to mieć znaczny wpływ na czas wykonywania algorytmu.</span><span class="sxs-lookup"><span data-stu-id="ad70d-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="ad70d-357">W przypadku wykonywania na rzeczywistym urządzeniu Quantum przestrzeń stosu może być ograniczona, a więc Szczegółowa rekursja może prowadzić do błędu czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="ad70d-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="ad70d-358">W szczególności kompilator Q # i środowisko wykonawcze nie identyfikują i nie optymalizują rekursji końcowego.</span><span class="sxs-lookup"><span data-stu-id="ad70d-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ad70d-359">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="ad70d-359">Next steps</span></span>

<span data-ttu-id="ad70d-360">Więcej informacji na temat [zmiennych](xref:microsoft.quantum.guide.variables) w Q #.</span><span class="sxs-lookup"><span data-stu-id="ad70d-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>
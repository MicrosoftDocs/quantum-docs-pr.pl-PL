---
title: 'Operacje i funkcje w Q#'
description: Jak definiować i wywoływać operacje i funkcje, a także wyspecjalizowane specjalizacje operacji.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 55e6d3e1a242386c46213083692377520df83a80
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692140"
---
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="b0dab-103">Operacje i funkcje w Q#</span><span class="sxs-lookup"><span data-stu-id="b0dab-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="b0dab-104">Definiowanie nowych operacji</span><span class="sxs-lookup"><span data-stu-id="b0dab-104">Defining New Operations</span></span>

<span data-ttu-id="b0dab-105">Operacje są podstawą programu Q# .</span><span class="sxs-lookup"><span data-stu-id="b0dab-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="b0dab-106">Po zadeklarowaniu można je wywołać z klasycznej aplikacji .NET, na przykład za pomocą symulatora lub przez inne operacje w programie Q# .</span><span class="sxs-lookup"><span data-stu-id="b0dab-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="b0dab-107">Każda operacja zdefiniowana w programie Q# może wywołać dowolną liczbę innych operacji, w tym wbudowane operacje wewnętrzne zdefiniowane przez język.</span><span class="sxs-lookup"><span data-stu-id="b0dab-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="b0dab-108">Określony sposób, w który Q# definiuje te operacje wewnętrzne, zależy od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="b0dab-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="b0dab-109">Po skompilowaniu każda operacja jest reprezentowana jako typ klasy .NET, który można dostarczyć dla maszyn docelowych.</span><span class="sxs-lookup"><span data-stu-id="b0dab-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="b0dab-110">Każdy Q# plik źródłowy może definiować dowolną liczbę operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="b0dab-111">Nazwy operacji muszą być unikatowe w obrębie przestrzeni nazw i nie mogą powodować konfliktów z nazwami typów lub funkcji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="b0dab-112">Deklaracja operacji składa się ze słowa kluczowego `operation` , po którym występuje symbol, który jest nazwą operacji, spójna kolekcja identyfikatorów, która definiuje argumenty do operacji, dwukropek `:` , adnotację typu opisującą typ wyniku operacji, opcjonalnie adnotację z charakterystykami operacji, otwartym nawiasem klamrowym, a następnie treść deklaracji operacji ujętą w nawiasy klamrowe `{ }` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="b0dab-113">Każda operacja przyjmuje dane wejściowe, tworzy dane wyjściowe i określa Implementację dla co najmniej jednej specjalizacji operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="b0dab-114">Możliwe specjalizacje oraz sposób definiowania i wywoływania tych elementów są szczegółowo opisane w różnych sekcjach tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="b0dab-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="b0dab-115">Na razie Rozważmy następujące operacje, które definiują tylko domyślną specjalizację treści i pobierają pojedyncze qubit jako dane wejściowe, a następnie wywołują wbudowaną <xref:Microsoft.Quantum.Intrinsic.X> operację na tym wejściu:</span><span class="sxs-lookup"><span data-stu-id="b0dab-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:Microsoft.Quantum.Intrinsic.X> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="b0dab-116">Słowo kluczowe `operation` rozpoczyna definicję operacji, po której następuje nazwa; tutaj, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="b0dab-117">Następnie typ danych wejściowych jest zdefiniowany ( `Qubit` ), wraz z nazwą,, w odniesieniu `target` do danych wejściowych w ramach nowej operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="b0dab-118">Wreszcie definiuje, `Unit` że dane wyjściowe operacji są puste.</span><span class="sxs-lookup"><span data-stu-id="b0dab-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="b0dab-119">`Unit` jest używany podobnie do `void` języka C# i innych nieużywanych języków i jest odpowiednikiem `unit` w języku F # i innych językach funkcjonalnych.</span><span class="sxs-lookup"><span data-stu-id="b0dab-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="b0dab-120">Operacje mogą również zwracać bardziej interesujące typy niż `Unit` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="b0dab-121">Na przykład <xref:Microsoft.Quantum.Intrinsic.m> operacja zwraca dane wyjściowe typu `Result` , reprezentujący wykonywanie pomiaru.</span><span class="sxs-lookup"><span data-stu-id="b0dab-121">For instance, the <xref:Microsoft.Quantum.Intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="b0dab-122">Można przekazać ją z operacji do innej operacji lub użyć jej ze `let` słowem kluczowym, aby zdefiniować nową zmienną.</span><span class="sxs-lookup"><span data-stu-id="b0dab-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="b0dab-123">Takie podejście umożliwia reprezentowanie klasycznego obliczenia, które współdziała z operacjami Quantum na niskim poziomie, na przykład w przypadku [kodowania](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding)z nadmiernym użyciem:</span><span class="sxs-lookup"><span data-stu-id="b0dab-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="b0dab-124">Każda operacja w programie Q# przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.</span><span class="sxs-lookup"><span data-stu-id="b0dab-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="b0dab-125">Wiele danych wejściowych i wyjściowych jest przedstawianych przy użyciu *krotek* , które zbierają wiele wartości w jedną wartość.</span><span class="sxs-lookup"><span data-stu-id="b0dab-125">Multiple inputs and outputs are represented using *tuples* , which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="b0dab-126">W tym przypadku Q# jest językiem "Krotka w kolekcji".</span><span class="sxs-lookup"><span data-stu-id="b0dab-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="b0dab-127">Po tym koncepcji zestaw pustych nawiasów `()` powinien zostać odczytany jako krotka "Empty", która ma typ `Unit` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="b0dab-128">Operacje kontrolowane i sąsiadujące</span><span class="sxs-lookup"><span data-stu-id="b0dab-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="b0dab-129">Jeśli operacja implementuje transformację jednostkową, tak jak w przypadku wielu operacji w Q# , można zdefiniować sposób działania operacji przy *adjointed* lub *kontrolowanej* .</span><span class="sxs-lookup"><span data-stu-id="b0dab-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled* .</span></span> <span data-ttu-id="b0dab-130">*Podległych* specjalizacji operacji określa sposób działania "odwrotności" operacji, podczas gdy *kontrolowana* specjalizacja określa, jak działa operacja, gdy jej aplikacja jest kondycjonowana na stanie określonego rejestru Quantum.</span><span class="sxs-lookup"><span data-stu-id="b0dab-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="b0dab-131">Adjoints operacji Quantum są kluczowe dla wielu aspektów przetwarzania Quantum.</span><span class="sxs-lookup"><span data-stu-id="b0dab-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="b0dab-132">Przykład jednej takiej sytuacji omówionej wraz z użyteczną Q# techniką programowania można znaleźć w temacie [sterowanie przepływem: sprzężenia](xref:microsoft.quantum.guide.controlflow#conjugations).</span><span class="sxs-lookup"><span data-stu-id="b0dab-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Control Flow: Conjugations](xref:microsoft.quantum.guide.controlflow#conjugations).</span></span> <span data-ttu-id="b0dab-133">Kontrolowana wersja operacji jest nową operacją, która efektywnie stosuje operację podstawową tylko wtedy, gdy wszystkie kontrolki qubits są w określonym stanie.</span><span class="sxs-lookup"><span data-stu-id="b0dab-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="b0dab-134">Jeśli kontrolka qubits znajduje się w położeniu, wówczas podstawowa operacja jest stosowana spójnie z odpowiednią częścią położenia.</span><span class="sxs-lookup"><span data-stu-id="b0dab-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="b0dab-135">W ten sposób kontrolowane operacje są często używane do generowania Entanglement.</span><span class="sxs-lookup"><span data-stu-id="b0dab-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="b0dab-136">W naturalny sposób *kontrolowanego* obszaru specjalizacji może istnieć również określenie kontrolowanej aplikacji sąsiadującej operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="b0dab-137">Jeśli $U $ to transformacja jednostkowa zaimplementowana przez operację `U` , `Adjoint U` reprezentuje ona transformację jednostkową $U ^ \dagger $, która jest złożonym transpozycję sprzężonej sprzężenia.</span><span class="sxs-lookup"><span data-stu-id="b0dab-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="b0dab-138">Po zastosowaniu operacji, a następnie jej współdziałaniu do stanu pozostawia stan niezmieniony, tak jak pokazano to jest fakt, że $UU ^ \dagger = U ^ \dagger U = \id $, macierz tożsamości.</span><span class="sxs-lookup"><span data-stu-id="b0dab-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="b0dab-139">Reprezentacja jednostkowa kontrolowanej operacji jest nieco bardziej złożonych, ale można znaleźć więcej szczegółów na temat [koncepcji przetwarzania Quantum: wielu qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="b0dab-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="b0dab-140">W poniższej sekcji opisano, jak wywoływać różne specjalizacje w Q# kodzie oraz jak definiować operacje do ich obsługi.</span><span class="sxs-lookup"><span data-stu-id="b0dab-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="b0dab-141">Wywoływanie specjalizacji operacji</span><span class="sxs-lookup"><span data-stu-id="b0dab-141">Calling operation specializations</span></span>

<span data-ttu-id="b0dab-142">*Funktor* w programie Q# to fabryka, która definiuje nową operację z innej operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="b0dab-143">Dwie standardowe funktory w programie Q# to `Adjoint` i `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="b0dab-144">Funktory mają dostęp do implementacji operacji podstawowej podczas definiowania implementacji nowej operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="b0dab-145">W ten sposób funktory może wykonywać bardziej złożone funkcje niż tradycyjne funkcje wyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="b0dab-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="b0dab-146">Funktory nie ma reprezentacji w Q# systemie typów.</span><span class="sxs-lookup"><span data-stu-id="b0dab-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="b0dab-147">Obecnie nie można powiązać ich ze zmienną lub przekazać ich jako argumenty.</span><span class="sxs-lookup"><span data-stu-id="b0dab-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="b0dab-148">Użyj Funktor, stosując go do operacji, która zwraca nową operację.</span><span class="sxs-lookup"><span data-stu-id="b0dab-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="b0dab-149">Na przykład zastosowanie `Adjoint` Funktor do `Y` operacji zwraca nową operację `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="b0dab-150">Nową operację można wywołać tak jak każda inna operacja.</span><span class="sxs-lookup"><span data-stu-id="b0dab-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="b0dab-151">W przypadku operacji do obsługi aplikacji `Adjoint` lub `Controlled` funktory jej typ zwracany musi być `Unit` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="b0dab-152">`Adjoint` Funktor</span><span class="sxs-lookup"><span data-stu-id="b0dab-152">`Adjoint` functor</span></span>

<span data-ttu-id="b0dab-153">W tym celu program `Adjoint Y(q1)` stosuje `Adjoint` Funktor do `Y` operacji w celu wygenerowania nowej operacji i stosuje tę nową operację do `q1` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="b0dab-154">Nowa operacja ma ten sam podpis i typ co operacja podstawowa `Y` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="b0dab-155">W szczególności Nowa operacja obsługuje także `Adjoint` i obsługuje tylko wtedy, `Controlled` gdy operacja podstawowa zakończyła się.</span><span class="sxs-lookup"><span data-stu-id="b0dab-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="b0dab-156">`Adjoint`Funktor jest własnym odwrotnością; oznacza to, że `Adjoint Adjoint Op` jest zawsze taka sama jak `Op` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="b0dab-157">`Controlled` Funktor</span><span class="sxs-lookup"><span data-stu-id="b0dab-157">`Controlled` functor</span></span>

<span data-ttu-id="b0dab-158">Podobnie program `Controlled X(controls, target)` stosuje `Controlled` Funktor do `X` operacji w celu wygenerowania nowej operacji i stosuje tę nową operację do `controls` i `target` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="b0dab-159">W systemie Q# kontrolowane wersje zawsze przyjmują tablicę kontrolek qubits, a kontrola jest zawsze oparta na wszystkich formantach qubits w stanie obliczeniowym ( `PauliZ` ) `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="b0dab-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="b0dab-160">Kontrola oparta na innych Stanach jest osiągana przez zastosowanie odpowiedniej operacji jednostkowej do kontrolki qubits przed operacją sterowaną, a następnie zastosowanie odwrotności operacji jednostkowej po kontrolowanej operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="b0dab-161">Na przykład stosowanie `X` operacji do kontrolki qubit przed i po kontrolowanej operacji powoduje, że operacja kontroluje `Zero` stan ($ \ket {0} $) dla tego qubit; stosowanie `H` operacji przed i po kontrolkach `PauliX` `One` stanu, czyli-1 eigenvalue Pauli X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )/\sqrt {2} $, a nie `PauliZ` `One` stan.</span><span class="sxs-lookup"><span data-stu-id="b0dab-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="b0dab-162">Po otrzymaniu wyrażenia operacji można utworzyć nowe wyrażenie operacji przy użyciu `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="b0dab-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="b0dab-163">Sygnatura nowej operacji jest oparta na podpisie oryginalnej operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="b0dab-164">Typ wyniku jest taki sam, ale typ danych wejściowych jest krotką dwukrotną z tablicą qubit, która przechowuje qubit kontrolki jako pierwszy element i argumenty oryginalnej operacji jako drugi element.</span><span class="sxs-lookup"><span data-stu-id="b0dab-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="b0dab-165">Nowa operacja obsługuje `Controlled` i będzie obsługiwać funkcję `Adjoint` if i tylko wtedy, gdy oryginalna operacja zakończyła się.</span><span class="sxs-lookup"><span data-stu-id="b0dab-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="b0dab-166">Jeśli oryginalna Operacja trwała tylko z pojedynczym argumentem, w tym miejscu będzie można odtwarzać [pojedynczej równoważności krotek](xref:microsoft.quantum.guide.types) .</span><span class="sxs-lookup"><span data-stu-id="b0dab-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="b0dab-167">Na przykład `Controlled X` jest kontrolowana wersja `X` operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="b0dab-168">`X` ma typ `(Qubit => Unit is Adj + Ctl)` , więc `Controlled X` ma typ `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; ze względu na równoważność spójnej kolekcji, jest to taka sama jak `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="b0dab-169">Jeśli operacja podstawowa wymagała kilku argumentów, pamiętaj, aby ująć odpowiednie argumenty kontrolowanej wersji operacji w nawiasach, aby przekonwertować je na krotkę.</span><span class="sxs-lookup"><span data-stu-id="b0dab-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="b0dab-170">Na przykład `Controlled Rz` jest kontrolowana wersja `Rz` operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="b0dab-171">`Rz` ma typ `((Double, Qubit) => Unit is Adj + Ctl)` , więc `Controlled Rz` ma typ `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="b0dab-172">W rezultacie będzie `Controlled Rz(controls, (0.1, target))` to poprawne wywołanie `Controlled Rz` (należy zwrócić uwagę na nawiasy `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="b0dab-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="b0dab-173">Innym przykładem `CNOT(control, target)` może być implementacja `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="b0dab-174">Jeśli element docelowy powinien być kontrolowany przez dwie qubits kontroli (CCNOT), użyj `Controlled X([control1, control2], target)` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="b0dab-175">`Controlled`I `Adjoint` funktory się, więc nie ma różnicy między stosowaniem `Controlled Adjoint Op` lub `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="b0dab-176">Definiowanie kontrolowanych i sąsiadujących implementacji</span><span class="sxs-lookup"><span data-stu-id="b0dab-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="b0dab-177">W pierwszej deklaracji operacji w poprzednich przykładach operacje `BitFlip` i `DecodeSuperdense` zostały zdefiniowane z podpisami `(Qubit => Unit)` i `((Qubit, Qubit) => (Result, Result))` odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="b0dab-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="b0dab-178">Jak `DecodeSuperdense` obejmuje pomiary, nie jest operacją jednostkową i w związku z tym nie może istnieć żadne kontrolowane niesąsiadujące specjalizacje (odwołaj powiązane wymaganie, aby ta operacja zwracała `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="b0dab-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="b0dab-179">Jednak jak `BitFlip` po prostu wykonuje operację jednostkową <xref:Microsoft.Quantum.Intrinsic.X> , można ją zdefiniować przy użyciu obu specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-179">However, as `BitFlip` simply performs the unitary <xref:Microsoft.Quantum.Intrinsic.X> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="b0dab-180">W tej sekcji szczegółowo opisano, jak uwzględnić istnienie specjalizacji w Q# deklaracjach operacji, dzięki czemu mogą one być wywoływane w połączeniu z `Adjoint` lub `Controlled` funktory.</span><span class="sxs-lookup"><span data-stu-id="b0dab-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="b0dab-181">Aby uzyskać więcej informacji o niektórych sytuacjach, w których jest to prawidłowe lub nieprawidłowe, aby zadeklarować specjalizacje, zobacz [warunki dotyczące prawidłowej definiowania specjalizacji](#circumstances-for-validly-defining-specializations) w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="b0dab-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="b0dab-182">Charakterystyki operacji definiują rodzaje funktory, które można zastosować do zadeklarowanej operacji oraz jaki ma wpływ.</span><span class="sxs-lookup"><span data-stu-id="b0dab-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="b0dab-183">Istnienie tych specjalizacji może być zadeklarowane jako część podpisu operacji, w odniesieniu do adnotacji z charakterystyką operacji: `is Adj` , `is Ctl` lub `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="b0dab-184">Rzeczywista implementacja każdej specjalizacji może być *jawnie* lub *jawnie* zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="b0dab-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="b0dab-185">Niejawnie Określanie implementacji</span><span class="sxs-lookup"><span data-stu-id="b0dab-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="b0dab-186">W takim przypadku treść deklaracji operacji składa się wyłącznie z implementacji domyślnej.</span><span class="sxs-lookup"><span data-stu-id="b0dab-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="b0dab-187">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="b0dab-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="b0dab-188">W tym miejscu odpowiednia implementacja dla każdej takiej niejawnie zadeklarowanej specjalizacji jest automatycznie generowana przez kompilator, która ma zostać wykonana w przypadku `Adjoint` `Controlled` użycia lub funktory.</span><span class="sxs-lookup"><span data-stu-id="b0dab-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="b0dab-189">Dlatego wywołanie `Adjoint PrepareEntangledPair` spowodowałaby kompilator implementujący sąsiadujące, `CNOT` a następnie sąsiadująco `H` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="b0dab-190">Te poszczególne operacje są samodzielne, więc wynikiem `Adjoint PrepareEntangledPair` operacji będzie po prostu zastosowanie, `CNOT(here, there)` a następnie `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="b0dab-191">W związku z tym możesz użyć tego polecenia `DecodeSuperdense` , aby napisać w poprzednim przykładzie bardziej kompaktowo, przy użyciu sąsiadująco w `PrepareEntangledPair` celu przekształcenia stanu Entangled z powrotem do pary unentangled qubits:</span><span class="sxs-lookup"><span data-stu-id="b0dab-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="b0dab-192">Adnotacja z charakterystyką operacji w deklaracji jest przydatna, aby zapewnić, że kompilator automatycznie generuje inne specjalizacje na podstawie domyślnej implementacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="b0dab-193">Istnieje kilka istotnych ograniczeń, które należy wziąć pod uwagę podczas projektowania operacji do użycia z funktory.</span><span class="sxs-lookup"><span data-stu-id="b0dab-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="b0dab-194">W przypadku niekrytycznej specjalizacji dla operacji korzystającej z wartości wyjściowej żadnej innej operacji *nie może* być automatycznie generowana przez kompilator, ponieważ jest niejednoznaczna w przypadku zmiany kolejności instrukcji w takiej operacji w celu uzyskania tego samego efektu.</span><span class="sxs-lookup"><span data-stu-id="b0dab-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="b0dab-195">W związku z tym często warto jawnie określić różne implementacje.</span><span class="sxs-lookup"><span data-stu-id="b0dab-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="b0dab-196">Jawne określanie implementacji</span><span class="sxs-lookup"><span data-stu-id="b0dab-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="b0dab-197">W przypadku, gdy kompilator nie może wygenerować implementacji, można określić ją jawnie.</span><span class="sxs-lookup"><span data-stu-id="b0dab-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="b0dab-198">Takie jawne deklaracje specjalizacji mogą składać się z odpowiedniej *dyrektywy generacji* lub implementacji zdefiniowanej przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b0dab-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="b0dab-199">Poniżej przedstawiono pełen zakres możliwości, z kilkoma przykładami jawnej specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="b0dab-200">Jawne deklaracje specjalizacji</span><span class="sxs-lookup"><span data-stu-id="b0dab-200">Explicit specialization declarations</span></span>

<span data-ttu-id="b0dab-201">Q# operacje mogą zawierać następujące jawne deklaracje specjalizacji:</span><span class="sxs-lookup"><span data-stu-id="b0dab-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="b0dab-202">`body`Specjalizacja określa implementację operacji bez zastosowanych funktory.</span><span class="sxs-lookup"><span data-stu-id="b0dab-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="b0dab-203">`adjoint`Specjalizacja określa implementację operacji z `Adjoint` zastosowaniem Funktor.</span><span class="sxs-lookup"><span data-stu-id="b0dab-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="b0dab-204">`controlled`Specjalizacja określa implementację operacji z `Controlled` zastosowaniem Funktor.</span><span class="sxs-lookup"><span data-stu-id="b0dab-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="b0dab-205">`controlled adjoint`Specjalizacja określa implementację operacji z `Adjoint` `Controlled` zastosowaniem zarówno i funktory.</span><span class="sxs-lookup"><span data-stu-id="b0dab-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="b0dab-206">Ta specjalizacja może być również nazywana `adjoint controlled` , ponieważ dwie funktory.</span><span class="sxs-lookup"><span data-stu-id="b0dab-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="b0dab-207">Specjalizacja operacji składa się z tagu specjalizacji (na przykład `body` lub `adjoint` ), po którym następuje jedna z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="b0dab-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="b0dab-208">Jawna deklaracja zgodnie z opisem w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="b0dab-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="b0dab-209">*Dyrektywa* , która informuje kompilator, *jak* generować specjalizację, jeden z:</span><span class="sxs-lookup"><span data-stu-id="b0dab-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="b0dab-210">`intrinsic`, co oznacza, że komputer docelowy udostępnia specjalizację.</span><span class="sxs-lookup"><span data-stu-id="b0dab-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="b0dab-211">`distribute`, używany z `controlled` `controlled adjoint` specjalizacjami i.</span><span class="sxs-lookup"><span data-stu-id="b0dab-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="b0dab-212">Gdy jest używany z `controlled` , wskazuje, że kompilator powinien obliczyć specjalizację, stosując `Controlled` do wszystkich operacji w `body` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="b0dab-213">Gdy jest używany z `controlled adjoint` , wskazuje, że kompilator powinien obliczyć specjalizację przez zastosowanie `Controlled` do wszystkich operacji w `adjoint` specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="b0dab-214">`invert`, co oznacza, że kompilator powinien obliczyć `adjoint` specjalizację, odwracając `body` , na przykład, odwracając kolejność operacji i stosując sąsiednie do każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="b0dab-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="b0dab-215">Gdy jest używany z `adjoint controlled` , oznacza to, że kompilator powinien obliczyć specjalizację, odwracając `controlled` specjalizację.</span><span class="sxs-lookup"><span data-stu-id="b0dab-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="b0dab-216">`self`, aby wskazać, że podległych specjalizacji jest taka sama jak `body` specjalizacja.</span><span class="sxs-lookup"><span data-stu-id="b0dab-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="b0dab-217">Korzystanie `self` z programu jest dozwolone `adjoint` dla `adjoint controlled` specjalizacji i.</span><span class="sxs-lookup"><span data-stu-id="b0dab-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="b0dab-218">W przypadku programu `adjoint controlled` `self` oznacza, że `adjoint controlled` specjalizacja jest taka sama jak `controlled` specjalizacja.</span><span class="sxs-lookup"><span data-stu-id="b0dab-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="b0dab-219">`auto`, aby wskazać, że kompilator powinien wybrać odpowiednią dyrektywę, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="b0dab-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="b0dab-220">Nie można użyć `auto` dla `body` specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="b0dab-221">Dyrektywy i `auto` wszystkie wymagają zamykającego średnika `;` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="b0dab-222">`auto`Dyrektywa jest rozpoznawana jako następująca wygenerowana dyrektywa, jeśli określono jawną deklarację `body` :</span><span class="sxs-lookup"><span data-stu-id="b0dab-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="b0dab-223">`adjoint`Specjalizacja generuje zgodnie z dyrektywą `invert` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="b0dab-224">`controlled`Specjalizacja generuje zgodnie z dyrektywą `distribute` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="b0dab-225">`adjoint controlled`Specjalizacja generuje zgodnie z dyrektywą, `invert` Jeśli jawna Deklaracja dla `controlled` jest podano, ale nie dla `adjoint` , i `distribute` w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="b0dab-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="b0dab-226">Jeśli operacja jest samodzielna, należy jawnie określić sąsiadujące lub kontrolowane specjalizację za pomocą dyrektywy generacji, `self` Aby umożliwić kompilatorowi użycie tych informacji do celów optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="b0dab-227">Deklaracja specjalizacji zawierająca implementację zdefiniowaną przez użytkownika składa się z krotki argumentu, po której następuje blok instrukcji z Q# kodem, który implementuje specjalizację.</span><span class="sxs-lookup"><span data-stu-id="b0dab-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="b0dab-228">Na liście argumentów `...` służy do reprezentowania argumentów zadeklarowanych dla operacji jako całości.</span><span class="sxs-lookup"><span data-stu-id="b0dab-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="b0dab-229">Dla `body` i `adjoint` , lista argumentów powinna być zawsze `(...)` ; dla `controlled` i `adjoint controlled` , lista argumentów powinna być symbolem, który reprezentuje tablicę kontrolki qubits, a następnie `...` ujętą w nawiasy; na przykład `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="b0dab-230">Przykłady</span><span class="sxs-lookup"><span data-stu-id="b0dab-230">Examples</span></span>

<span data-ttu-id="b0dab-231">Deklaracja operacji może być prosta jako następująca, która definiuje pierwotną operację Pauli X:</span><span class="sxs-lookup"><span data-stu-id="b0dab-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="b0dab-232">Należy zauważyć, że sąsiadująca operacja Pauli X została zdefiniowana z dyrektywą, `self` ponieważ według definicji `X` jest jej własnymi oddziałami.</span><span class="sxs-lookup"><span data-stu-id="b0dab-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="b0dab-233">W poprzednim `PrepareEntangledPair` przykładzie kod jest równoważny z poniższym kodem zawierającym jawne deklaracje specjalizacji:</span><span class="sxs-lookup"><span data-stu-id="b0dab-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="b0dab-234">Słowo kluczowe `auto` wskazuje, że kompilator powinien określić sposób generowania implementacji specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="b0dab-235">Implementacja specjalizacji zdefiniowanej przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="b0dab-235">User-defined specialization implementation</span></span>

<span data-ttu-id="b0dab-236">Jeśli kompilator nie może automatycznie wygenerować implementacji dla konkretnej specjalizacji lub można określić bardziej wydajną implementację, można ręcznie zdefiniować implementację.</span><span class="sxs-lookup"><span data-stu-id="b0dab-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

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
<span data-ttu-id="b0dab-237">W poprzednim przykładzie oznacza to, `adjoint invert;` że jest generowana podległych specjalizacji przez odwrócenie implementacji treści i `controlled adjoint invert;` wskazuje, że kontrolowana specjalizacja jest generowana przez odwrócenie danej implementacji kontrolowanej specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="b0dab-238">Jeśli co najmniej jedna specjalizacja poza treścią domyślną musi być zadeklarowana w sposób jawny, implementacja treści domyślnej musi być opakowana do odpowiedniej deklaracji specjalizacji:</span><span class="sxs-lookup"><span data-stu-id="b0dab-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="b0dab-239">Warunki dotyczące prawidłowej definiowania specjalizacji</span><span class="sxs-lookup"><span data-stu-id="b0dab-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="b0dab-240">Deklaracje operacji z sąsiadującymi/kontrolowanymi</span><span class="sxs-lookup"><span data-stu-id="b0dab-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="b0dab-241">Istnieje możliwość określenia operacji bez wersji sąsiednich lub kontrolowanych.</span><span class="sxs-lookup"><span data-stu-id="b0dab-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="b0dab-242">Na przykład operacje pomiarów nie mają żadnego elementu, ponieważ nie są odwracalna ani nie są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="b0dab-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="b0dab-243">Operacja obsługuje `Adjoint` i funktory, `Controlled` Jeśli jej deklaracja zawiera niejawną lub jawną deklarację odpowiednich specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="b0dab-244">Jawne zadeklarowane, sąsiadujące/kontrolowane specjalizacje implikuje istnienie podległych/kontrolowanej specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="b0dab-245">Dla operacji, której treść zawiera pętle REPEAT-until-Success, Set instrukcje, pomiary, instrukcje Return lub wywołania do innych operacji, które nie obsługują `Adjoint` Funktor, nie jest możliwe wygenerowanie przyległych specjalizacji po `invert` dyrektywie lub `auto` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="b0dab-246">Dla operacji, której treść zawiera wywołania do innych operacji, które nie obsługują `Controlled` Funktor, nie jest możliwe wygenerowanie kontrolowanej specjalizacji po `distribute` `auto` dyrektywie lub.</span><span class="sxs-lookup"><span data-stu-id="b0dab-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="b0dab-247">Kontrolowane sąsiadująco</span><span class="sxs-lookup"><span data-stu-id="b0dab-247">Controlled Adjoint</span></span>

<span data-ttu-id="b0dab-248">Sterowana sąsiadująco wersja operacji określa sposób implementacji kontrolowanej przez Quantum wersji podległych operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="b0dab-249">Istnieje możliwość określenia operacji bez kontrolowanej wersji sąsiadującej; na przykład operacje pomiarów nie mają kontrolowanej wersji sąsiadującej, ponieważ nie są ani odwracalnae ani nie są dostępne.</span><span class="sxs-lookup"><span data-stu-id="b0dab-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="b0dab-250">Kontrolowana podległych specjalizacji dla operacji musi istnieć, jeśli i tylko wtedy, gdy istnieje zarówno przyległych, jak i kontrolowanych specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="b0dab-251">W takim przypadku istnieje wywnioskowane istnienie kontrolowanej specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="b0dab-252">Jeśli żadna implementacja nie jest jawnie zdefiniowana, kompilacja generuje odpowiednią specjalizację.</span><span class="sxs-lookup"><span data-stu-id="b0dab-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="b0dab-253">W przypadku operacji, której treść zawiera wywołania do innych operacji, które nie mają kontrolowanej sąsiedniej wersji, funkcja nie jest możliwa do wygenerowania podległych specjalizacji zgodnie z `invert` , `distribute` lub `auto` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="b0dab-254">Zgodność typów</span><span class="sxs-lookup"><span data-stu-id="b0dab-254">Type Compatibility</span></span>

<span data-ttu-id="b0dab-255">Użyj operacji z dodatkowymi funktoryami obsługiwanymi wszędzie tam, gdzie używasz operacji z mniejszą liczbą funktory, ale z tą samą sygnaturą.</span><span class="sxs-lookup"><span data-stu-id="b0dab-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="b0dab-256">Na przykład użyj operacji typu w `(Qubit => Unit is Adj)` dowolnym miejscu, w którym używasz operacji typu `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="b0dab-257">Q# jest *współwariantem* w odniesieniu do możliwego do zwrócenia typu zwracanego: wywoływany, który zwraca typ jest zgodny z wywoływanym `'A` z tym samym typem danych wejściowych i typem wyniku, który jest zgodny z `'A` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="b0dab-258">Q# jest *kontrawariantne* w odniesieniu do typów danych wejściowych: wywoływanie, który przyjmuje typ `'A` jako dane wejściowe jest zgodny z wywoływanym z tym samym typem wynikowym i typem danych wejściowych zgodnym z `'A` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="b0dab-259">Oznacza to, że podano następujące definicje:</span><span class="sxs-lookup"><span data-stu-id="b0dab-259">That is, given the following definitions,</span></span>

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

<span data-ttu-id="b0dab-260">Można</span><span class="sxs-lookup"><span data-stu-id="b0dab-260">you can</span></span>

- <span data-ttu-id="b0dab-261">Wywołaj funkcję `ConjugateInvertWith` z `inner` argumentem `Invert` lub `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="b0dab-262">Wywołaj funkcję `ConjugateUnitaryWith` z `inner` argumentem `ApplyUnitary` , ale nie `Invert` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="b0dab-263">Zwraca wartość typu `(Qubit[] => Unit is Adj + Ctl)` z `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0dab-264">Q# 0,3 wprowadza znaczną różnicę w zachowaniu typów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b0dab-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="b0dab-265">Typy zdefiniowane przez użytkownika są traktowane jako opakowana wersja typu podstawowego, a nie jako podtyp.</span><span class="sxs-lookup"><span data-stu-id="b0dab-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="b0dab-266">Oznacza to, że wartość typu zdefiniowanego przez użytkownika nie może być użyteczna w przypadku, gdy oczekiwano wartości typu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="b0dab-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="b0dab-267">Definiowanie nowych funkcji</span><span class="sxs-lookup"><span data-stu-id="b0dab-267">Defining New Functions</span></span>

<span data-ttu-id="b0dab-268">Funkcje są czysto deterministyczne, klasyczne procedury w Q# , które różnią się od operacji w tym, że nie mogą mieć żadnych efektów poza obliczaniem wartości wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="b0dab-268">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="b0dab-269">W szczególności funkcje nie mogą wywoływać operacji; Działaj na, alokuj lub zażycz qubits; Przykładowe liczby losowe; lub w inny sposób zależy od stanu poza wartością wejściową do funkcji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-269">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="b0dab-270">W związku z tym Q# funkcje są *czyste* , w tym, że zawsze mapują te same wartości wejściowe na te same wartości wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="b0dab-270">As a consequence, Q# functions are *pure* , in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="b0dab-271">Takie zachowanie umożliwia Q# kompilatorowi bezpieczne Zmienianie kolejności sposobu i czasu wywoływania funkcji podczas generowania specjalizacji operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-271">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="b0dab-272">Każdy Q# plik źródłowy może definiować dowolną liczbę funkcji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-272">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="b0dab-273">Nazwy funkcji muszą być unikatowe w obrębie przestrzeni nazw i nie mogą powodować konfliktu z nazwami operacji lub typów.</span><span class="sxs-lookup"><span data-stu-id="b0dab-273">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="b0dab-274">Definiowanie funkcji działa podobnie do definiowania operacji, z tą różnicą, że dla funkcji nie można definiować podległych lub kontrolowanych specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-274">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="b0dab-275">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b0dab-275">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="b0dab-276">lub</span><span class="sxs-lookup"><span data-stu-id="b0dab-276">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="b0dab-277">Klasyczna logika w funkcjach = = dobra</span><span class="sxs-lookup"><span data-stu-id="b0dab-277">Classical logic in functions == good</span></span>

<span data-ttu-id="b0dab-278">Za każdym razem, gdy jest to możliwe, warto napisać klasyczną logikę pod kątem funkcji, a nie operacji, dzięki czemu operacje mogą łatwo korzystać z niej.</span><span class="sxs-lookup"><span data-stu-id="b0dab-278">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="b0dab-279">Na przykład, jeśli wcześniej zapisałeś wcześniejszą `Square` deklarację jako *operację* , kompilator nie może zagwarantowania, że wywołanie go z tymi samymi danymi wejściowymi będzie spójnie generować te same dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="b0dab-279">For example, if you had written the earlier `Square` declaration as an *operation* , then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="b0dab-280">Aby podkreślić różnicę między funkcjami i operacjami, należy wziąć pod uwagę problem z próbkami klasycznymi losowych z poziomu Q# operacji:</span><span class="sxs-lookup"><span data-stu-id="b0dab-280">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="b0dab-281">Za każdym razem `U` , gdy jest wywoływana, ma inną akcję na `target` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-281">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="b0dab-282">W szczególności kompilator nie może zagwarantować, że jeśli dodasz `adjoint auto` deklarację specjalizacji do `U` , `U(target); Adjoint U(target);` działa jako tożsamość (to oznacza, że jako No-op).</span><span class="sxs-lookup"><span data-stu-id="b0dab-282">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="b0dab-283">To narusza definicję części sąsiedniej zdefiniowanej w [wektorach i macierzach](xref:microsoft.quantum.concepts.vectors), takich jak umożliwienie kompilatorowi automatyczne wygenerowanie sąsiadującej specjalizacji w operacji, w której wywołanie operacji <xref:Microsoft.Quantum.Math.RandomReal> spowodowałoby przerwanie gwarancji dostarczonych przez kompilator; <xref:Microsoft.Quantum.Math.RandomReal> jest operacją, dla której nie istnieje przyległych lub kontrolowana wersja.</span><span class="sxs-lookup"><span data-stu-id="b0dab-283">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:Microsoft.Quantum.Math.RandomReal> would break the guarantees provided by the compiler; <xref:Microsoft.Quantum.Math.RandomReal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="b0dab-284">Z drugiej strony, zezwolenie na wywołania funkcji, takie jak `Square` jest bezpieczne, i gwarantuje, że kompilator musi tylko zachować dane wejściowe, aby `Square` zachować stabilny wynik.</span><span class="sxs-lookup"><span data-stu-id="b0dab-284">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="b0dab-285">W ten sposób izolowanie możliwie największej logiki w ramach funkcji pozwala łatwo ponownie wykorzystać tę logikę w innych funkcjach i operacjach.</span><span class="sxs-lookup"><span data-stu-id="b0dab-285">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="b0dab-286">Typy ogólne (sparametryzowane od typu)</span><span class="sxs-lookup"><span data-stu-id="b0dab-286">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="b0dab-287">Wiele funkcji i operacji, które można zdefiniować, nie jest w rzeczywistości zależne od typów danych wejściowych, ale raczej niejawnie Używaj ich typów za pośrednictwem innej funkcji lub operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-287">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="b0dab-288">Rozważmy na przykład, że koncepcja *mapy* jest wspólna dla wielu języków funkcjonalnych; dana funkcja $f (x) $ i Kolekcja wartości $ \{ x_1, x_2, \dots, x_n \} $, map zwraca nową kolekcję $ \{ f (x_1), f (x_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="b0dab-288">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="b0dab-289">W celu zaimplementowania tego programu w programie Q# należy skorzystać z faktu, że funkcje są pierwszej klasy.</span><span class="sxs-lookup"><span data-stu-id="b0dab-289">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="b0dab-290">Oto szybki przykład `Map` użycia `T` jako symbol zastępczy podczas ustalania potrzebnych typów.</span><span class="sxs-lookup"><span data-stu-id="b0dab-290">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="b0dab-291">Należy zauważyć, że ta funkcja wygląda bardzo podobnie niezależnie od tego, jakie typy rzeczywiste zostały zastąpione.</span><span class="sxs-lookup"><span data-stu-id="b0dab-291">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="b0dab-292">Mapa z liczb całkowitych na Paul, na przykład, wygląda podobnie jak mapa od liczb zmiennoprzecinkowych do ciągów:</span><span class="sxs-lookup"><span data-stu-id="b0dab-292">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="b0dab-293">W zasadzie można napisać wersję programu `Map` dla każdej pary typów, które napotykasz, ale wprowadzamy kilka trudności.</span><span class="sxs-lookup"><span data-stu-id="b0dab-293">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="b0dab-294">Na przykład jeśli znajdziesz usterkę w programie `Map` , należy upewnić się, że poprawka jest stosowana jednolicie we wszystkich wersjach programu `Map` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-294">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="b0dab-295">Ponadto w przypadku konstruowania nowej spójnej kolekcji lub UDT, należy również utworzyć nową, `Map` Aby przejść do nowego typu.</span><span class="sxs-lookup"><span data-stu-id="b0dab-295">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="b0dab-296">Chociaż jest to możliwe w przypadku niewielkiej liczby takich funkcji, podczas zbierania większej i większej liczby funkcji tego samego formularza co `Map` koszt wprowadzenia nowych typów stanie się nieuzasadniony w dość krótkim porządku.</span><span class="sxs-lookup"><span data-stu-id="b0dab-296">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="b0dab-297">Jednak większość tego rodzaju trudności wynika z faktu, że nie podano w kompilatorze informacji, które muszą rozpoznać, w jaki sposób `Map` są powiązane różne wersje.</span><span class="sxs-lookup"><span data-stu-id="b0dab-297">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="b0dab-298">Efektywnie, chcesz, aby kompilator traktował `Map` jako rodzaj funkcji matematycznej z Q# *typów* do Q# funkcji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-298">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="b0dab-299">Q# formalizes to pojęcie przez umożliwienie funkcjom i operacjom posiadania *parametrów typu* , a także ich zwykłych parametrów krotek.</span><span class="sxs-lookup"><span data-stu-id="b0dab-299">Q# formalizes this notion by allowing functions and operations to have *type parameters* , as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="b0dab-300">W poprzednich przykładach, chcesz traktować `Map` jako parametry typu `Int, Pauli` w pierwszym przypadku i `Double, String` w drugim przypadku.</span><span class="sxs-lookup"><span data-stu-id="b0dab-300">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="b0dab-301">W większości przypadków Użyj tych parametrów typu, tak jakby były to typy zwykłe.</span><span class="sxs-lookup"><span data-stu-id="b0dab-301">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="b0dab-302">Używaj wartości parametrów typu do wprowadzania tablic i krotek, wywoływania funkcji i operacji oraz przypisywania do zmiennych normalnych lub modyfikowalnych.</span><span class="sxs-lookup"><span data-stu-id="b0dab-302">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="b0dab-303">Największą sytuacją pośrednią jest to, że qubits, w którym Q# program nie może bezpośrednio polegać na strukturze `Qubit` typu, ale **musi** przekazać takie typy do innych operacji i funkcji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-303">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="b0dab-304">Powracanie do wcześniejszego przykładu, zobaczysz, że `Map` musi mieć parametry typu, jeden do reprezentowania danych wejściowych `fn` i jeden do reprezentowania danych wyjściowych `fn` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-304">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="b0dab-305">W programie Q# jest to zapisywana przez dodanie nawiasów kątowych ( `<>` nie brakets $ \braket {} $!) po nazwie funkcji lub operacji w jej deklaracji oraz przez wystawienie poszczególnych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="b0dab-305">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="b0dab-306">Nazwa każdego parametru typu musi rozpoczynać się od osi `'` , wskazując, że jest parametrem typu, a nie zwykłym typem (znanym także jako *konkretny* typ).</span><span class="sxs-lookup"><span data-stu-id="b0dab-306">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="b0dab-307">W tym przypadku `Map` :</span><span class="sxs-lookup"><span data-stu-id="b0dab-307">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="b0dab-308">Należy zauważyć, że definicja `Map<'Input, 'Output>` wygląda bardzo podobna do wersji previoius.</span><span class="sxs-lookup"><span data-stu-id="b0dab-308">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="b0dab-309">Jedyną różnicą jest to, że użytkownik jawnie poinformowany o kompilatorze, który `Map` nie zależy bezpośrednio od tego `'Input` `'Output` , co jest `fn`</span><span class="sxs-lookup"><span data-stu-id="b0dab-309">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="b0dab-310">Po zdefiniowaniu `Map<'Input, 'Output>` w ten sposób można wywołać tę funkcję, tak jakby była to funkcja zwykła:</span><span class="sxs-lookup"><span data-stu-id="b0dab-310">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="b0dab-311">Pisanie funkcji ogólnych i operacji to jedno miejsce, w którym "Krotka w kolekcji" jest bardzo przydatna, aby myśleć o Q# funkcjach i operacjach.</span><span class="sxs-lookup"><span data-stu-id="b0dab-311">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="b0dab-312">Ponieważ każda funkcja przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście, dane wejściowe typu `'T -> 'U` dopasowują *dowolną* Q# funkcję.</span><span class="sxs-lookup"><span data-stu-id="b0dab-312">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="b0dab-313">Podobnie można przekazać dowolną operację do danych wejściowych typu `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-313">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="b0dab-314">W drugim przykładzie należy wziąć pod uwagę wyzwanie napisania funkcji, która zwraca skład dwóch innych funkcji:</span><span class="sxs-lookup"><span data-stu-id="b0dab-314">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="b0dab-315">W tym miejscu należy określić dokładnie to `A` , co `B` i co `C` to jest, a tym samym znacznie ograniczyć narzędzie do nowej `Compose` funkcji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-315">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="b0dab-316">Po wszystko jest `Compose` zależne od `A` , `B` i `C` *przez* `innerFn` i `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="b0dab-316">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="b0dab-317">Alternatywnie, można dodać parametry typu do `Compose` , które wskazują, że działa dla *dowolnego* `A` , `B` i `C` , tak długo, jak te parametry są zgodne z oczekiwanymi przez `innerFn` i `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="b0dab-317">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="b0dab-318">Q#Biblioteki standardowe zapewniają wiele takich operacji i funkcji sparametryzowanych typu, aby ułatwić przepływ kontroli wyższej kolejności.</span><span class="sxs-lookup"><span data-stu-id="b0dab-318">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="b0dab-319">Są one omówione bardziej szczegółowo w [ Q# przewodniku po bibliotece standardowej](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="b0dab-319">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="b0dab-320">Możliwy do przeFirst-Class wartości</span><span class="sxs-lookup"><span data-stu-id="b0dab-320">Callables as First-Class Values</span></span>

<span data-ttu-id="b0dab-321">Jedną z kluczowych technik z przyczyn dotyczących przepływu sterowania i klasycznej logiki przy użyciu funkcji, a nie operacji, jest korzystanie z tych operacji i funkcji w programie, które Q# są *pierwszej klasy* .</span><span class="sxs-lookup"><span data-stu-id="b0dab-321">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class* .</span></span>
<span data-ttu-id="b0dab-322">Oznacza to, że są to poszczególne wartości w języku we własnym zakresie.</span><span class="sxs-lookup"><span data-stu-id="b0dab-322">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="b0dab-323">Na przykład, poniżej jest doskonale prawidłowy Q# kod, w przypadku niewielkiego pośrednika:</span><span class="sxs-lookup"><span data-stu-id="b0dab-323">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="b0dab-324">Wartość zmiennej `ourH` w poprzednim fragmencie kodu jest następnie operacją <xref:Microsoft.Quantum.Intrinsic.H> , która umożliwia wywoływanie tej wartości podobnie jak każda inna operacja.</span><span class="sxs-lookup"><span data-stu-id="b0dab-324">The value of the variable `ourH` in the previous snippet is then the operation <xref:Microsoft.Quantum.Intrinsic.H>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="b0dab-325">Dzięki tej możliwości można pisać operacje, które przyjmują operacje w ramach danych wejściowych, tworząc koncepcje przepływu sterowania wyższego rzędu.</span><span class="sxs-lookup"><span data-stu-id="b0dab-325">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="b0dab-326">Na przykład można wyobrazić się do operacji "kwadratowych", stosując ją dwa razy do tego samego elementu docelowego qubit.</span><span class="sxs-lookup"><span data-stu-id="b0dab-326">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="b0dab-327">Zwracanie operacji z funkcji</span><span class="sxs-lookup"><span data-stu-id="b0dab-327">Returning operations from a function</span></span>

<span data-ttu-id="b0dab-328">Ważne jest, aby podkreślić, że można również zwracać operacje w ramach danych wyjściowych, takich jak możliwość izolowania pewnego rodzaju klasycznej logiki warunkowej jako funkcji klasycznej, która zwraca opis programu Quantum w postaci operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-328">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="b0dab-329">W ramach prostego przykładu Rozważmy przykład teleportowego, w którym strona otrzymująca dwubitowy klasyczny komunikat musi użyć komunikatu, aby zdekodować qubit w odpowiedni stan teleportowy.</span><span class="sxs-lookup"><span data-stu-id="b0dab-329">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="b0dab-330">Można napisać to pod względem funkcji, która pobiera te dwa klasyczne bity i zwraca odpowiednią operację dekodowania.</span><span class="sxs-lookup"><span data-stu-id="b0dab-330">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="b0dab-331">Ta nowa funkcja jest w rzeczywistości funkcją, w tym przypadku, gdy wywołuje ją z tymi samymi wartościami `hereBit` i `thereBit` , zawsze jest przywracana ta sama operacja.</span><span class="sxs-lookup"><span data-stu-id="b0dab-331">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="b0dab-332">W związku z tym dekoder może być bezpiecznie uruchamiany wewnątrz operacji bez powodowania, jak logika dekodowania współdziała z definicjami różnych specjalizacji operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-332">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="b0dab-333">Oznacza to, że klasyczna logika wewnątrz funkcji jest izolowana, co gwarantuje kompilatorowi możliwość zmiany kolejności wywołania funkcji z impunity tak długo, jak dane wejściowe są zachowywane.</span><span class="sxs-lookup"><span data-stu-id="b0dab-333">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="b0dab-334">Aplikacja częściowa</span><span class="sxs-lookup"><span data-stu-id="b0dab-334">Partial Application</span></span>

<span data-ttu-id="b0dab-335">Można wykonać znacznie więcej dzięki funkcjom, które zwracają operacje przy użyciu *częściowej aplikacji* , w którym można dostarczyć co najmniej jedną część danych wejściowych do funkcji lub operacji bez jej rzeczywistego wywoływania.</span><span class="sxs-lookup"><span data-stu-id="b0dab-335">You can do significantly more with functions that return operations by using *partial application* , in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="b0dab-336">W poprzednim `ApplyTwice` przykładzie można wskazać, że nie chcesz określać, od razu, do czego qubit powinna być stosowana operacja wejściowa:</span><span class="sxs-lookup"><span data-stu-id="b0dab-336">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="b0dab-337">W takim przypadku zmienna lokalna `twiceOp` zawiera częściowo zastosowana operacja `ApplyTwice(op, _)` , gdzie `_` wskazuje części danych wejściowych, które nie zostały jeszcze określone.</span><span class="sxs-lookup"><span data-stu-id="b0dab-337">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="b0dab-338">Po wywołaniu `twiceOp` w następnym wierszu zostanie przekazane jako dane wejściowe do operacji częściowo zastosowanej wszystkie pozostałe części danych wejściowych do oryginalnej operacji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-338">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="b0dab-339">W związku z tym poprzedni fragment kodu jest efektywnie identyczny, aby był wywoływany `ApplyTwice(op, target)` bezpośrednio, Zapisz, że wprowadzono nową zmienną lokalną, aby można było opóźnić połączenie, jednocześnie dostarczając niektóre części danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="b0dab-339">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="b0dab-340">Ponieważ operacja, która została częściowo zastosowana, nie jest faktycznie wywoływana do momentu podania całego danych wejściowych, można bezpiecznie zastosować częściowe operacje nawet z poziomu funkcji.</span><span class="sxs-lookup"><span data-stu-id="b0dab-340">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="b0dab-341">W zasadzie klasyczna logika w ramach `SquareOperation` mogły być znacznie inne, ale nadal jest odizolowana od reszty operacji przez gwarancje, które kompilator może zaoferować na informacje o funkcjach.</span><span class="sxs-lookup"><span data-stu-id="b0dab-341">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="b0dab-342">Q#Standardowa biblioteka używa tego podejścia w celu wyrażenia klasycznego przepływu sterowania w sposób, w jaki programy Quantum mogą łatwo używać.</span><span class="sxs-lookup"><span data-stu-id="b0dab-342">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="b0dab-343">Rekursja</span><span class="sxs-lookup"><span data-stu-id="b0dab-343">Recursion</span></span>

<span data-ttu-id="b0dab-344">Q# możliwe, że możliwe jest bezpośrednie lub pośrednie cykliczne.</span><span class="sxs-lookup"><span data-stu-id="b0dab-344">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="b0dab-345">Oznacza to, że operacja lub funkcja może wywołać się sama lub wywołać inne wywołanie, które bezpośrednio lub pośrednio wywołuje operację wywołującą.</span><span class="sxs-lookup"><span data-stu-id="b0dab-345">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="b0dab-346">Istnieją jednak dwa ważne komentarze dotyczące korzystania z rekursji:</span><span class="sxs-lookup"><span data-stu-id="b0dab-346">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="b0dab-347">Użycie rekursji w operacjach może zakłócać pewne optymalizacje.</span><span class="sxs-lookup"><span data-stu-id="b0dab-347">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="b0dab-348">Zakłócenia te mogą mieć znaczny wpływ na czas wykonywania algorytmu.</span><span class="sxs-lookup"><span data-stu-id="b0dab-348">This interference can have a substantial impact on the run time of the algorithm.</span></span>
- <span data-ttu-id="b0dab-349">W przypadku uruchamiania na rzeczywistym urządzeniu Quantum przestrzeń stosu może być ograniczona, a więc Szczegółowa rekursja może prowadzić do błędu czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b0dab-349">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="b0dab-350">W szczególności Q# kompilator i środowisko uruchomieniowe nie identyfikują i nie optymalizują rekursji końcowej.</span><span class="sxs-lookup"><span data-stu-id="b0dab-350">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b0dab-351">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="b0dab-351">Next steps</span></span>

<span data-ttu-id="b0dab-352">Dowiedz się więcej na temat [zmiennych](xref:microsoft.quantum.guide.variables) w Q# .</span><span class="sxs-lookup"><span data-stu-id="b0dab-352">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>
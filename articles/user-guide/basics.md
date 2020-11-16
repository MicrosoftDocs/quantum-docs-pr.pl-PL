---
title: 'Q# Nazwie'
description: 'Podstawowe pojęcia związane z Q#'
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: b3bc0841eabeac5d3968776f9dab3a02b1a1eef9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691633"
---
# <a name="no-locq-basics"></a><span data-ttu-id="1fb17-103">Q# Nazwie</span><span class="sxs-lookup"><span data-stu-id="1fb17-103">Q# Basics</span></span>

<span data-ttu-id="1fb17-104">W tym artykule przedstawiono krótkie wprowadzenie do podstawowych bloków konstrukcyjnych Q# .</span><span class="sxs-lookup"><span data-stu-id="1fb17-104">This article presents a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="1fb17-105">Aby Q# dowiedzieć się, co to jest i gdzie mieści się w ramach podstawowego składnika zestawu Quantum Development Kit, zobacz [co to jest Q# ?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="1fb17-105">For an overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, see [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="1fb17-106">Co to jest program Quantum?</span><span class="sxs-lookup"><span data-stu-id="1fb17-106">What is a quantum program?</span></span>

<span data-ttu-id="1fb17-107">Z perspektywy technicznej, program Quantum jest określonym zestawem klasycznych podprocedur, które po wywołaniu należy wykonać pewne operacje w systemie Quantum.</span><span class="sxs-lookup"><span data-stu-id="1fb17-107">From a technical perspective, a quantum program is a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="1fb17-108">Istotną konsekwencją tego widoku jest to, że Q# program nie jest bezpośrednio modelem qubits, ale raczej opisuje, w jaki sposób klasyczny komputer współdziała z tymi qubitsami.</span><span class="sxs-lookup"><span data-stu-id="1fb17-108">An important consequence of that view is that a Q# program does not directly model qubits themselves, but rather describes how a classically controlled computer interacts with those qubits.</span></span>
<span data-ttu-id="1fb17-109">Zgodnie z projektem, nie Q# definiuje bezpośrednio Stanów Quantum ani innych właściwości Mechanics Quantum.</span><span class="sxs-lookup"><span data-stu-id="1fb17-109">By design, Q# does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="1fb17-110">Na przykład rozważmy stan $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ omówiony w przewodniku [koncepcji obliczeniowej usługi Quantum](xref:microsoft.quantum.concepts.intro) .</span><span class="sxs-lookup"><span data-stu-id="1fb17-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="1fb17-111">Aby przygotować ten stan w programie Q# , Zacznij od faktów, że qubits są inicjowane w stanie $ \ket {0} $ i że $ \ket{+} = H\ket {0} $, gdzie $H $ to [Hadamard Transform](xref:microsoft.quantum.glossary#hadamard), zaimplementowany przez [ `H` operację](xref:Microsoft.Quantum.Intrinsic.H).</span><span class="sxs-lookup"><span data-stu-id="1fb17-111">To prepare this state in Q#, start with the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the [Hadamard transform](xref:microsoft.quantum.glossary#hadamard), implemented by the [`H` operation](xref:Microsoft.Quantum.Intrinsic.H).</span></span> <span data-ttu-id="1fb17-112">Kod podstawowy Q# do zainicjowania i przekształcenia qubit jest następujący:</span><span class="sxs-lookup"><span data-stu-id="1fb17-112">The basic Q# code to initialize and transform a qubit, then, looks like this:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
<span data-ttu-id="1fb17-113">Aby uzyskać więcej informacji na temat inicjowania lub *alokowania* qubits, zobacz [Praca z qubits](xref:microsoft.quantum.guide.qubits).</span><span class="sxs-lookup"><span data-stu-id="1fb17-113">For more information on initializing, or *allocating* , qubits, see [Working with qubits](xref:microsoft.quantum.guide.qubits).</span></span>

## <a name="quantum-states-in-no-locq"></a><span data-ttu-id="1fb17-114">Stany Quantum w Q#</span><span class="sxs-lookup"><span data-stu-id="1fb17-114">Quantum states in Q#</span></span>

<span data-ttu-id="1fb17-115">Z tego powodu poprzedni program nie odwołuje się jawnie do stanu w ramach Q# programu, ale opisano, w jaki sposób ten program *przekształca* stan.</span><span class="sxs-lookup"><span data-stu-id="1fb17-115">Importantly, the previous program does not explicitly refer to the state within Q# but described how our program *transformed* the state.</span></span>
<span data-ttu-id="1fb17-116">Korzystając z tej metody, można całkowicie niezależny od na temat tego, co stan Quantum *jest* nawet na każdej maszynie docelowej, co może mieć różne interpretacje w zależności od maszyny.</span><span class="sxs-lookup"><span data-stu-id="1fb17-116">With this approach, you can be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="1fb17-117">Q#Program nie może Introspect stanu qubit.</span><span class="sxs-lookup"><span data-stu-id="1fb17-117">A Q# program cannot introspect into the state of a qubit.</span></span>
<span data-ttu-id="1fb17-118">Zamiast tego program może wywoływać operacje, takie jak [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) Aby poznać informacje z qubit i wywoływać operacje, takie jak [`X`](xref:Microsoft.Quantum.Intrinsic.X) i [`H`](xref:Microsoft.Quantum.Intrinsic.H) do działania na stanie qubit.</span><span class="sxs-lookup"><span data-stu-id="1fb17-118">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to learn information from a qubit, and call operations such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) to act on the state of a qubit.</span></span>
<span data-ttu-id="1fb17-119">Te *operacje są wykonywane* tylko w konkretnym miejscu przez maszynę docelową używaną do uruchamiania określonego Q# programu.</span><span class="sxs-lookup"><span data-stu-id="1fb17-119">What these operations actually *do* is only made concrete by the target machine used to run the particular Q# program.</span></span>
<span data-ttu-id="1fb17-120">Na przykład, jeśli uruchamiasz program w [symulatorze pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator), symulator wykonuje odpowiednie operacje matematyczne w symulowanym systemie Quantum.</span><span class="sxs-lookup"><span data-stu-id="1fb17-120">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="1fb17-121">Jednak w przyszłości, gdy maszyna docelowa jest rzeczywistym komputerem z systemem Quantum, wywołanie takich operacji powoduje Q# kierowanie komputera Quantum do wykonywania odpowiednich *rzeczywistych* operacji na *rzeczywistym* systemie Quantum, na przykład precyzyjne impulsy laserowe.</span><span class="sxs-lookup"><span data-stu-id="1fb17-121">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# directs the quantum computer to perform the corresponding *real* operations on the *real* quantum system, for example, precisely timed laser pulses).</span></span>

<span data-ttu-id="1fb17-122">Q#Program ponownie łączy te operacje w sposób zdefiniowany przez maszynę docelową w celu utworzenia nowych, wyższych operacji do wyrażenia Quantum obliczeń.</span><span class="sxs-lookup"><span data-stu-id="1fb17-122">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="1fb17-123">W ten sposób można Q# łatwo wyrażać logikę podstawowych algorytmów Quantum i hybrydowe, a także ogólnie w odniesieniu do struktury maszyny docelowej lub symulatora.</span><span class="sxs-lookup"><span data-stu-id="1fb17-123">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="no-locq-operations-and-functions"></a><span data-ttu-id="1fb17-124">Q# operacje i funkcje</span><span class="sxs-lookup"><span data-stu-id="1fb17-124">Q# operations and functions</span></span>

<span data-ttu-id="1fb17-125">W konkretnym przypadku Q# program składa się z *operacji* , *funkcji* i wszystkich typów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1fb17-125">Concretely, a Q# program comprises *operations* , *functions* , and any user-defined types.</span></span> 

<span data-ttu-id="1fb17-126">Operacje są używane do opisywania transformacji systemów Quantum i są najbardziej podstawowymi blokami konstrukcyjnymi Q# programów.</span><span class="sxs-lookup"><span data-stu-id="1fb17-126">Operations are used to describe the transformations of quantum systems and are the most fundamental building block of Q# programs.</span></span> <span data-ttu-id="1fb17-127">Każda operacja zdefiniowana w programie Q# może następnie wywołać dowolną liczbę innych operacji.</span><span class="sxs-lookup"><span data-stu-id="1fb17-127">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="1fb17-128">W przeciwieństwie do operacji, funkcje są używane do opisywania przejrzystie *deterministycznych* zachowań klasycznych i nie mają żadnych efektów poza obliczaniem klasycznych wartości.</span><span class="sxs-lookup"><span data-stu-id="1fb17-128">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="1fb17-129">Załóżmy na przykład, że chcesz zmierzyć qubits na końcu programu i dodać wyniki pomiarów do tablicy.</span><span class="sxs-lookup"><span data-stu-id="1fb17-129">For example, suppose you want to measure the qubits at the end of a program and add the measurement results to an array.</span></span>
<span data-ttu-id="1fb17-130">W tym przypadku `Measure` jest *operacją* , która instruuje maszynę docelową, aby wykonywała pomiary w qubits (rzeczywista lub symulowana).</span><span class="sxs-lookup"><span data-stu-id="1fb17-130">In this case, `Measure` is an *operation* that instructs the target machine to perform a measurement on the (real or simulated) qubits.</span></span> <span data-ttu-id="1fb17-131">W tym samym czasie *Funkcja* obsługuje klasyczny proces dodawania zwracanych wyników do tablicy.</span><span class="sxs-lookup"><span data-stu-id="1fb17-131">At the same time, *functions* handle the classical process of adding the returned results to an array.</span></span>

<span data-ttu-id="1fb17-132">Razem operacje i funkcje są nazywane *możliwymi* do przełożenia.</span><span class="sxs-lookup"><span data-stu-id="1fb17-132">Together, operations and functions are known as *callables* .</span></span> <span data-ttu-id="1fb17-133">Ich podstawowa struktura i zachowanie są wprowadzane i szczegółowo opisane w temacie [operacje Q# i funkcje w ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="1fb17-133">Their underlying structure and behavior are introduced and detailed in [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>


## <a name="no-locq-syntax-overview"></a><span data-ttu-id="1fb17-134">Q# Omówienie składni</span><span class="sxs-lookup"><span data-stu-id="1fb17-134">Q# syntax overview</span></span>

<span data-ttu-id="1fb17-135">Składnia języka opisuje różne kombinacje symboli, które tworzą poprawny w składni program.</span><span class="sxs-lookup"><span data-stu-id="1fb17-135">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="1fb17-136">W programie Q# elementy składni są klasyfikowane do trzech różnych grup: typów, wyrażeń i instrukcji.</span><span class="sxs-lookup"><span data-stu-id="1fb17-136">In Q#, syntax elements are classified into three different groups: types, expressions, and statements.</span></span>

### <a name="types"></a><span data-ttu-id="1fb17-137">Typy</span><span class="sxs-lookup"><span data-stu-id="1fb17-137">Types</span></span>
<span data-ttu-id="1fb17-138">Q# jest językiem o jednoznacznie określonym typie, w taki sposób, że staranne użycie typów może pomóc kompilatorowi zapewnić mocne gwarancje dotyczące Q# programów w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="1fb17-138">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="1fb17-139">Oprócz standardowych i opartych na Quantum typów pierwotnych, na przykład,,, `Int` `Bool` `Qubit` i `Result` , Q# zapewnia obsługę typów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1fb17-139">In addition to standard and quantum-specific built-in primitive types, for example, `Int`, `Bool`, `Qubit`, and `Result`, Q# provides support for user-defined types.</span></span>

<span data-ttu-id="1fb17-140">Aby zapoznać się z opisami wszystkich typów pierwotnych, szczegóły dotyczące typów tablic i krotek oraz kroki definiowania nowych typów w Q# pliku, zobacz [typy w Q# ](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="1fb17-140">For descriptions of all the primitive types, details for array and tuple types, and steps to define new types within a Q# file, see [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

### <a name="expressions"></a><span data-ttu-id="1fb17-141">Wyrażenia</span><span class="sxs-lookup"><span data-stu-id="1fb17-141">Expressions</span></span>
<span data-ttu-id="1fb17-142">Wyrażenie w języku programowania jest kombinacją jednej lub więcej stałych, zmiennych, operatorów i funkcji interpretowanych przez język programowania i obliczanych w określonej wartości.</span><span class="sxs-lookup"><span data-stu-id="1fb17-142">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="1fb17-143">W przypadku każdego typu w języku wyrażenia tego typu mogą być *literałami* lub symbolami związanymi z wartością tego typu.</span><span class="sxs-lookup"><span data-stu-id="1fb17-143">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="1fb17-144">Na przykład, `5` to `Int` literał (również wyrażenie typu `Int` ) i jeśli symbol `count` jest powiązany z wartością całkowitą `5` , `count` jest również wyrażeniem liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="1fb17-144">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="1fb17-145">Ponadto wyrażenie może składać się z innych wyrażeń połączonych przez niektóre operatory.</span><span class="sxs-lookup"><span data-stu-id="1fb17-145">Additionally, an expression can consist of other expressions combined by certain operators.</span></span>
<span data-ttu-id="1fb17-146">Na przykład inne `Int` wyrażenie, którego wynikiem jest wartość `5` `2+3` .</span><span class="sxs-lookup"><span data-stu-id="1fb17-146">For example, another `Int` expression that evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="1fb17-147">Aby uzyskać więcej informacji na temat wyrażeń i zgodnych operatorów w Q# , zobacz [typu Expressions in Q# ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="1fb17-147">For more information about expressions and compatible operators in Q#, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span> 

### <a name="statements"></a><span data-ttu-id="1fb17-148">Instrukcje</span><span class="sxs-lookup"><span data-stu-id="1fb17-148">Statements</span></span> 
<span data-ttu-id="1fb17-149">Instrukcja jest jednostką składniową bezwzględnego języka programowania, która wyraża pewne działania do wykonania. Różnice instrukcji z wyrażeniami w tych instrukcjach nie zwracają wyników i są uruchamiane wyłącznie dla ich efektów ubocznych.</span><span class="sxs-lookup"><span data-stu-id="1fb17-149">A statement is a syntactic unit of an imperative programming language that expresses some action to carry out. Statements contrast with expressions in that statements do not return results and are run solely for their side effects.</span></span> <span data-ttu-id="1fb17-150">Wyrażenia, jednak zawsze zwracają wynik i często nie mają żadnych efektów ubocznych.</span><span class="sxs-lookup"><span data-stu-id="1fb17-150">Expressions, however, always return a result and often do not have any side effects.</span></span> <span data-ttu-id="1fb17-151">W krótkim Q# czasie są wykonywane instrukcje, podczas gdy wyrażenia są oceniane.</span><span class="sxs-lookup"><span data-stu-id="1fb17-151">In short, Q# statements are run, while expressions are evaluated.</span></span>

<span data-ttu-id="1fb17-152">Prosty przykład instrukcji w programie Q# przypisuje symbol do wyrażenia:</span><span class="sxs-lookup"><span data-stu-id="1fb17-152">A simple example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="1fb17-153">Bardziej interesujący przykład to `for` instrukcja, która obsługuje iterację i zawiera *blok instrukcji* .</span><span class="sxs-lookup"><span data-stu-id="1fb17-153">A more interesting example is the `for` statement which supports iteration and includes a *statement block* .</span></span>
<span data-ttu-id="1fb17-154">Załóżmy `qubits` , że symbol jest powiązany z rejestrem qubits (technicznie typu `Qubit[]` lub tablicy `Qubit` typów).</span><span class="sxs-lookup"><span data-stu-id="1fb17-154">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, or an array of `Qubit` types).</span></span> <span data-ttu-id="1fb17-155">Następnie</span><span class="sxs-lookup"><span data-stu-id="1fb17-155">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="1fb17-156">jest instrukcją, która wykonuje iterację na każdym qubit w rejestrze, wykonując `H` operację na każdej z nich.</span><span class="sxs-lookup"><span data-stu-id="1fb17-156">is a statement that iterates over each qubit in the register, performing the `H` operation on each one.</span></span> <span data-ttu-id="1fb17-157">Należy zauważyć, że `H(qubit);` jest również instrukcją w samej siebie.</span><span class="sxs-lookup"><span data-stu-id="1fb17-157">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="1fb17-158">Można użyć dowolnego wyrażenia wywołania typu `Unit` ( `Unit` Typ nie zwraca żadnych informacji) jako instrukcji.</span><span class="sxs-lookup"><span data-stu-id="1fb17-158">You can use any call expression of type `Unit` (a `Unit` type does not return any information) as a statement.</span></span>
<span data-ttu-id="1fb17-159">Ten typ wyrażenia jest przydatny podczas wywoływania operacji na qubits, które zwracają, `Unit` ponieważ celem instrukcji jest zmodyfikowanie niejawnego stanu Quantum.</span><span class="sxs-lookup"><span data-stu-id="1fb17-159">This type of expression is useful when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="1fb17-160">Instrukcje oceny wyrażeń wymagają zakończenia średnika.</span><span class="sxs-lookup"><span data-stu-id="1fb17-160">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="1fb17-161">Instrukcje służą do kompilowania niemal każdego aspektu Q# programu, a żadna pojedyncza strona nie może obejmować wszystkich informacji odnoszących się do nich.</span><span class="sxs-lookup"><span data-stu-id="1fb17-161">You use statements to build nearly every aspect of a Q# program, and no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="1fb17-162">Aby uzyskać więcej informacji na temat ich struktury i formatowania leksykalnego, zobacz [ Q# Struktura pliku](xref:microsoft.quantum.guide.filestructure); w przypadku przypisywania i zakresu powiązań symboli, patrz [zmienne w Q# ](xref:microsoft.quantum.guide.variables); i w przypadku pętli przepływu sterowania, takich jak `for` , zobacz [Flow Control in Q# ](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="1fb17-162">For more information about their lexical structure and formatting, see [Q# File Structure](xref:microsoft.quantum.guide.filestructure); for symbol binding assignment and scope, see [Variables in Q#](xref:microsoft.quantum.guide.variables); and for control flow loops such as `for`, see [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1fb17-163">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="1fb17-163">Next steps</span></span>

<span data-ttu-id="1fb17-164">Rozpocznij uczenie [na temat Q# typów w ](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="1fb17-164">Start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="1fb17-165">Aby uzyskać więcej informacji o wykrytych i motywacji Q# , zobacz [dlaczego są potrzebne Q# ?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="1fb17-165">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>

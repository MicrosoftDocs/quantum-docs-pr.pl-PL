---
title: Standardowe biblioteki Q-Control i Flow | Microsoft Docs
description: Standardowe biblioteki Q-Control i Flow
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5e865dbb48029724b6f507ecb63b85d10d80c9a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185651"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="56325-103">Przepływ sterowania wyższej kolejności</span><span class="sxs-lookup"><span data-stu-id="56325-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="56325-104">Jedną z podstawowych ról standardowej biblioteki jest ułatwienie bardziej szczegółowych rozwiązań algorytmów wysokiego poziomu jako [programów Quantum](https://en.wikipedia.org/wiki/Quantum_programming).</span><span class="sxs-lookup"><span data-stu-id="56325-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="56325-105">W ten sposób funkcja Q # Canon udostępnia wiele różnych konstrukcji sterowania przepływem, z których każdy jest zaimplementowany przy użyciu częściowej aplikacji funkcji i operacji.</span><span class="sxs-lookup"><span data-stu-id="56325-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="56325-106">Przeskocz bezpośrednio do przykładu Rozważmy przypadek, w którym jeden chce utworzyć "CNOT drabinę" w rejestrze:</span><span class="sxs-lookup"><span data-stu-id="56325-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="56325-107">Ten wzorzec można wyrazić za pomocą iteracji i `for` pętle:</span><span class="sxs-lookup"><span data-stu-id="56325-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="56325-108">Jest to jednak znacznie krótsze i łatwiejsze do odczytania, wyrażone w zakresie <xref:microsoft.quantum.canon.applytoeachca> i funkcji manipulowania tablicami, takich jak <xref:microsoft.quantum.arrays.zip>.</span><span class="sxs-lookup"><span data-stu-id="56325-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="56325-109">W pozostałej części tej sekcji udostępnimy kilka przykładów użycia różnych operacji sterowania przepływem i funkcji dostarczonych przez Canon w celu kompaktowania ekspresowych programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="56325-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="56325-110">Stosowanie operacji i funkcji w odniesieniu do tablic i zakresów</span><span class="sxs-lookup"><span data-stu-id="56325-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="56325-111">Jednym z podstawowych streszczeń dostarczonych przez Canon jest iteracja.</span><span class="sxs-lookup"><span data-stu-id="56325-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="56325-112">Na przykład rozważmy jednostkową część formularza $U \otimes U \otimes \cdots \otimes U $ dla $U jednostkowego dla jednej qubit $.</span><span class="sxs-lookup"><span data-stu-id="56325-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="56325-113">W Q # firma Microsoft może używać <xref:microsoft.quantum.arrays.indexrange> do reprezentowania tego jako `for` pętli w rejestrze:</span><span class="sxs-lookup"><span data-stu-id="56325-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation HAll(register : Qubit[]) : Unit 
is Adj + Ctl {

    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="56325-114">Następnie możemy użyć tej nowej operacji jako `HAll(register)`, aby zastosować $H \otimes H \otimes \cdots \otimes H $.</span><span class="sxs-lookup"><span data-stu-id="56325-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="56325-115">Jest to bardzo skomplikowane, ale szczególnie w większym algorytmie.</span><span class="sxs-lookup"><span data-stu-id="56325-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="56325-116">Ponadto takie podejście jest wyspecjalizowane dla konkretnej operacji, którą chcemy zastosować do każdego qubitu.</span><span class="sxs-lookup"><span data-stu-id="56325-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="56325-117">Możemy użyć faktu, że operacje są pierwszej klasy, aby bardziej szczegółowo wyrażać ten algorytm algorytmu:</span><span class="sxs-lookup"><span data-stu-id="56325-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="56325-118">W tym miejscu sufiks `CA` wskazuje, że wywołanie `ApplyToEach` jest samodzielne i kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="56325-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="56325-119">W tym przypadku, jeśli `U` obsługuje `Adjoint` i `Controlled`, następujące wiersze są równoważne:</span><span class="sxs-lookup"><span data-stu-id="56325-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="56325-120">W szczególności oznacza to, że wywołania do `ApplyToEachCA` mogą pojawić się w operacjach, dla których jest generowana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="56325-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="56325-121">Podobnie <xref:microsoft.quantum.canon.applytoeachindex> jest przydatne do reprezentowania wzorców `U(0, targets[0]); U(1, targets[1]); ...`formularzy i oferuje wersje dla każdej kombinacji funktory obsługiwane przez dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="56325-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="56325-122">`ApplyToEach` jest typu sparametryzowanego, aby można go było używać z operacjami, które pobierają dane wejściowe inne niż `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="56325-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="56325-123">Załóżmy na przykład, że `codeBlocks` jest tablicą wartości <xref:microsoft.quantum.errorcorrection.logicalregister>, które należy odzyskać.</span><span class="sxs-lookup"><span data-stu-id="56325-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="56325-124">Następnie `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` zastosuje `code` kod poprawiający błędy i funkcję odzyskiwania `recoveryFn` niezależnie od siebie.</span><span class="sxs-lookup"><span data-stu-id="56325-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="56325-125">Ta wartość jest przechowywana nawet dla klasycznych danych wejściowych: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` zastosuje rotację $ \pi/$2 o $X $, a następnie rotacją $pi/$3 o $Y $.</span><span class="sxs-lookup"><span data-stu-id="56325-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="56325-126">Program Q # Canon również zapewnia obsługę klasycznych wzorców wyliczenia, które są znane do programowania funkcjonalnego.</span><span class="sxs-lookup"><span data-stu-id="56325-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="56325-127">Na przykład <xref:microsoft.quantum.arrays.fold> implementuje wzorzec $f (f (f (s\_{\Text{Initial}}, x\_0), x\_1), \dots) $ w celu ograniczenia funkcji na liście.</span><span class="sxs-lookup"><span data-stu-id="56325-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="56325-128">Ten wzorzec może służyć do implementowania sum, produktów, wartości minimum, wartości maksymalnych i innych takich funkcji:</span><span class="sxs-lookup"><span data-stu-id="56325-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="56325-129">Podobnie funkcje takie jak <xref:microsoft.quantum.arrays.mapped> i <xref:microsoft.quantum.arrays.mappedbyindex> mogą służyć do wyrażania funkcjonalne koncepcje programowania w Q #.</span><span class="sxs-lookup"><span data-stu-id="56325-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="56325-130">Tworzenie operacji i funkcji</span><span class="sxs-lookup"><span data-stu-id="56325-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="56325-131">Konstrukcje przepływu sterowania oferowane przez firmy Canon podejmują działania i pełnią funkcję jako dane wejściowe, dzięki czemu mogą być w stanie redagować kilka operacji lub działać w jednym możliwym do przeniesieniu.</span><span class="sxs-lookup"><span data-stu-id="56325-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="56325-132">Na przykład wzorzec $UVU ^ {\dagger} $ jest niezwykle powszechny w programowaniu Quantum, w taki sposób, że Canon udostępnia operację <xref:microsoft.quantum.canon.applywith> jako abstrakcję dla tego wzorca.</span><span class="sxs-lookup"><span data-stu-id="56325-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="56325-133">Takie streszczenie umożliwia również bardziej wydajne przestrzeganie obwodów, ponieważ `Controlled` działające na `U(qubit); V(qubit); Adjoint U(qubit);` sekwencji nie muszą działać na poszczególnych `U`ach.</span><span class="sxs-lookup"><span data-stu-id="56325-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="56325-134">Aby to zobaczyć, niech $c (U) $ jest jednostką, która reprezentuje `Controlled U([control], target)` i let $c (V) $ można zdefiniować w taki sam sposób.</span><span class="sxs-lookup"><span data-stu-id="56325-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="56325-135">Następnie dla dowolnego stanu $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ KET{1} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="56325-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="56325-136">\end{align} przez definicję `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="56325-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="56325-137">Z drugiej strony \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c ( V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\psi}.</span><span class="sxs-lookup"><span data-stu-id="56325-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="56325-138">\end{align} się według liniowości, możemy dowiedzieć się, że możemy w ten sposób wziąć pod uwagę $U $ w ten sposób dla wszystkich stanów wejścia.</span><span class="sxs-lookup"><span data-stu-id="56325-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="56325-139">Oznacza to, że $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="56325-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="56325-140">Ponieważ operacje kontrolne mogą być kosztowne ogólnie, korzystanie z kontrolowanych wariantów, takich jak `WithC` i `WithCA`, może pomóc w zmniejszeniu liczby funktory kontroli, które należy zastosować.</span><span class="sxs-lookup"><span data-stu-id="56325-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="56325-141">Jednym $U z nich jest to, że nie trzeba jeszcze wiedzieć, jak zastosować Funktor `Controlled` do `U`.</span><span class="sxs-lookup"><span data-stu-id="56325-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="56325-142">w związku z tym `ApplyWithCA` ma słabsze sygnaturę niż oczekiwano:</span><span class="sxs-lookup"><span data-stu-id="56325-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="56325-143">Podobnie <xref:microsoft.quantum.canon.bind> wytwarza operacje, które stosują sekwencję innych operacji z kolei.</span><span class="sxs-lookup"><span data-stu-id="56325-143">Similarly, <xref:microsoft.quantum.canon.bind> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="56325-144">Na przykład następujące są równoważne:</span><span class="sxs-lookup"><span data-stu-id="56325-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bind([H, X], qubit);
```

<span data-ttu-id="56325-145">Łączenie ze wzorcami iteracji może być szczególnie przydatne:</span><span class="sxs-lookup"><span data-stu-id="56325-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bind([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="56325-146">Kompozycja uporządkowana według czasu</span><span class="sxs-lookup"><span data-stu-id="56325-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="56325-147">Nadal jesteśmy w stanie kontynuować kontrolę przepływu pod względem częściowej aplikacji i funkcji klasycznych, a także można modelować nawet dość zaawansowane koncepcje Quantum w zakresie klasycznej kontroli przepływu.</span><span class="sxs-lookup"><span data-stu-id="56325-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="56325-148">Ta wartość analogiczna jest precyzyjna przez rozpoznawanie, że operatory jednostkowe odpowiadają dokładnie na skutki uboczne operacji wywołujących, tak że jakakolwiek dekompozycja operatorów jednostkowych w warunkach innych operatorów jednostkowych odpowiada za konstruowanie określonego Wywołanie sekwencji dla klasycznej procedury podrzędnej, która emituje instrukcje do działania jako określone operatory jednostkowe.</span><span class="sxs-lookup"><span data-stu-id="56325-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="56325-149">W tym widoku `Bind` jest precyzyjnie reprezentacja produktu macierzy, ponieważ `Bind([A, B])(target)` jest równoważne `A(target); B(target);`, co z kolei jest sekwencją wywołującą odpowiadającą $BA $.</span><span class="sxs-lookup"><span data-stu-id="56325-149">Under this view, `Bind` is precisely the representation of the matrix product, since `Bind([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="56325-150">Bardziej zaawansowanym przykładem jest [rozwinięcie Trotter — Suzuki](https://arxiv.org/abs/math-ph/0506007v1).</span><span class="sxs-lookup"><span data-stu-id="56325-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="56325-151">Jak opisano w sekcji reprezentacja generatora dynamicznego [struktur danych](xref:microsoft.quantum.libraries.data-structures), rozszerzanie Trotter – Suzuki zapewnia szczególnie przydatny sposób wyrażania wartości wykładniczych macierzy.</span><span class="sxs-lookup"><span data-stu-id="56325-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="56325-152">Na przykład zastosowanie rozwinięcia z najniższym porządkiem daje, że dla wszystkich operatorów $A $ i $B $, które $A = A ^ \dagger $ i $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \lim_{n\to\infty} \left (\exp (i t/n) \exp (i B t/n ) \right) ^ n.</span><span class="sxs-lookup"><span data-stu-id="56325-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="56325-153">\end{align} colloquially, oznacza to, że możemy około rozwijać stan w $A + B $ przez alternatywny sposób, w $A $ i $B $.</span><span class="sxs-lookup"><span data-stu-id="56325-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="56325-154">Jeśli reprezentujemy ewolucję w $A $ przez operację `A : (Double, Qubit[]) => Unit`, która stosuje $e ^ {i t A} $, reprezentacja rozwinięcia Trotter – Suzuki pod kątem zmiany kolejności wywołań zostanie wyczyszczona.</span><span class="sxs-lookup"><span data-stu-id="56325-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="56325-155">W konkretnym czasie, w przypadku operacji `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` takiej, `A = U(0, _, _)` i `B = U(1, _, _)`, możemy zdefiniować nową operację reprezentującą integralność `U` na czas $t $ przez generowanie sekwencji formularza</span><span class="sxs-lookup"><span data-stu-id="56325-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="56325-156">Teraz możemy przyczynić się do rozszerzenia Trotter – Suzuki *bez odwołania do Mechanics Quantum*.</span><span class="sxs-lookup"><span data-stu-id="56325-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="56325-157">Rozszerzanie jest efektywnie bardzo konkretnym wzorcem iteracji, które zostały poddane przez $ \eqref{EQ: Trotter-Suzuki-0} $.</span><span class="sxs-lookup"><span data-stu-id="56325-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="56325-158">Ten wzorzec iteracji jest implementowany przez <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span><span class="sxs-lookup"><span data-stu-id="56325-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="56325-159">Sygnatura `DecomposeIntoTimeStepsCA` jest zgodna ze wspólnym wzorcem w języku Q #, gdzie kolekcje, które mogą być tworzone przez tablice lub przez coś, które elementy obliczeniowe na bieżąco są reprezentowane przez krotki, których pierwsze elementy są `Int` wartości wskazujące ich długości.</span><span class="sxs-lookup"><span data-stu-id="56325-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="56325-160">Umieszczenie go razem: kontrolowanie operacji</span><span class="sxs-lookup"><span data-stu-id="56325-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="56325-161">Na koniec firma Canon kompiluje się w `Controlled` Funktor, dostarczając dodatkowe sposoby wykonywania operacji Quantum.</span><span class="sxs-lookup"><span data-stu-id="56325-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="56325-162">Jest to typowy, szczególnie w przypadku arytmetycznego przetwarzania, do warunkowych operacji na Stanach obliczeniowych innych niż $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="56325-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="56325-163">Korzystając z operacji sterowania i funkcji wprowadzonych powyżej, możemy uzyskać więcej ogólnych warunków Quantum w jednej instrukcji.</span><span class="sxs-lookup"><span data-stu-id="56325-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="56325-164">Przejdźmy do sposobu, w jaki <xref:microsoft.quantum.canon.controlledonbitstring> robi to (parametry typu San), a następnie Podzielmy pojedyncze elementy o jeden.</span><span class="sxs-lookup"><span data-stu-id="56325-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="56325-165">Najpierw należy określić operację, która w rzeczywistości wykonuje silną transwierzenie implementacji kontroli na podstawie dowolnego stanu.</span><span class="sxs-lookup"><span data-stu-id="56325-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="56325-166">Nie wywołamy tej operacji bezpośrednio, ale dodamy `_` na początku nazwy, aby wskazać, że jest to implementacja innej konstrukcji w innym miejscu.</span><span class="sxs-lookup"><span data-stu-id="56325-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl),
        controlRegister : Qubit[],
        targetRegister: Qubit[]) 
: Unit 
is Adj + Ctl {
```

<span data-ttu-id="56325-167">Należy pamiętać, że przyjmujemy ciąg bitów, reprezentowany jako tablica `Bool`, którego używamy do określenia warunku, który chcemy zastosować do operacji `oracle`.</span><span class="sxs-lookup"><span data-stu-id="56325-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="56325-168">Ponieważ ta operacja rzeczywiście wykonuje aplikację bezpośrednio, musimy również przyjąć rejestry kontroli i celu, reprezentowane poniżej jako `Qubit[]`.</span><span class="sxs-lookup"><span data-stu-id="56325-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="56325-169">Następnie należy zauważyć, że kontrolowanie stanu podstawy obliczeniowej $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ dla ciągu bitowego $ \vec{s} $ może być zrealizowane przez transformowanie $ \ket{\vec{s}} $ do $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="56325-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="56325-170">W szczególności $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="56325-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="56325-171">Ponieważ $X ^ {\dagger} = X $, oznacza to, że $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.</span><span class="sxs-lookup"><span data-stu-id="56325-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="56325-172">W tym celu możemy zastosować $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, zastosować `Controlled oracle`i przekształcić z powrotem do $ \vec{s} $.</span><span class="sxs-lookup"><span data-stu-id="56325-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="56325-173">Ta konstrukcja jest precyzyjna `ApplyWith`, więc piszemy odpowiednio treść nowej operacji:</span><span class="sxs-lookup"><span data-stu-id="56325-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="56325-174">W tym miejscu użyto <xref:microsoft.quantum.canon.applypaulifrombitstring>, aby zastosować $P $, częściowo stosując się do jego celu do użycia z `ApplyWith`.</span><span class="sxs-lookup"><span data-stu-id="56325-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="56325-175">Należy jednak pamiętać, że konieczne jest przekształcenie rejestru *kontrolki* na nasz żądany formularz, więc częściowo stosujemy wewnętrzną operację `(Controlled oracle)` w elemencie *docelowym*.</span><span class="sxs-lookup"><span data-stu-id="56325-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="56325-176">Spowoduje to pozostawienie `ApplyWith`, które w ten sposób przejdzie do przedziału rejestru kontrolki na $P $.</span><span class="sxs-lookup"><span data-stu-id="56325-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="56325-177">W tym momencie możemy to zrobić, ale jest to w jakiś sposób niesatysfakcjonujący, że nasza nowa operacja nie "działa", podobnie jak zastosowanie `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="56325-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="56325-178">W tym celu możemy zdefiniować nasze nowe koncepcje przepływu sterowania, pisząc funkcję, która powoduje, że baza danych Oracle będzie kontrolowana i która zwraca nową operację.</span><span class="sxs-lookup"><span data-stu-id="56325-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="56325-179">W ten sposób nasza nowa funkcja wygląda i czuje bardzo podobne `Controlled`, co oznacza, że można łatwo definiować zaawansowane nowe konstrukcje przepływu sterowania przy użyciu Q # i firmy Canon razem:</span><span class="sxs-lookup"><span data-stu-id="56325-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl)) 
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
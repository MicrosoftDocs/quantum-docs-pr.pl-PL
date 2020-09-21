---
title: Zmienne w Q#
description: Dowiedz się, jak korzystać z różnych zmiennych w Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- Q#
- $$v
ms.openlocfilehash: bb87f36d3c9b7df195f64e85151e833d494ea945
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835880"
---
# <a name="variables-in-no-locq"></a><span data-ttu-id="dd6f7-103">Zmienne w Q#</span><span class="sxs-lookup"><span data-stu-id="dd6f7-103">Variables in Q#</span></span>

<span data-ttu-id="dd6f7-104">Q# rozróżnia symbole modyfikowalne *i zmienne,* które są powiązane/przypisane do wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-104">Q# distinguishes between mutable and immutable symbols, or *variables*, which are bound/assigned to expressions.</span></span>
<span data-ttu-id="dd6f7-105">Ogólnie rzecz biorąc, zaleca się użycie niezmiennych symboli, ponieważ umożliwia kompilatorowi wykonywanie większej optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="dd6f7-106">Lewa strona powiązania składa się z krotki symboli i prawej strony wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-106">The left-hand-side of a binding consists of a symbol tuple and the right-hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="dd6f7-107">Zmienne niezmienne</span><span class="sxs-lookup"><span data-stu-id="dd6f7-107">Immutable Variables</span></span>

<span data-ttu-id="dd6f7-108">Można przypisać wartość dowolnego typu Q# do zmiennej do ponownego użycia w ramach operacji lub funkcji przy użyciu `let` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-108">You can assign a value of any type in Q# to a variable for reuse within an operation or function by using the `let` keyword.</span></span> 

<span data-ttu-id="dd6f7-109">Niezmienne powiązanie składa się ze słowa kluczowego `let` , a po nim symbolu lub krotki symboli, znaku równości `=` , wyrażenia służącego do powiązania symboli z i kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="dd6f7-110">Przykład:</span><span class="sxs-lookup"><span data-stu-id="dd6f7-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="dd6f7-111">Przypisuje określoną tablicę operatorów Pauli do nazwy zmiennej (lub "symbol"), `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="dd6f7-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="dd6f7-112">W poprzednim przykładzie nie ma potrzeby jawnego określania typu nowej zmiennej, ponieważ wyrażenie po prawej stronie `let` instrukcji jest niejednoznaczne, a kompilator wnioskuje właściwy typ.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-112">In the previous example, there is no need to explicitly specify the type of the new variable, as the expression on the right-hand side of the `let` statement is unambiguous, and the compiler infers the correct type.</span></span> 

<span data-ttu-id="dd6f7-113">Zmienne zdefiniowane przy użyciu `let` są *niezmienne*, co oznacza, że po jego zdefiniowaniu nie można już zmieniać w żaden sposób.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-113">Variables defined using `let` are *immutable*, meaning that once you define it, you can no longer change it in any way.</span></span>
<span data-ttu-id="dd6f7-114">Pozwala to na kilka optymalizacji, w tym optymalizację klasycznej logiki, która działa na zmiennych do zmiany kolejności w przypadku zastosowania `Adjoint` wariantu operacji.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-114">This allows for several beneficial optimizations, including optimization of the classical logic that acts on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="dd6f7-115">Zmienne modyfikowalne</span><span class="sxs-lookup"><span data-stu-id="dd6f7-115">Mutable Variables</span></span>

<span data-ttu-id="dd6f7-116">Jako alternatywę do tworzenia zmiennej przy użyciu `let` `mutable` słowa kluczowego tworzy zmienną modyfikowalną, którą *można* powiązać po jej początkowym utworzeniu za pomocą `set` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-116">As an alternative to creating a variable with `let`, the `mutable` keyword creates a mutable variable that *can* be rebound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="dd6f7-117">Można ponownie powiązać symbole zadeklarowane i powiązane jako część `mutable` instrukcji z inną wartością w dalszej części kodu.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-117">You can rebind symbols declared and bound as part of a `mutable` statement to a different value later in the code.</span></span> <span data-ttu-id="dd6f7-118">Jeśli symbol zostanie powiązana później w kodzie, jego typ nie zmieni się, a nowo związana wartość musi być zgodna z tym typem.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value must be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="dd6f7-119">Ponowne wiązanie modyfikowalnych symboli</span><span class="sxs-lookup"><span data-stu-id="dd6f7-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="dd6f7-120">Można ponownie powiązać modyfikowalną zmienną przy użyciu `set` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-120">You can rebind a mutable variable using a `set` statement.</span></span>
<span data-ttu-id="dd6f7-121">Takie ponowne powiązanie składa się ze słowa kluczowego `set` , po którym następuje ciąg lub krotka symboli, znak równości `=` , wyrażenie służące do ponownego powiązania symboli z i kończący średnik.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="dd6f7-122">Poniżej przedstawiono kilka przykładów technik rebind instrukcji.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-122">The following are some examples of rebinding statement techniques.</span></span>

#### <a name="apply-and-reassign-statements"></a><span data-ttu-id="dd6f7-123">Instrukcje Apply i Reassign</span><span class="sxs-lookup"><span data-stu-id="dd6f7-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="dd6f7-124">Szczególnym rodzajem instrukcji `set` , instrukcja *apply-and-Reassign* , zapewnia wygodny sposób łączenia, jeśli po prawej stronie składa się operator binarny, a wynik ma zostać Przewiązany do lewego argumentu operatora.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-124">A particular kind of `set`-statement, the *apply-and-reassign* statement, provides a convenient way of concatenation if the right-hand side consists of the application of a binary operator, and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="dd6f7-125">Przykład:</span><span class="sxs-lookup"><span data-stu-id="dd6f7-125">For example,</span></span>

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="dd6f7-126">zwiększa wartość licznika `counter` w każdej iteracji `for` pętli.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="dd6f7-127">Poprzedni kod jest równoważny z</span><span class="sxs-lookup"><span data-stu-id="dd6f7-127">The previous code is equivalent to</span></span> 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="dd6f7-128">Podobne instrukcje są dostępne dla wszystkich operatorów binarnych, w których typ lewej strony jest zgodny z typem wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-128">Similar statements are available for all binary operators in which the type of the left-hand side matches the expression type.</span></span> <span data-ttu-id="dd6f7-129">Te instrukcje zapewniają wygodny sposób na gromadzenie wartości.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-129">These statements provide a convenient way to accumulate values.</span></span>

<span data-ttu-id="dd6f7-130">Załóżmy na przykład, że `qubits` jest to rejestr qubits:</span><span class="sxs-lookup"><span data-stu-id="dd6f7-130">For example, supposing `qubits` is a register of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a><span data-ttu-id="dd6f7-131">Instrukcje Update-and-Reassign</span><span class="sxs-lookup"><span data-stu-id="dd6f7-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="dd6f7-132">Podobne łączenie istnieje dla [wyrażeń Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand side.</span></span>
<span data-ttu-id="dd6f7-133">Istnieją odpowiednie instrukcje *Update-and-Reassign* dla *nazwanych elementów* w typach zdefiniowanych przez użytkownika, a także dla *elementów tablicy*.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="dd6f7-134">W przypadku tablic [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) w Q# bibliotece standardowej dostępne są niezbędne narzędzia do wykonywania wielu typowych operacji inicjowania tablic i manipulowania nimi, co pozwala uniknąć konieczności aktualizowania elementów tablicy w pierwszym miejscu.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in the Q# standard library provides the necessary tools for many common array initialization and manipulation needs, and thus helps avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="dd6f7-135">Instrukcje Update-and-Reassign oferują alternatywę w razie konieczności:</span><span class="sxs-lookup"><span data-stu-id="dd6f7-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="dd6f7-136">Za pomocą narzędzi biblioteki dla tablic dostępnych w programie [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) można na przykład łatwo zdefiniować funkcję zwracającą tablicę `Pauli` typów, w których element w indeksie `i` przyjmuje daną `Pauli` wartość, a wszystkie inne wpisy są tożsamością ( `PauliI` ).</span><span class="sxs-lookup"><span data-stu-id="dd6f7-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), you can, for example, easily define a function that returns an array of `Pauli` types where the element at index `i` takes a given `Pauli` value, and all other entries are the identity (`PauliI`).</span></span>

<span data-ttu-id="dd6f7-137">Poniżej przedstawiono dwie definicje takich funkcji, a drugie korzystanie z narzędzi na tym etapie.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

<span data-ttu-id="dd6f7-138">Zamiast przeiterować każdy indeks w tablicy i warunkowo ustawić go na `PauliI` lub dane `pauli` , można zamiast tego użyć z programu, `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) Aby utworzyć tablicę `PauliI` typów, a następnie po prostu zwrócić wyrażenie Copy-and-Update, w którym zmieniono określoną wartość przy indeksie `location` :</span><span class="sxs-lookup"><span data-stu-id="dd6f7-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or the given `pauli`, you can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI` types, and then simply return a copy-and-update expression in which you've changed the specific value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="dd6f7-139">Dekonstrukcja krotki</span><span class="sxs-lookup"><span data-stu-id="dd6f7-139">Tuple Deconstruction</span></span>

<span data-ttu-id="dd6f7-140">Oprócz przypisywania pojedynczej zmiennej można użyć `let` `mutable` słów kluczowych i innych konstrukcji powiązań, takich jak `set` — do rozpakowania zawartości [typu krotki](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="dd6f7-140">In addition to assigning a single variable, you can use the `let` and `mutable` keywords - or any other binding construct, such as `set` - to unpack the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="dd6f7-141">Przypisanie tego formularza jest określane w celu *odtworzenia* elementów tej krotki.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="dd6f7-142">Jeśli po prawej stronie powiązania jest krotka, można ją dekonstruować po przypisaniu.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-142">If the right-hand side of the binding is a tuple, then you can deconstruct that tuple upon assignment.</span></span>
<span data-ttu-id="dd6f7-143">Takie dekonstrukcji mogą dotyczyć krotek zagnieżdżonych, a każda pełna lub częściowa dekonstrukcja jest prawidłowa, o ile kształt krotki po prawej stronie jest zgodny z kształtem krotki symboli.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-143">Such deconstructions can involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right-hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="dd6f7-144">Przykład:</span><span class="sxs-lookup"><span data-stu-id="dd6f7-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="dd6f7-145">Zakresy powiązań</span><span class="sxs-lookup"><span data-stu-id="dd6f7-145">Binding Scopes</span></span>

<span data-ttu-id="dd6f7-146">Ogólnie rzecz biorąc, powiązania symboli wykraczają poza zakres i stają się nieaktywne na końcu bloku instrukcji, w którym występują.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="dd6f7-147">Istnieją dwa wyjątki od tej reguły:</span><span class="sxs-lookup"><span data-stu-id="dd6f7-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="dd6f7-148">Powiązanie zmiennej pętli `for` pętli jest w zakresie dla treści pętli for, ale nie po końcu pętli.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="dd6f7-149">Wszystkie trzy części `repeat` / `until` pętli (treść, test i naprawa) działają jako pojedynczy zakres, dlatego symbole, które są powiązane z treścią są dostępne w teście i naprawie.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) act as a single scope, so symbols that are bound in the body are available in the test and the fixup.</span></span>

<span data-ttu-id="dd6f7-150">W przypadku obu typów pętli każdy przebieg przez pętlę działa we własnym zakresie, dlatego powiązania z wcześniejszego przebiegu nie są dostępne w późniejszym przebiegu.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-150">For both types of loops, each pass through the loop runs in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="dd6f7-151">Aby uzyskać więcej informacji na temat tych pętli, zobacz [Flow Control](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="dd6f7-151">For more information on these loops, see [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="dd6f7-152">Bloki wewnętrzne dziedziczą powiązania symboli z bloków zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-152">Inner blocks inherit symbol bindings from outer blocks.</span></span>
<span data-ttu-id="dd6f7-153">Można powiązać symbol tylko raz na blok; nie można zdefiniować symbolu o takiej samej nazwie jak inny symbol znajdujący się w zakresie (bez "przesłaniania").</span><span class="sxs-lookup"><span data-stu-id="dd6f7-153">You can only bind a symbol once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="dd6f7-154">Następujące sekwencje są dozwolone:</span><span class="sxs-lookup"><span data-stu-id="dd6f7-154">The following sequences are legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="dd6f7-155">oraz</span><span class="sxs-lookup"><span data-stu-id="dd6f7-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="dd6f7-156">Może to jednak być niedozwolone:</span><span class="sxs-lookup"><span data-stu-id="dd6f7-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="dd6f7-157">w takim przypadku:</span><span class="sxs-lookup"><span data-stu-id="dd6f7-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="dd6f7-158">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="dd6f7-158">Next steps</span></span>

<span data-ttu-id="dd6f7-159">Dowiedz się więcej na temat [pracy z usługą Qubits](xref:microsoft.quantum.guide.qubits) w programie Q# .</span><span class="sxs-lookup"><span data-stu-id="dd6f7-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>
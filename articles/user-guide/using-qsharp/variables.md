---
title: 'Zmienne w Q #'
description: Opis wypełnienia
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 456c05d4ca66a747e0cc514a30c6bbb33610f481
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327785"
---
# <a name="variables-in-q"></a><span data-ttu-id="8df41-103">Zmienne w Q #</span><span class="sxs-lookup"><span data-stu-id="8df41-103">Variables in Q#</span></span>

<span data-ttu-id="8df41-104">Polecenie Q # rozróżnia symbole modyfikowalne i zmienne, czyli "zmienne", które są powiązane/przypisane do wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="8df41-104">Q# distinguishes between mutable and immutable symbols, or "variables", which are bound/assigned to expressions.</span></span>
<span data-ttu-id="8df41-105">Ogólnie rzecz biorąc, zaleca się użycie niezmiennych symboli, ponieważ umożliwia kompilatorowi wykonywanie większej optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="8df41-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="8df41-106">Lewa strona powiązania składa się z krotki symboli i prawej strony wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="8df41-106">The left-hand-side of a binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="8df41-107">Zmienne niezmienne</span><span class="sxs-lookup"><span data-stu-id="8df41-107">Immutable Variables</span></span>

<span data-ttu-id="8df41-108">Wartość dowolnego typu w Q # można przypisać do zmiennej do ponownego użycia w ramach operacji lub funkcji za pomocą `let` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="8df41-108">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>

<span data-ttu-id="8df41-109">Niezmienne powiązanie składa się ze słowa kluczowego `let` , a po nim symbolu lub krotki symboli, znaku równości `=` , wyrażenia służącego do powiązania symboli z i kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="8df41-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="8df41-110">Przykład:</span><span class="sxs-lookup"><span data-stu-id="8df41-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="8df41-111">Przypisuje określoną tablicę operatorów Pauli do nazwy zmiennej (lub "symbol"), `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="8df41-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="8df41-112">Nie trzeba jawnie określać typu naszej nowej zmiennej, ponieważ wyrażenie po prawej stronie `let` instrukcji jest niejednoznaczne i typ jest wnioskowany przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="8df41-112">We did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="8df41-113">Zmienne zdefiniowane przy użyciu `let` są *niezmienne*, co oznacza, że po jego zdefiniowaniu nie można już zmieniać w jakikolwiek sposób.</span><span class="sxs-lookup"><span data-stu-id="8df41-113">Variables defined using `let` are *immutable*, meaning that once it has been defined, it can no longer be changed in any way.</span></span>
<span data-ttu-id="8df41-114">Pozwala to na kilka optymalizacji, w tym optymalizację klasycznej logiki działającej na zmienne, które mają być zmieniane w celu zastosowania `Adjoint` wariantu operacji.</span><span class="sxs-lookup"><span data-stu-id="8df41-114">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="8df41-115">Zmienne modyfikowalne</span><span class="sxs-lookup"><span data-stu-id="8df41-115">Mutable Variables</span></span>

<span data-ttu-id="8df41-116">Alternatywnie, aby utworzyć zmienną za pomocą `let` `mutable` słowa kluczowego, zostanie utworzona zmienna modyfikowalna, którą *można* ponownie powiązać po jej początkowym utworzeniu za pomocą `set` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="8df41-116">As an alternative to creating a variable with `let`, the `mutable` keyword will create a mutable variable that *can* be re-bound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="8df41-117">Symbole zadeklarowane i powiązane jako część `mutable` instrukcji mogą być ponownie powiązane z inną wartością w kodzie.</span><span class="sxs-lookup"><span data-stu-id="8df41-117">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> <span data-ttu-id="8df41-118">Jeśli symbol zostanie powiązana później w kodzie, jego typ nie ulegnie zmianie, a nowo związana wartość musi być zgodna z tym typem.</span><span class="sxs-lookup"><span data-stu-id="8df41-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="8df41-119">Ponowne wiązanie modyfikowalnych symboli</span><span class="sxs-lookup"><span data-stu-id="8df41-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="8df41-120">Zmienna modyfikowalna może być powiązana przy użyciu `set` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="8df41-120">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="8df41-121">Takie ponowne powiązanie składa się ze słowa kluczowego `set` , po którym następuje ciąg lub krotka symboli, znak równości `=` , wyrażenie służące do ponownego powiązania symboli z i kończący średnik.</span><span class="sxs-lookup"><span data-stu-id="8df41-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="8df41-122">Tutaj udostępniamy niektóre możliwe przykłady technik rebind instrukcji</span><span class="sxs-lookup"><span data-stu-id="8df41-122">Here, we provide some possible examples of rebinding statement techniques</span></span>

### <a name="apply-and-reassign-statements"></a><span data-ttu-id="8df41-123">Instrukcje Apply i Reassign</span><span class="sxs-lookup"><span data-stu-id="8df41-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="8df41-124">Szczególnym rodzajem `set` instrukcji, do których odwołuje się jako instrukcja *apply-and-Reassign* , stanowi wygodny sposób łączenia, jeśli prawa strona składa się z aplikacji operatora binarnego, a wynik jest przełączany do lewego argumentu operatora.</span><span class="sxs-lookup"><span data-stu-id="8df41-124">A particular kind of `set`-statement we refer to as an *apply-and-reassign* statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="8df41-125">Na przykład</span><span class="sxs-lookup"><span data-stu-id="8df41-125">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="8df41-126">zwiększa wartość licznika `counter` w każdej iteracji `for` pętli.</span><span class="sxs-lookup"><span data-stu-id="8df41-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="8df41-127">Powyższy kod jest równoważny z</span><span class="sxs-lookup"><span data-stu-id="8df41-127">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="8df41-128">Podobne instrukcje są dostępne dla wszystkich operatorów binarnych, w których typ po lewej stronie jest zgodny z typem wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="8df41-128">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="8df41-129">Pozwala to na przykład wygodny sposób na gromadzenie wartości.</span><span class="sxs-lookup"><span data-stu-id="8df41-129">This provides for example a convenient way to accumulate values.</span></span>

<span data-ttu-id="8df41-130">Załóżmy na przykład, że `qubits` jest to REGSITER qubits:</span><span class="sxs-lookup"><span data-stu-id="8df41-130">For example, supposing `qubits` is a regsiter of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a><span data-ttu-id="8df41-131">Instrukcje Update-and-Reassign</span><span class="sxs-lookup"><span data-stu-id="8df41-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="8df41-132">Podobne łączenie istnieje dla [wyrażeń Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="8df41-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand-side.</span></span>
<span data-ttu-id="8df41-133">Istnieją odpowiednie instrukcje *Update-and-Reassign* dla *nazwanych elementów* w typach zdefiniowanych przez użytkownika, a także dla *elementów tablicy*.</span><span class="sxs-lookup"><span data-stu-id="8df41-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

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

<span data-ttu-id="8df41-134">W przypadku tablic [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) w naszych bibliotekach standardowych dostępne są niezbędne narzędzia do wykonywania wielu typowych operacji inicjowania tablic i manipulowania nimi, co pozwala uniknąć konieczności aktualizowania elementów tablicy w pierwszym miejscu.</span><span class="sxs-lookup"><span data-stu-id="8df41-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in our standard libraries provides the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="8df41-135">Instrukcje Update-and-Reassign oferują alternatywę w razie konieczności:</span><span class="sxs-lookup"><span data-stu-id="8df41-135">Update-and-reassign statements provide an alternative if needed:</span></span>

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

<span data-ttu-id="8df41-136">Za pomocą narzędzi biblioteki dla tablic dostępnych w programie [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) możemy na przykład łatwo zdefiniować funkcję zwracającą tablicę Paul, gdzie Pauli przy indeksie `i` przyjmuje daną wartość, a wszystkie inne wpisy są tożsamością.</span><span class="sxs-lookup"><span data-stu-id="8df41-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can, for example, easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity.</span></span>

<span data-ttu-id="8df41-137">Poniżej przedstawiono dwie definicje takich funkcji, a drugie korzystanie z narzędzi na tym etapie.</span><span class="sxs-lookup"><span data-stu-id="8df41-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

<span data-ttu-id="8df41-138">Zamiast przeiterować każdy indeks w tablicy i warunkowo ustawić go na `PauliI` lub `Pauli` , zamiast tego można użyć `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) do tworzenia tablicy `PauliI` , a następnie po prostu zwrócić wyrażenie Copy-and-Update, w którym zmieniono wartość specifc w indeksie `location` :</span><span class="sxs-lookup"><span data-stu-id="8df41-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or `Pauli`, we can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI`'s, and then simply returning a copy-and-update expression in which we've changed the specifc value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="8df41-139">Dekonstrukcja krotki</span><span class="sxs-lookup"><span data-stu-id="8df41-139">Tuple Deconstruction</span></span>

<span data-ttu-id="8df41-140">Oprócz przypisywania pojedynczej zmiennej `let` i `mutable` słów kluczowych---lub w rzeczywistości każda inna konstrukcja powiązania, taka jak `set` opisana poniżej),---również zezwalać na rozpakowywanie zawartości [typu krotki](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="8df41-140">In addition to assigning a single variable, the `let` and `mutable` keywords---or in fact any other binding construct, such as `set` (described below)---also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="8df41-141">Przypisanie tego formularza jest określane w celu *odtworzenia* elementów tej krotki.</span><span class="sxs-lookup"><span data-stu-id="8df41-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="8df41-142">Jeśli po prawej stronie powiązania jest krotka, ta krotka może zostać rozbudowana po przypisaniu.</span><span class="sxs-lookup"><span data-stu-id="8df41-142">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="8df41-143">Takie dekonstrukcji mogą dotyczyć krotek zagnieżdżonych, a każda pełna lub częściowa dekonstrukcja jest prawidłowa, o ile kształt krotki po prawej stronie jest zgodny z kształtem krotki symboli.</span><span class="sxs-lookup"><span data-stu-id="8df41-143">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="8df41-144">Przykład:</span><span class="sxs-lookup"><span data-stu-id="8df41-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="8df41-145">Zakresy powiązań</span><span class="sxs-lookup"><span data-stu-id="8df41-145">Binding Scopes</span></span>

<span data-ttu-id="8df41-146">Ogólnie rzecz biorąc, powiązania symboli wykraczają poza zakres i stają się nieaktywne na końcu bloku instrukcji, w którym występują.</span><span class="sxs-lookup"><span data-stu-id="8df41-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="8df41-147">Istnieją dwa wyjątki od tej reguły:</span><span class="sxs-lookup"><span data-stu-id="8df41-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="8df41-148">Powiązanie zmiennej pętli `for` pętli jest w zakresie dla treści pętli for, ale nie po końcu pętli.</span><span class="sxs-lookup"><span data-stu-id="8df41-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="8df41-149">Wszystkie trzy części `repeat` / `until` pętli (treść, test i naprawa) są traktowane jako pojedynczy zakres, dlatego symbole, które są powiązane z treścią, są dostępne w teście i w naprawie.</span><span class="sxs-lookup"><span data-stu-id="8df41-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="8df41-150">W przypadku obu typów pętli każdy przechodzi przez pętlę do własnego zakresu, dlatego powiązania z wcześniejszych przebiegów nie są dostępne w późniejszym przebiegu.</span><span class="sxs-lookup"><span data-stu-id="8df41-150">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="8df41-151">Szczegółowe informacje o tych pętlach można znaleźć w [przepływie sterowania](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="8df41-151">Details on these loops can be found at [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="8df41-152">Powiązania symboli z bloków zewnętrznych są dziedziczone przez bloki wewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="8df41-152">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="8df41-153">Symbol może być powiązany tylko raz na blok; nie można zdefiniować symbolu o takiej samej nazwie jak inny symbol znajdujący się w zakresie (bez "przesłaniania").</span><span class="sxs-lookup"><span data-stu-id="8df41-153">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="8df41-154">Następujące sekwencje byłyby dozwolone:</span><span class="sxs-lookup"><span data-stu-id="8df41-154">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="8df41-155">oraz</span><span class="sxs-lookup"><span data-stu-id="8df41-155">and</span></span>

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

<span data-ttu-id="8df41-156">Może to jednak być niedozwolone:</span><span class="sxs-lookup"><span data-stu-id="8df41-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="8df41-157">w takim przypadku:</span><span class="sxs-lookup"><span data-stu-id="8df41-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="8df41-158">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="8df41-158">Next steps</span></span>

<span data-ttu-id="8df41-159">Dowiedz się więcej na temat [pracy z Qubits w usłudze](xref:microsoft.quantum.guide.qubits) Q #.</span><span class="sxs-lookup"><span data-stu-id="8df41-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>
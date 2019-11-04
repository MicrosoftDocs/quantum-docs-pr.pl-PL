---
title: 'Techniki Q # — dalsze przechodzenie | Microsoft Docs'
description: 'Techniki Q # — dalsze przechodzenie'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4677b0f9c4f64a9c1bc46d34e8a883dc006ba8f0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183305"
---
# <a name="going-further"></a><span data-ttu-id="bd0b3-103">Dalsze przechodzenie</span><span class="sxs-lookup"><span data-stu-id="bd0b3-103">Going Further</span></span> #

<span data-ttu-id="bd0b3-104">Teraz, gdy wiesz już, jak pisać interesujące programy Quantum w Q #, ta sekcja jest bardziej wydajna, wprowadzając kilka bardziej zaawansowanych tematów, które powinny być przydatne w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>

<!-- Moved Debugging and Testing Quantum Programs section to a separate article -->

## <a name="generic-operations-and-functions"></a><span data-ttu-id="bd0b3-105">Operacje ogólne i funkcje</span><span class="sxs-lookup"><span data-stu-id="bd0b3-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="bd0b3-106">W tej sekcji przyjęto założenie, że podstawowa znajomość metod [ogólnych C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics) [ F#w programie ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ szablonów](https://docs.microsoft.com/cpp/cpp/templates-cpp)lub podobnych podejścia do programowania w innych językach.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="bd0b3-107">Wiele funkcji i operacji, które firma Microsoft może chcieć zdefiniować, nie opiera się na typach ich danych wejściowych, ale raczej niejawnie używa ich typów za pośrednictwem innej funkcji lub operacji.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="bd0b3-108">Rozważmy na przykład, że koncepcja *mapy* jest wspólna dla wielu języków funkcjonalnych; dana funkcja $f (x) $ i Kolekcja wartości $\{x_1, x_2, \dots, x_n\}$, map zwraca nową kolekcję $\{f (x_1), f (x_2), \dots, f (x_n)\}$.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="bd0b3-109">W celu zaimplementowania tego zadania w programie Q # można skorzystać z tej funkcji jako pierwszej klasy.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="bd0b3-110">Napiszmy do krótkiego przykładu `Map`przy użyciu ★ jako symbolu zastępczego, aby określić, jakich typów potrzebujemy.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="bd0b3-111">Należy zauważyć, że ta funkcja wygląda bardzo podobnie niezależnie od tego, jakie rzeczywiste typy zostały zastąpione.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="bd0b3-112">Mapa z liczb całkowitych na Paul, na przykład, wygląda podobnie jak mapa od liczb zmiennoprzecinkowych do ciągów:</span><span class="sxs-lookup"><span data-stu-id="bd0b3-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="bd0b3-113">W zasadzie można napisać wersję `Map` dla każdej pary typów, które napotykamy, ale wprowadzamy wiele problemów.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="bd0b3-114">Na przykład jeśli znajdziesz usterkę w `Map`, należy upewnić się, że poprawka jest stosowana jednolicie we wszystkich wersjach `Map`.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="bd0b3-115">Ponadto, jeśli tworzymy nową krotkę lub UDT, teraz musimy utworzyć nową `Map`, która będzie musiała być nowym typem.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="bd0b3-116">Chociaż jest to pozyskanie dla niewielkiej liczby takich funkcji, ponieważ zbieramy więcej i więcej funkcji tego samego formularza co `Map`, koszt wprowadzenia nowych typów stanie się nieuzasadniony bardzo krótki.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="bd0b3-117">Większość tego rodzaju trudności wynika jednak z tego, że kompilator nie udostępnił informacji, które są potrzebne do rozpoznania, w jaki sposób są powiązane różne wersje `Map`.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="bd0b3-118">Efektywnie, chcemy, aby kompilator traktował `Map` jako rodzaj funkcji matematycznej z *typów* q # do funkcji q #.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="bd0b3-119">Pojęcie to jest formalne przez umożliwienie funkcjom i operacjom posiadania *parametrów typu*, a także ich zwykłych parametrów krotek.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="bd0b3-120">W powyższych przykładach chcemy myśleć, że `Map` jako parametry typu `Int, Pauli` w pierwszym przypadku i `Double, String` w drugim przypadku.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="bd0b3-121">W większości przypadków te parametry typu mogą być używane tak, jakby były typami zwyczajnymi: używamy wartości parametrów typu do wprowadzania tablic i krotek, wywoływania funkcji i operacji oraz przypisywania do zmiennych normalnych lub modyfikowalnych.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="bd0b3-122">Najbardziej skrajnym przypadkiem pośredniego zależności jest qubits, gdzie program Q # nie może bezpośrednio polegać na strukturze typu `Qubit`, ale **musi** przekazać takie typy do innych operacji i funkcji.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="bd0b3-123">Powracając do powyższego przykładu, możemy zobaczyć, że potrzebujemy `Map`, aby zawierały parametry typu, jeden do reprezentowania danych wejściowych do `fn` i jeden do reprezentowania danych wyjściowych z `fn`.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="bd0b3-124">W języku Q # jest to zapisywana przez dodanie nawiasów ostrych (`<>`, nie brakets $ \braket{}$!) po nazwie funkcji lub operacji w swojej deklaracji oraz przez wystawienie poszczególnych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="bd0b3-125">Nazwa każdego parametru typu musi rozpoczynać się od osi `'`, co oznacza, że jest parametrem typu, a nie typem zwykłym (znanym także jako *konkretny* typ).</span><span class="sxs-lookup"><span data-stu-id="bd0b3-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="bd0b3-126">W przypadku `Map`należy napisać:</span><span class="sxs-lookup"><span data-stu-id="bd0b3-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="bd0b3-127">Należy zauważyć, że definicja `Map<'Input, 'Output>` wygląda bardzo podobnie do wersji zanotowanych przed.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="bd0b3-128">Jedyną różnicą jest to, że został jawnie poinformowany kompilator, że `Map` nie zależał bezpośrednio od tego, co `'Input` i `'Output` są, ale działa w przypadku każdego z dwóch typów przy użyciu ich pośrednio za pośrednictwem `fn`.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="bd0b3-129">Po zdefiniowaniu `Map<'Input, 'Output>` w ten sposób możemy ją wywołać, tak jakby była to funkcja zwykła:</span><span class="sxs-lookup"><span data-stu-id="bd0b3-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="bd0b3-130">Pisanie funkcji ogólnych i operacji to jedno miejsce, w którym "krotka spójna z krotką" to bardzo użyteczny sposób, aby myśleć o funkcjach i operacjach pytań i odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="bd0b3-131">Ponieważ każda funkcja przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście, dane wejściowe typu `'T -> 'U` dopasowują *dowolną* funkcję Q #.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="bd0b3-132">Podobnie każda operacja może zostać przeniesiona do danych wejściowych typu `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="bd0b3-133">W drugim przykładzie należy wziąć pod uwagę wyzwanie napisania funkcji, która zwraca skład dwóch innych funkcji:</span><span class="sxs-lookup"><span data-stu-id="bd0b3-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="bd0b3-134">W tym miejscu należy określić dokładnie `A`, `B`i `C`, a tym samym znacznie ograniczyć narzędzie do nowej funkcji `Compose`.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="bd0b3-135">Po wszystkich `Compose` zależy tylko od `A`, `B`i `C` *za pośrednictwem* `innerFn` i `outerFn`.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="bd0b3-136">Alternatywnie, możemy dodać parametry typu do `Compose`, które wskazują, że działa dla *dowolnego* `A`, `B`i `C`, tak długo, jak te parametry są zgodne z oczekiwanymi przez `innerFn` i `outerFn`:</span><span class="sxs-lookup"><span data-stu-id="bd0b3-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="bd0b3-137">Biblioteki Q # Standard oferują wiele takich operacji i funkcji sparametryzowanych typu, aby ułatwić przepływ sterowania wyższym kolejnością.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="bd0b3-138">Są one omówione bardziej szczegółowo w [przewodniku po bibliotece standardowej Q #](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="bd0b3-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="bd0b3-139">Pożyczanie Qubits</span><span class="sxs-lookup"><span data-stu-id="bd0b3-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="bd0b3-140">Mechanizm pożyczania umożliwia alokację qubits, która może być używana jako miejsce do rozliczania podczas obliczeń.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="bd0b3-141">Te qubits zazwyczaj nie są w stanie czystym, tzn. nie muszą być inicjowane w znanym stanie, takim jak $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="bd0b3-142">Jeden również mówi "Dirty" qubits, gdy ich stan jest nieznany i może nawet być Entangled z innymi częściami pamięci komputera Quantum.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="bd0b3-143">Wśród znanych przypadków użycia zanieczyszczonych qubits są implementacje bram CNOT z wieloma kontrolowanymi żądaniami, które wymagają tylko bardzo małej liczby qubits i implementacji przyrostów.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="bd0b3-144">W programie Canon istnieją przykłady, które używają słowa kluczowego `borrowing`, na przykład funkcja `MultiControlledXBorrow` zdefiniowana poniżej.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="bd0b3-145">Jeśli `controls` określa, że kontrolka qubits powinna zostać dodana do operacji `X`, w tej implementacji zostanie dodana ogólna `Length(controls)-2` wiele zanieczyszczonych ancillas.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="bd0b3-146">Należy zauważyć, że rozległe użycie `With` Combinator---w swojej formie, która ma zastosowanie do operacji, które obsługują sąsiednie, tj., `WithA`---zostało wykonane w tym przykładzie, który jest dobrym stylem programowania jako dodanie kontroli do struktur obejmujących tylko `With` propaguje formant do operacji wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="bd0b3-147">Należy również zwrócić uwagę, że w tym miejscu oprócz `body` operacji wdrożenie `controlled` treści operacji zostało jawnie dostarczone, a nie do instrukcji `controlled auto`.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="bd0b3-148">Przyczyną tego jest fakt, że wiemy ze struktury obwodu, jak łatwo dodać dalsze kontrolki, które są korzystne w porównaniu z dodawaniem kontroli do poszczególnych bram i każdej bramy w `body`.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="bd0b3-149">Warto porównać ten kod z inną funkcją firmy Canon `MultiControlledXClean`, która osiąga ten sam cel implementacji operacji pomnożonej `X`, ale korzysta z kilku czystych qubits przy użyciu mechanizmu `using`.</span><span class="sxs-lookup"><span data-stu-id="bd0b3-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

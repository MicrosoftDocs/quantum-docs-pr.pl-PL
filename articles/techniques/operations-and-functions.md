---
title: 'Techniki Q # — operacje i funkcje | Microsoft Docs'
description: 'Metody Q # — operacje i funkcje'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 06da09dc9c6e0ba0331db6bc0cd3d2ddeb287113
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183458"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="fc218-103">Operacje i funkcje pytań i odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="fc218-103">Q# Operations and Functions</span></span>

<span data-ttu-id="fc218-104">Programy Q # składają się z jednej lub wielu *operacji* , które opisują efekty uboczne działania Quantum mogą mieć na dane Quantum oraz co najmniej jedną *funkcję* , która zezwala na modyfikacje danych klasycznych.</span><span class="sxs-lookup"><span data-stu-id="fc218-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="fc218-105">W przeciwieństwie do operacji, funkcje są używane do opisywania przejrzystie klasycznego zachowania i nie mają żadnych efektów poza obliczaniem klasycznej wartości wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="fc218-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="fc218-106">Każda operacja zdefiniowana w Q # może następnie wywołać dowolną liczbę innych operacji, łącznie z wbudowanymi operacjami wewnętrznymi zdefiniowanymi przez język.</span><span class="sxs-lookup"><span data-stu-id="fc218-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="fc218-107">Określony sposób, w jaki te operacje wewnętrzne są zdefiniowane, zależy od maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="fc218-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="fc218-108">Po skompilowaniu każda operacja jest reprezentowana jako typ klasy .NET, który można dostarczyć dla maszyn docelowych.</span><span class="sxs-lookup"><span data-stu-id="fc218-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="fc218-109">Definiowanie nowych operacji</span><span class="sxs-lookup"><span data-stu-id="fc218-109">Defining New Operations</span></span>

<span data-ttu-id="fc218-110">Jak opisano powyżej, najbardziej podstawowy blok konstrukcyjny w programie Quantum Zapisano w Q # jest *operacją*, którą można wywołać z klasycznej aplikacji .NET, np. za pomocą symulatora lub przez inne operacje w usłudze Q #.</span><span class="sxs-lookup"><span data-stu-id="fc218-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="fc218-111">Każda operacja przyjmuje dane wejściowe, tworzy dane wyjściowe i określa Implementację dla co najmniej jednej specjalizacji operacji.</span><span class="sxs-lookup"><span data-stu-id="fc218-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="fc218-112">Na przykład następująca operacja definiuje tylko domyślną specjalizację treści i przyjmuje pojedyncze qubit jako dane wejściowe, a następnie wywołuje wbudowaną operację `X` na tym wejściu:</span><span class="sxs-lookup"><span data-stu-id="fc218-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="fc218-113">Słowo kluczowe `operation` rozpoczyna definicję operacji, a po niej następuje nazwa; tutaj `BitFlip`.</span><span class="sxs-lookup"><span data-stu-id="fc218-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="fc218-114">Następnie typ danych wejściowych jest zdefiniowany jako `Qubit`, wraz z nazwą `target` do odwoływania się do danych wejściowych w ramach nowej operacji.</span><span class="sxs-lookup"><span data-stu-id="fc218-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="fc218-115">Podobnie `Unit` definiuje, że dane wyjściowe operacji są puste.</span><span class="sxs-lookup"><span data-stu-id="fc218-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="fc218-116">Jest to podobne do `void` w C# i innych językach bezwzględnych i jest równoważne `unit` w F# i innych językach funkcjonalnych.</span><span class="sxs-lookup"><span data-stu-id="fc218-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="fc218-117">Szczegółowo omówiono poniżej, ale każda operacja w Q # przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.</span><span class="sxs-lookup"><span data-stu-id="fc218-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="fc218-118">Dane wejściowe i wyjściowe są następnie reprezentowane przy użyciu *krotek*, które zbierają wiele wartości w jedną wartość.</span><span class="sxs-lookup"><span data-stu-id="fc218-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="fc218-119">Nieformalnie Załóżmy, że Q # to język "Krotka w poziomie".</span><span class="sxs-lookup"><span data-stu-id="fc218-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="fc218-120">Po tym koncepcji `()` powinna zostać odczytana jako spójna krotka, która ma typ `Unit`.</span><span class="sxs-lookup"><span data-stu-id="fc218-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="fc218-121">W ramach nowej operacji implementacja może być określona bezpośrednio w deklaracji, jeśli tylko implementacja specjalizacji treści domyślnej musi być określona jawnie.</span><span class="sxs-lookup"><span data-stu-id="fc218-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="fc218-122">Ponadto można zdefiniować implementacje programu, na przykład jedną lub więcej operacji `functor`, jak zostało to opisane poniżej.</span><span class="sxs-lookup"><span data-stu-id="fc218-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="fc218-123">W powyższym przykładzie jedyną instrukcją jest wywołanie wbudowanej operacji Q # <xref:microsoft.quantum.intrinsic.x>.</span><span class="sxs-lookup"><span data-stu-id="fc218-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="fc218-124">Operacje mogą również zwracać bardziej interesujące typy niż `Unit`.</span><span class="sxs-lookup"><span data-stu-id="fc218-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="fc218-125">Na przykład operacja <xref:microsoft.quantum.intrinsic.m> zwraca dane wyjściowe typu `Result`, co oznacza, że przeprowadzono pomiar.</span><span class="sxs-lookup"><span data-stu-id="fc218-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="fc218-126">Możemy przekazać dane wyjściowe operacji do innej operacji lub użyć jej przy użyciu słowa kluczowego `let`, aby zdefiniować nową zmienną.</span><span class="sxs-lookup"><span data-stu-id="fc218-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="fc218-127">Pozwala to na reprezentowanie klasycznego obliczenia, które współdziała z operacjami Quantum na niskim poziomie, na przykład w przypadku kodowania w stojaku:</span><span class="sxs-lookup"><span data-stu-id="fc218-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="fc218-128">Funktory, sąsiadujące i kontrolowane</span><span class="sxs-lookup"><span data-stu-id="fc218-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="fc218-129">Jeśli operacja implementuje transformację jednostkową, można zdefiniować sposób działania operacji przy *adjointed* lub *kontrolowanej*.</span><span class="sxs-lookup"><span data-stu-id="fc218-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="fc218-130">Podległych specjalizacja operacji określa, jak działa po uruchomieniu w odwrotnym czasie, podczas kontrolowanej specjalizacji określa sposób działania operacji po zastosowaniu warunku na stanie rejestru Quantum.</span><span class="sxs-lookup"><span data-stu-id="fc218-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="fc218-131">Istnienie tych specjalizacji może być zadeklarowane jako część sygnatury operacji: `is Adj + Ctl` w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="fc218-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="fc218-132">Odpowiednia implementacja dla każdej takiej niejawnie zadeklarowanej specjalizacji jest generowana przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="fc218-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="fc218-133">Wiele operacji w Q # reprezentuje bramy jednostkowe.</span><span class="sxs-lookup"><span data-stu-id="fc218-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="fc218-134">Jeśli $U $ jest bramą jednostkową reprezentowaną przez operację `U`, wówczas `Adjoint U` reprezentuje bramę jednostkową $U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="fc218-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="fc218-135">W przypadku, gdy implementacja nie może zostać wygenerowana przez kompilator, można ją jawnie określić.</span><span class="sxs-lookup"><span data-stu-id="fc218-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="fc218-136">Takie jawne deklaracje specjalizacji mogą składać się z odpowiedniej dyrektywy generacji lub implementacji zdefiniowanej przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fc218-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="fc218-137">Kod w `PrepareEntangledPair` powyżej na przykład jest odpowiednikiem poniższego kodu zawierającego jawne deklaracje specjalizacji:</span><span class="sxs-lookup"><span data-stu-id="fc218-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="fc218-138">Słowo kluczowe `auto` wskazuje, że kompilator powinien określić sposób generowania implementacji specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="fc218-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="fc218-139">Jeśli kompilator nie może automatycznie wygenerować implementacji dla konkretnej specjalizacji lub można określić bardziej wydajną implementację, implementacja może być również zdefiniowana ręcznie.</span><span class="sxs-lookup"><span data-stu-id="fc218-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="fc218-140">W powyższym przykładzie `adjoint invert;` wskazuje, że podległych specjalizacji ma być generowana przez odwrócenie implementacji treści, a `controlled adjoint invert;` wskazuje, że kontrolowana podległych specjalizacji ma być generowany przez odwrócenie danej implementacji kontrolowana specjalizacja.</span><span class="sxs-lookup"><span data-stu-id="fc218-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="fc218-141">Zobaczymy więcej przykładów tego elementu w [przepływie sterowania wyższej kolejności](xref:microsoft.quantum.concepts.control-flow).</span><span class="sxs-lookup"><span data-stu-id="fc218-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="fc218-142">Aby wywołać specjalizację operacji, użyj słowa kluczowego `Adjoint` lub `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="fc218-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="fc218-143">Na przykład powyższy przykładowy przykład kodowania można napisać bardziej kompaktowo, używając sąsiadującego `PrepareEntangledPair` do przekształcenia stanu Entangled z powrotem do pary unentangled qubits:</span><span class="sxs-lookup"><span data-stu-id="fc218-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="fc218-144">Istnieje kilka ważnych ograniczeń, które należy wziąć pod uwagę podczas projektowania operacji do użycia z funktory.</span><span class="sxs-lookup"><span data-stu-id="fc218-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="fc218-145">W przypadku niekrytycznej specjalizacji dla operacji korzystającej z wartości wyjściowej żadnej innej operacji nie może być automatycznie generowana przez kompilator, ponieważ jest niejednoznaczna w przypadku zmiany kolejności instrukcji w takiej operacji w celu uzyskania tego samego efektu.</span><span class="sxs-lookup"><span data-stu-id="fc218-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="fc218-146">Definiowanie nowych funkcji</span><span class="sxs-lookup"><span data-stu-id="fc218-146">Defining New Functions</span></span>

<span data-ttu-id="fc218-147">Funkcja Q # umożliwia także Definiowanie *funkcji*, które różnią się od operacji w tym, że nie mogą mieć żadnych efektów poza obliczaniem wartości wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="fc218-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="fc218-148">W szczególności funkcje nie mogą wywoływać operacji, działać na qubits, przykładowe liczby losowe lub w inny sposób zależały od stanu poza wartością wejściową do funkcji.</span><span class="sxs-lookup"><span data-stu-id="fc218-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="fc218-149">W związku z tym funkcje Q # są *czyste*, w tym przypadku zawsze mapują te same wartości wejściowe na te same wartości wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="fc218-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="fc218-150">Dzięki temu kompilator Q # może bezpiecznie zmienić kolejność i czas wywoływania funkcji podczas generowania specjalizacji operacji.</span><span class="sxs-lookup"><span data-stu-id="fc218-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="fc218-151">Definiowanie funkcji działa podobnie do definiowania operacji, z tą różnicą, że dla funkcji nie można definiować podległych lub kontrolowanych specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="fc218-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="fc218-152">Na wystąpienie:</span><span class="sxs-lookup"><span data-stu-id="fc218-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="fc218-153">Za każdym razem, gdy jest to możliwe, warto napisać klasyczną logikę pod kątem funkcji, a nie operacji, dzięki czemu można łatwiej używać jej w ramach operacji.</span><span class="sxs-lookup"><span data-stu-id="fc218-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="fc218-154">Jeśli firma Microsoft zapisała `Square` w ramach operacji, na przykład kompilator nie może zagwarantować, że wywołanie go z tym samym danymi wejściowymi będzie spójnie generować te same dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="fc218-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="fc218-155">Aby podkreślić różnicę między funkcjami i operacjami, należy wziąć pod uwagę problem z próbkami klasycznymi losowych, z poziomu operacji Q #:</span><span class="sxs-lookup"><span data-stu-id="fc218-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="fc218-156">Za każdym razem, gdy `U` jest wywoływana, będzie ona mieć inną akcję na `target`.</span><span class="sxs-lookup"><span data-stu-id="fc218-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="fc218-157">W szczególności kompilator nie może zagwarantować, że w przypadku dodania do `U`deklaracji specjalizacji `adjoint auto`, `U(target); Adjoint U(target);` działa jako tożsamość (to oznacza, że jako No-op).</span><span class="sxs-lookup"><span data-stu-id="fc218-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="fc218-158">Jest to naruszone w przypadku [wektorów i macierzy](xref:microsoft.quantum.concepts.vectors), co pozwala na automatyczne generowanie podległych specjalizacji w operacji, w których wywołano operację, <xref:microsoft.quantum.math.randomreal> spowodują przerwanie gwarancji dostarczonych przez kompilator ; <xref:microsoft.quantum.math.randomreal> to operacja, dla której nie istnieje przyległych lub kontrolowana wersja.</span><span class="sxs-lookup"><span data-stu-id="fc218-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="fc218-159">Z drugiej strony, zezwolenie na wywołania funkcji, takie jak `Square`, jest bezpieczne, w tym przypadku kompilator może mieć pewność, że tylko dane wejściowe są zachowywane `Square` w celu zapewnienia stabilności danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="fc218-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="fc218-160">W ten sposób izolowanie możliwie największej logiki w ramach funkcji pozwala łatwo ponownie wykorzystać tę logikę w innych funkcjach i operacjach.</span><span class="sxs-lookup"><span data-stu-id="fc218-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="fc218-161">Przepływ sterowania</span><span class="sxs-lookup"><span data-stu-id="fc218-161">Control Flow</span></span>

<span data-ttu-id="fc218-162">W ramach operacji lub funkcji każda instrukcja jest wykonywana w kolejności, podobnie jak w przypadku najczęściej używanych języków klasycznych.</span><span class="sxs-lookup"><span data-stu-id="fc218-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="fc218-163">Ten przepływ sterowania można jednak zmodyfikować na trzy różne sposoby:</span><span class="sxs-lookup"><span data-stu-id="fc218-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="fc218-164">Instrukcje `if`</span><span class="sxs-lookup"><span data-stu-id="fc218-164">`if` Statements</span></span>
- <span data-ttu-id="fc218-165">Pętle `for`</span><span class="sxs-lookup"><span data-stu-id="fc218-165">`for` Loops</span></span>
- <span data-ttu-id="fc218-166">`repeat`-`until` pętle</span><span class="sxs-lookup"><span data-stu-id="fc218-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="fc218-167">Wykorzystamy z tej ostatniej dyskusji, dopóki nie będziemy omawiać powtarzających się obwodów [(jednostek ru)](xref:microsoft.quantum.techniques.qubits#measurements) .</span><span class="sxs-lookup"><span data-stu-id="fc218-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="fc218-168">Konstrukcje `if` i `for` sterowania przepływem, jednak należy pamiętać o najbardziej znanym znaczeniu dla większości klasycznych języków programowania.</span><span class="sxs-lookup"><span data-stu-id="fc218-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="fc218-169">W szczególności instrukcja `if` może wykonać jedną lub więcej instrukcji `elif` i może kończyć się `else`:</span><span class="sxs-lookup"><span data-stu-id="fc218-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="fc218-170">Podobnie pętle `for` wskazują iterację w zakresie liczb całkowitych lub na elementy tablicy:</span><span class="sxs-lookup"><span data-stu-id="fc218-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="fc218-171">Należy pamiętać, że `for` pętle i instrukcje `if` mogą być również używane w operacjach, dla których specjalizacje są generowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="fc218-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="fc218-172">W takim przypadku sąsiadująca pętla `for` odwraca kierunek i przyjmuje sąsiadujące poszczególne iteracje.</span><span class="sxs-lookup"><span data-stu-id="fc218-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="fc218-173">Ta zasada jest zgodna z zasadą "buty i-SOCKS": Jeśli chcesz cofnąć umieszczanie w ramach SOCKS, a następnie odbuty, musisz cofnąć umieszczanie na butów, a następnie cofnąć umieszczenie w usłudze SOCKS.</span><span class="sxs-lookup"><span data-stu-id="fc218-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="fc218-174">Decidedly mniej dobrze, aby wypróbować i podjąć Twoje SOCKS, gdy będziesz nadal korzystać z swoich oddziałów.</span><span class="sxs-lookup"><span data-stu-id="fc218-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="fc218-175">Operacje i funkcje jako wartości pierwszej klasy</span><span class="sxs-lookup"><span data-stu-id="fc218-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="fc218-176">Jedną z kluczowych technik z przyczyn dotyczących przepływu sterowania i klasycznej logiki przy użyciu funkcji, a nie operacji, jest wykorzystanie tych operacji i funkcji w Q # są *pierwszą klasą*.</span><span class="sxs-lookup"><span data-stu-id="fc218-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="fc218-177">Oznacza to, że są to poszczególne wartości w języku we własnym zakresie.</span><span class="sxs-lookup"><span data-stu-id="fc218-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="fc218-178">Na przykład, poniżej jest doskonale prawidłowy kod Q #, w przypadku niewielkiego pośrednika:</span><span class="sxs-lookup"><span data-stu-id="fc218-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="fc218-179">Wartość zmiennej `ourH` w powyższym fragmencie kodu jest wtedy operacją <xref:microsoft.quantum.intrinsic.h>, dzięki czemu możemy wywołać tę wartość, podobnie jak każda inna operacja.</span><span class="sxs-lookup"><span data-stu-id="fc218-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="fc218-180">Dzięki temu możemy pisać operacje, które przyjmują operacje w ramach danych wejściowych, tworząc koncepcje przepływu sterowania wyższego rzędu.</span><span class="sxs-lookup"><span data-stu-id="fc218-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="fc218-181">Na przykład możemy Wyobraź sobie, że chcemy "kwadratowych" operacji, stosując ją dwa razy do tego samego elementu docelowego qubit.</span><span class="sxs-lookup"><span data-stu-id="fc218-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="fc218-182">W tym przykładzie strzałka `=>`, która pojawia się w typie `(Qubit => Unit)` oznacza, że pole wejściowe `op` jest operacją, która przyjmuje jako dane wejściowe typ `Qubit` i tworzy pustą krotkę jako wyjściową.</span><span class="sxs-lookup"><span data-stu-id="fc218-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="fc218-183">Dodatkowo określimy cechy tego typu operacji, które zawierają informacje o tym, które funktory są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="fc218-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="fc218-184">Operacja typu `(Qubit => Unit)` nie obsługuje `Adjoint` ani `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="fc218-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="fc218-185">Jeśli chcemy wskazać, że operacja tego typu musi obsługiwać np. `Adjoint` Funktor, musimy zadeklarować ją jako sąsiedniej.</span><span class="sxs-lookup"><span data-stu-id="fc218-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="fc218-186">Jest to realizowane przy użyciu adnotacji `is Adj` do typu.</span><span class="sxs-lookup"><span data-stu-id="fc218-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="fc218-187">Podobnie `(Qubit => Unit is Ctl)` oznacza, że operacja tego typu obsługuje `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="fc218-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="fc218-188">Zapoznajemy się z tym tematem, aby poznać [typy w Q #] (linki XREF: Microsoft. Quantum. Language. Type-model) bardziej ogólnie.</span><span class="sxs-lookup"><span data-stu-id="fc218-188">We will explore this further when we discuss [types in Q#] (xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="fc218-189">Teraz przykro, że możemy również zwrócić operacje w ramach danych wyjściowych, aby można było izolować niektóre rodzaje klasycznej logiki warunkowej jako klasyczną funkcję, która zwraca opis programu Quantum w postaci operacji.</span><span class="sxs-lookup"><span data-stu-id="fc218-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="fc218-190">W ramach prostego przykładu Rozważmy przykład teleportowego, w którym strona otrzymująca dwubitowy klasyczny komunikat musi użyć komunikatu, aby zdekodować qubit w odpowiedni stan teleportowy.</span><span class="sxs-lookup"><span data-stu-id="fc218-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="fc218-191">Możemy napisać to pod względem funkcji, która pobiera te dwa klasyczne bity i zwraca odpowiednią operację dekodowania.</span><span class="sxs-lookup"><span data-stu-id="fc218-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="fc218-192">Ta nowa funkcja jest w rzeczywistości funkcją, w tym przypadku, gdy wywołamy ją z tymi samymi wartościami `hereBit` i `thereBit`, zawsze będziemy wrócić do tej samej operacji.</span><span class="sxs-lookup"><span data-stu-id="fc218-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="fc218-193">W związku z tym dekoder może być bezpiecznie uruchamiany wewnątrz operacji bez powodowania, jak logika dekodowania współdziała z definicjami różnych specjalizacji operacji.</span><span class="sxs-lookup"><span data-stu-id="fc218-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="fc218-194">Oznacza to, że w funkcji jest izolowana klasyczna logika, która gwarantuje, że wywołanie funkcji można zmienić przy użyciu impunity, tak długo, jak dane wejściowe są zachowywane.</span><span class="sxs-lookup"><span data-stu-id="fc218-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="fc218-195">Możemy również traktować funkcje jako wartości pierwszej klasy, ponieważ w przypadku omawianych [typów operacji i funkcji](#operations-and-functions-as-first-class-values)zostanie wyświetlony bardziej szczegółowy.</span><span class="sxs-lookup"><span data-stu-id="fc218-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="fc218-196">Częściowo stosowane operacje i funkcje</span><span class="sxs-lookup"><span data-stu-id="fc218-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="fc218-197">Możemy znacznie bardziej robić dzięki funkcjom, które zwracają operacje przy użyciu *częściowej aplikacji*, w którym możemy dostarczyć co najmniej jedną część danych wejściowych do funkcji lub operacji bez jej rzeczywistego wywoływania.</span><span class="sxs-lookup"><span data-stu-id="fc218-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="fc218-198">Na przykład odwołując się do powyższego przykładu `ApplyTwice`, możemy wskazać, że nie chcemy określać, od razu, do czego qubit operacja wejścia powinna być stosowana:</span><span class="sxs-lookup"><span data-stu-id="fc218-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="fc218-199">W takim przypadku zmienna lokalna `twiceOp` przechowuje częściowo zastosowana operacja `ApplyTwice(op, _)`, w przypadku których części danych wejściowych, które nie zostały jeszcze określone, są wskazywane przez `_`.</span><span class="sxs-lookup"><span data-stu-id="fc218-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="fc218-200">Gdy faktycznie wywołamy `twiceOp` w następnym wierszu, przekazujemy jako dane wejściowe do operacji częściowo zastosowanej wszystkie pozostałe części danych wejściowych do oryginalnej operacji.</span><span class="sxs-lookup"><span data-stu-id="fc218-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="fc218-201">W związku z tym Powyższy fragment kodu jest efektywnie identyczny z nazwą, która jest bezpośrednio wywoływana `ApplyTwice(op, target)`, a następnie Zapisz, że wprowadziliśmy nową zmienną lokalną, która pozwala na opóźnienie wywołania podczas udostępniania niektórych części danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="fc218-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="fc218-202">Ponieważ operacja, która została częściowo zastosowana, nie jest faktycznie wywoływana do momentu udostępnienia całego danych wejściowych, możemy bezpiecznie zastosować operacje nawet z poziomu funkcji.</span><span class="sxs-lookup"><span data-stu-id="fc218-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="fc218-203">W zasadzie klasyczna logika w ramach `SquareOperation` może być znacznie większa, ale nadal odizolowana od pozostałej części operacji przez gwarancje, które kompilator może zaoferować na temat funkcji.</span><span class="sxs-lookup"><span data-stu-id="fc218-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="fc218-204">Ta metoda zostanie użyta w całej standardowej bibliotece Q # do wyrażenia klasycznego przepływu sterowania w sposób, który może być łatwo używany w ramach programów Quantum.</span><span class="sxs-lookup"><span data-stu-id="fc218-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>

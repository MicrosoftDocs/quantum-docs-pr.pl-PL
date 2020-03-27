---
title: 'Struktura pliku Q #'
description: 'Dowiedz się, jak struktury przestrzeni nazw, operacji, funkcji i deklaracji typu zdefiniowanego przez użytkownika w programie Q # programy i biblioteki.'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 96de062bc6ce4edf94520bec449e8d95259c0f5c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320761"
---
# <a name="file-structure"></a><span data-ttu-id="5323c-103">Struktura plików</span><span class="sxs-lookup"><span data-stu-id="5323c-103">File Structure</span></span>

<span data-ttu-id="5323c-104">Plik Q # składa się z sekwencji nazw deklaracji.</span><span class="sxs-lookup"><span data-stu-id="5323c-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="5323c-105">Każda deklaracja przestrzeni nazw zawiera deklaracje dla typów, operacji i funkcji zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5323c-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="5323c-106">Deklaracja przestrzeni nazw może zawierać dowolną liczbę typów deklaracji i w dowolnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="5323c-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="5323c-107">Jedynym tekstem, który może występować poza deklaracją przestrzeni nazw, jest komentarz.</span><span class="sxs-lookup"><span data-stu-id="5323c-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="5323c-108">W szczególności Komentarze do dokumentacji dla przestrzeni nazw poprzedzają deklarację.</span><span class="sxs-lookup"><span data-stu-id="5323c-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="5323c-109">Deklaracje przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="5323c-109">Namespace Declarations</span></span>

<span data-ttu-id="5323c-110">Plik Q # zazwyczaj ma dokładnie jedną deklarację przestrzeni nazw, ale może mieć wartość None (i być pusty lub zawierać komentarze) lub może zawierać wiele przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="5323c-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="5323c-111">Deklaracje przestrzeni nazw nie mogą być zagnieżdżane.</span><span class="sxs-lookup"><span data-stu-id="5323c-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="5323c-112">Ta sama przestrzeń nazw może być zadeklarowana w wielu plikach Q #, które są kompilowane razem, o ile nie istnieją deklaracje typu, operacji lub funkcji o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="5323c-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="5323c-113">W szczególności nie można zdefiniować tego samego typu w tej samej przestrzeni nazw w wielu plikach, nawet jeśli deklaracje są identyczne.</span><span class="sxs-lookup"><span data-stu-id="5323c-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="5323c-114">Deklaracja przestrzeni nazw składa się ze słowa kluczowego `namespace`, a po nim nazwy przestrzeni nazw, otwartego nawiasu `{`klamrowego, deklaracji zawartych w przestrzeni nazw i zamykającego nawiasu klamrowego `}`.</span><span class="sxs-lookup"><span data-stu-id="5323c-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="5323c-115">Nazwy przestrzeni nazw są zgodne ze wzorcem .NET sekwencji jednego lub więcej symboli dozwolonych, oddzielonych kropkami `.`.</span><span class="sxs-lookup"><span data-stu-id="5323c-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="5323c-116">Na przykład `MyQuantumStuff` i `Microsoft.Quantum.Canon` są prawidłowymi nazwami przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="5323c-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="5323c-117">Według Konwencji symbole w nazwie przestrzeni nazw są pisane wielkimi literami, ale nie jest to wymagane.</span><span class="sxs-lookup"><span data-stu-id="5323c-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="5323c-118">Deklaracje mogą pojawiać się w dowolnej kolejności w deklaracji przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="5323c-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="5323c-119">Odwołania do typów lub wartości, które zostały zadeklarowane w sposób nieokreślony w pliku, są rozwiązywane prawidłowo; nie ma potrzeby składania deklaracji typu, operacji lub funkcji przed odwołaniem do niej.</span><span class="sxs-lookup"><span data-stu-id="5323c-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="5323c-120">Otwarte dyrektywy</span><span class="sxs-lookup"><span data-stu-id="5323c-120">Open Directives</span></span>

<span data-ttu-id="5323c-121">W bloku przestrzeni nazw dyrektywa `open` może służyć do zaimportowania wszystkich typów i dożądanych nazw zdefiniowanych w określonym zakresie oraz odwoływania się do nich za pomocą niekwalifikowanej nazwy.</span><span class="sxs-lookup"><span data-stu-id="5323c-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="5323c-122">Taka `open` dyrektywa składa się ze słowa kluczowego `open`, a następnie przestrzeni nazw do otwarcia i kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="5323c-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="5323c-123">Na przykład,</span><span class="sxs-lookup"><span data-stu-id="5323c-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="5323c-124">Opcjonalnie, krótka nazwa otwartej przestrzeni nazw może być zdefiniowana, tak że wszystkie elementy z tej przestrzeni nazw mogą (i muszą) być kwalifikowane przez zdefiniowaną krótką nazwę.</span><span class="sxs-lookup"><span data-stu-id="5323c-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="5323c-125">Taka krótka nazwa jest definiowana przez dodanie słowa kluczowego `as`, po którym następuje żądana krótka nazwa przed średnikiem w dyrektywie `open`:</span><span class="sxs-lookup"><span data-stu-id="5323c-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="5323c-126">Wszystkie dyrektywy `open` muszą występować przed dowolnymi deklaracjami `function`, `operation`lub `newtype` w bloku przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="5323c-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="5323c-127">Dyrektywa `open` ma zastosowanie do całego bloku przestrzeni nazw w pliku.</span><span class="sxs-lookup"><span data-stu-id="5323c-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="5323c-128">Deklaracje typu zdefiniowanego przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="5323c-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="5323c-129">Polecenie Q # zapewnia użytkownikom sposób deklarowania nowych typów zdefiniowanych przez użytkownika, zgodnie z opisem w sekcji [model typu Q #](xref:microsoft.quantum.language.type-model) .</span><span class="sxs-lookup"><span data-stu-id="5323c-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="5323c-130">Typy zdefiniowane przez użytkownika są różne, nawet jeśli typy podstawowe są identyczne.</span><span class="sxs-lookup"><span data-stu-id="5323c-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="5323c-131">W szczególności nie istnieje Automatyczna konwersja między wartościami dwóch typów zdefiniowanych przez użytkownika, nawet jeśli typy bazowe są identyczne.</span><span class="sxs-lookup"><span data-stu-id="5323c-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="5323c-132">Deklaracja typu zdefiniowanego przez użytkownika składa się ze słowa kluczowego `newtype`, po którym następuje nazwa typu zdefiniowanego przez użytkownika, `=`, prawidłowej specyfikacji typu i kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="5323c-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="5323c-133">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="5323c-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="5323c-134">Każdy plik źródłowy Q # może deklarować dowolną liczbę typów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5323c-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="5323c-135">Nazwy typów muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktów z nazwami operacji i funkcji.</span><span class="sxs-lookup"><span data-stu-id="5323c-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="5323c-136">Nie można definiować zależności cykliczne między typami zdefiniowanymi przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5323c-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="5323c-137">W takim przypadku typy cykliczne nie są w tym przypadku dostępne w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="5323c-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="5323c-138">Deklaracje operacji</span><span class="sxs-lookup"><span data-stu-id="5323c-138">Operation Declarations</span></span>

<span data-ttu-id="5323c-139">Operacje są rdzeniem Q #, w przybliżeniu analogiczne do funkcji w innych językach.</span><span class="sxs-lookup"><span data-stu-id="5323c-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="5323c-140">Każdy plik źródłowy Q # może definiować dowolną liczbę operacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="5323c-141">Nazwy operacji muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktów z nazwami typów i funkcji.</span><span class="sxs-lookup"><span data-stu-id="5323c-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="5323c-142">Deklaracje operacji składają się ze słowa kluczowego `operation`, po którym występuje symbol, który jest nazwą operacji, spójna kolekcja identyfikatorów, która definiuje argumenty do operacji, dwukropek `:`, adnotację typu opisującą typ wyniku operacji, opcjonalnie adnotację z charakterystykami operacji, otwierającą nawias `{`klamrowy, treść deklaracji operacji i końcowy nawias zamykający `}`.</span><span class="sxs-lookup"><span data-stu-id="5323c-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="5323c-143">Treść deklaracji operacji obejmuje domyślną implementację lub listę specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="5323c-144">Implementację domyślną można określić bezpośrednio w deklaracji, jeśli tylko implementacja specjalizacji treści domyślnej musi być określona jawnie.</span><span class="sxs-lookup"><span data-stu-id="5323c-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="5323c-145">W takim przypadku Adnotacja z charakterystyką operacji w deklaracji jest przydatna do zapewnienia, że kompilator automatycznie generuje inne specjalizacje na podstawie domyślnej implementacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="5323c-146">Na przykład</span><span class="sxs-lookup"><span data-stu-id="5323c-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="5323c-147">Charakterystyki operacji definiują, jakie rodzaje funktory można stosować do zadeklarowanej operacji oraz jaki ma wpływ.</span><span class="sxs-lookup"><span data-stu-id="5323c-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="5323c-148">Jeśli operacja implementuje transformację jednostkową, można zdefiniować sposób działania operacji przy *adjointed* lub *kontrolowanej*.</span><span class="sxs-lookup"><span data-stu-id="5323c-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="5323c-149">Istnienie tych specjalizacji może być zadeklarowane jako część podpisu operacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="5323c-150">Odpowiednia implementacja dla każdej takiej niejawnie zadeklarowanej specjalizacji jest generowana przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="5323c-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="5323c-151">W powyższym przykładzie, współdzielone, kontrolowane i kontrolowane specjalizacje są generowane przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="5323c-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="5323c-152">W przypadku, gdy implementacja nie może zostać wygenerowana przez kompilator, można ją jawnie określić.</span><span class="sxs-lookup"><span data-stu-id="5323c-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="5323c-153">Takie jawne deklaracje specjalizacji mogą składać się z odpowiedniej dyrektywy generacji, która wyjaśnia, w jaki sposób można skompilować konkretną specjalizację lub implementację zdefiniowaną przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5323c-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="5323c-154">Kod w `PrepareEntangledPair` powyżej na przykład jest odpowiednikiem poniższego kodu zawierającego jawne deklaracje specjalizacji:</span><span class="sxs-lookup"><span data-stu-id="5323c-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="5323c-155">Słowo kluczowe `auto` wskazuje, że kompilator powinien określić sposób generowania implementacji specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="5323c-156">Jeśli kompilator nie może wygenerować implementacji dla określonej specjalizacji bez dalszych instrukcji, takich jak dokładniejsza dyrektywa generacji — lub jeśli można podać bardziej wydajną implementację, implementacja może być również zdefiniowana ręcznie.</span><span class="sxs-lookup"><span data-stu-id="5323c-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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

<span data-ttu-id="5323c-157">W powyższym przykładzie `adjoint invert;` wskazuje, że jest generowana podległych specjalizacji, przez odwrócenie implementacji treści, a `controlled adjoint invert;` wskazuje, że kontrolowana podległych specjalizacji ma być generowana przez odwrócenie danej implementacji kontrolowanej specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="5323c-158">Aby można było wykonać operację do obsługi aplikacji `Adjoint` i/lub `Controlled` Funktor, jego typ zwracany musi być `Unit`.</span><span class="sxs-lookup"><span data-stu-id="5323c-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="5323c-159">Jawne deklaracje specjalizacji</span><span class="sxs-lookup"><span data-stu-id="5323c-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="5323c-160">Operacje Q # mogą zawierać następujące jawne deklaracje specjalizacji:</span><span class="sxs-lookup"><span data-stu-id="5323c-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="5323c-161">Specjalizacja `body` określa implementację operacji bez zastosowania funktory.</span><span class="sxs-lookup"><span data-stu-id="5323c-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="5323c-162">Specjalizacja `adjoint` określa implementację operacji z zastosowaniem `Adjoint` Funktor.</span><span class="sxs-lookup"><span data-stu-id="5323c-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="5323c-163">Specjalizacja `controlled` określa implementację operacji z zastosowaniem `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="5323c-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="5323c-164">Specjalizacja `controlled adjoint` określa implementację operacji z zastosowaniem zarówno `Adjoint`, jak i `Controlled` funktory.</span><span class="sxs-lookup"><span data-stu-id="5323c-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="5323c-165">Ta specjalizacja może być również nazywana `adjoint controlled`, ponieważ dwie funktory.</span><span class="sxs-lookup"><span data-stu-id="5323c-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="5323c-166">Specjalizacja operacji składa się z tagu specjalizacji (np. `body`lub `adjoint`itp.), po którym następuje jedno z:</span><span class="sxs-lookup"><span data-stu-id="5323c-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="5323c-167">Jawna deklaracja opisana poniżej.</span><span class="sxs-lookup"><span data-stu-id="5323c-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="5323c-168">Dyrektywa, która informuje kompilator, jak generować specjalizację, jeden z:</span><span class="sxs-lookup"><span data-stu-id="5323c-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="5323c-169">`intrinsic`, co oznacza, że specjalizacja jest udostępniana przez maszynę docelową.</span><span class="sxs-lookup"><span data-stu-id="5323c-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="5323c-170">`distribute`, które mogą być używane z specjalizacjami `controlled` i `controlled adjoint`.</span><span class="sxs-lookup"><span data-stu-id="5323c-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="5323c-171">Gdy jest używany z `controlled`, wskazuje, że kompilator powinien obliczyć specjalizację, stosując `Controlled` do wszystkich operacji w `body`.</span><span class="sxs-lookup"><span data-stu-id="5323c-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="5323c-172">Gdy jest używany z `controlled adjoint`, wskazuje, że kompilator powinien obliczyć specjalizację, stosując `Controlled` do wszystkich operacji w `adjoint` specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="5323c-173">`invert`, który wskazuje, że kompilator powinien obliczyć `adjoint` specjalizacji przez odwrócenie `body`, czyli odwracanie kolejności operacji i stosowanie sąsiadujących do nich.</span><span class="sxs-lookup"><span data-stu-id="5323c-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="5323c-174">Gdy jest używany z `adjoint controlled`, oznacza to, że kompilator powinien obliczyć specjalizację, odwracając specjalizację `controlled`.</span><span class="sxs-lookup"><span data-stu-id="5323c-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="5323c-175">`self`w celu wskazania, że specjalizacja jest taka sama jak specjalizacja `body`.</span><span class="sxs-lookup"><span data-stu-id="5323c-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="5323c-176">Jest to dozwolone w przypadku specjalizacji `adjoint` i `adjoint controlled`.</span><span class="sxs-lookup"><span data-stu-id="5323c-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="5323c-177">W przypadku `adjoint controlled``self` oznacza, że specjalizacja `adjoint controlled` jest taka sama jak specjalizacja `controlled`.</span><span class="sxs-lookup"><span data-stu-id="5323c-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="5323c-178">`auto`, aby wskazać, że kompilator powinien wybrać odpowiednią dyrektywę, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5323c-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="5323c-179">nie można użyć `auto` dla specjalizacji `body`.</span><span class="sxs-lookup"><span data-stu-id="5323c-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="5323c-180">Dyrektywy i `auto` wszystkie wymagają zamykającego średnika `;`.</span><span class="sxs-lookup"><span data-stu-id="5323c-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="5323c-181">Dyrektywa `auto` jest rozpoznawana jako następująca dyrektywa generacji, jeśli podano jawną deklarację `body`:</span><span class="sxs-lookup"><span data-stu-id="5323c-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="5323c-182">Specjalizacja `adjoint` jest generowana zgodnie z dyrektywą `invert`.</span><span class="sxs-lookup"><span data-stu-id="5323c-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="5323c-183">Specjalizacja `controlled` jest generowana zgodnie z dyrektywą `distribute`.</span><span class="sxs-lookup"><span data-stu-id="5323c-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="5323c-184">Specjalizacja `adjoint controlled` jest generowana zgodnie z dyrektywą `invert`, jeśli jawna Deklaracja dla `controlled` jest podano, ale nie dla `adjoint`, i `distribute` w przeciwnym razie.</span><span class="sxs-lookup"><span data-stu-id="5323c-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="5323c-185">Jeśli operacja jest samodzielna, należy jawnie określić podległych lub kontrolowanej specjalizacji za pośrednictwem dyrektywy Generation `self`, aby umożliwić kompilatorowi użycie tych informacji do celów optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="5323c-186">Deklaracja specjalizacji, która zawiera implementację zdefiniowaną przez użytkownika, składa się z krotki argumentu, po której następuje blok instrukcji z kodem Q #, który implementuje specjalizację.</span><span class="sxs-lookup"><span data-stu-id="5323c-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="5323c-187">Na liście argumentów `...` jest używany do reprezentowania argumentów zadeklarowanych dla operacji jako całości.</span><span class="sxs-lookup"><span data-stu-id="5323c-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="5323c-188">Dla `body` i `adjoint`lista argumentów powinna być zawsze `(...)`; dla `controlled` i `adjoint controlled`lista argumentów powinna być symbolem, który reprezentuje tablicę kontrolki qubits, a następnie `...`ujętą w nawiasy. na przykład `(controls,...)`.</span><span class="sxs-lookup"><span data-stu-id="5323c-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="5323c-189">Jeśli co najmniej jedna specjalizacja poza treścią domyślną musi być zadeklarowana w sposób jawny, implementacja treści domyślnej musi być opakowana do odpowiedniej deklaracji specjalizacji:</span><span class="sxs-lookup"><span data-stu-id="5323c-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="adjoint"></a><span data-ttu-id="5323c-190">Sąsiadująco</span><span class="sxs-lookup"><span data-stu-id="5323c-190">Adjoint</span></span>

<span data-ttu-id="5323c-191">Sąsiadująca operacja określa sposób, w jaki jest zaimplementowana złożona funkcja transpozycji sprzężonej operacji. oznacza to, jak działa operacja, gdy "Uruchom w odwrotnie".</span><span class="sxs-lookup"><span data-stu-id="5323c-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="5323c-192">Jest to możliwe, aby określić operację niesąsiadującą; na przykład operacje pomiarów nie mają sąsiadujących, ponieważ nie są odwracalna.</span><span class="sxs-lookup"><span data-stu-id="5323c-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="5323c-193">Operacja obsługuje `Adjoint` Funktor, jeśli jej deklaracja zawiera niejawną lub jawną deklarację specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="5323c-194">Jawne zadeklarowane, kontrolowane podległych specjalizacji oznacza istnienie podległych specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="5323c-195">Dla operacji, której treść zawiera pętle REPEAT-until-Success, Set instrukcje, pomiary, instrukcje Return lub wywołania do innych operacji, które nie obsługują `Adjoint` Funktor, Autogenerowanie podległych specjalizacji po `invert` lub `auto` dyrektywie nie jest możliwe.</span><span class="sxs-lookup"><span data-stu-id="5323c-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="5323c-196">Kontrolowane</span><span class="sxs-lookup"><span data-stu-id="5323c-196">Controlled</span></span>

<span data-ttu-id="5323c-197">Kontrolowana wersja operacji określa, w jaki sposób jest zaimplementowana przeprowadzona przez Quantum wersja operacji, czyli sposób działania operacji po zastosowaniu warunku na stanie rejestru Quantum.</span><span class="sxs-lookup"><span data-stu-id="5323c-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="5323c-198">Dokładniejszy opis znajduje się w sekcji [kontrolowanej](xref:microsoft.quantum.language.type-model#controlled) .</span><span class="sxs-lookup"><span data-stu-id="5323c-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="5323c-199">Istnieje możliwość określenia operacji bez kontrolowanej wersji; na przykład operacje pomiarów nie mają kontrolowanej wersji, ponieważ nie można ich kontrolować.</span><span class="sxs-lookup"><span data-stu-id="5323c-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="5323c-200">Operacja obsługuje `Controlled` Funktor if i tylko wtedy, gdy jej deklaracja zawiera niejawną lub jawną deklarację kontrolowanej specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="5323c-201">Jawne zadeklarowane, kontrolowane podległych specjalizacji implikuje istnienie kontrolowanej specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="5323c-202">Dla operacji, której treść zawiera wywołania do innych operacji, które nie obsługują `Controlled` Funktor, nie jest możliwe wygenerowanie kontrolowanej specjalizacji po dyrektywie `distribute` lub `auto`.</span><span class="sxs-lookup"><span data-stu-id="5323c-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="5323c-203">Kontrolowane sąsiadująco</span><span class="sxs-lookup"><span data-stu-id="5323c-203">Controlled Adjoint</span></span>

<span data-ttu-id="5323c-204">Kontrolowana sąsiadująca wersja operacji określa, jak jest zaimplementowana przeprowadzona przez Quantum wersja sąsiadującej operacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="5323c-205">Istnieje możliwość określenia operacji bez kontrolowanej wersji sąsiadującej; na przykład operacje pomiarów nie mają kontrolowanej wersji sąsiadującej, ponieważ nie są ani odwracalnae ani nie są dostępne.</span><span class="sxs-lookup"><span data-stu-id="5323c-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="5323c-206">Kontrolowana podległych specjalizacji dla operacji musi istnieć, jeśli i tylko wtedy, gdy istnieje zarówno przyległych, jak i kontrolowanych specjalizacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="5323c-207">W takim przypadku istnienie kontrolowanej specjalizacji jest wnioskowane, a odpowiednia specjalizacja jest generowana przez kompilator, jeśli żadna implementacja nie została jawnie zdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="5323c-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="5323c-208">W przypadku operacji, której treść zawiera wywołania do innych operacji, które nie mają kontrolowanej sąsiedniej wersji, należy ją wygenerować przy użyciu autospecjalizacji następującego po `invert`, `distribute` lub `auto` dyrektywie nie jest możliwe.</span><span class="sxs-lookup"><span data-stu-id="5323c-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="5323c-209">Przykłady</span><span class="sxs-lookup"><span data-stu-id="5323c-209">Examples</span></span>

<span data-ttu-id="5323c-210">Deklaracja operacji może być prosta jako następująca, która definiuje pierwotną operację Pauli X:</span><span class="sxs-lookup"><span data-stu-id="5323c-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="5323c-211">Poniżej definiuje operację teleport.</span><span class="sxs-lookup"><span data-stu-id="5323c-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation PrepareEntangledPair (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        PrepareEntangledPair(target, ancilla);

        // Do the teleportation
        Adjoint PrepareEntangledPair(ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="5323c-212">Deklaracje funkcji</span><span class="sxs-lookup"><span data-stu-id="5323c-212">Function Declarations</span></span>

<span data-ttu-id="5323c-213">Funkcje są czysto klasycznymi procedurami w Q #.</span><span class="sxs-lookup"><span data-stu-id="5323c-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="5323c-214">Każdy plik źródłowy Q # może definiować dowolną liczbę funkcji.</span><span class="sxs-lookup"><span data-stu-id="5323c-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="5323c-215">Deklaracja funkcji składa się z `function`słowa kluczowego, po którym następuje symbol, który jest nazwą funkcji, krotką o identyfikatorze wpisanej, adnotacją typu opisującą typ zwracany funkcji i blokiem instrukcji opisującym implementację funkcji.</span><span class="sxs-lookup"><span data-stu-id="5323c-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="5323c-216">Blok instrukcji definiujący funkcję musi być ujęty w `{` i `}` jak każdy inny blok instrukcji.</span><span class="sxs-lookup"><span data-stu-id="5323c-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="5323c-217">Nazwy funkcji muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktu z nazwami operacji i typów.</span><span class="sxs-lookup"><span data-stu-id="5323c-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="5323c-218">Funkcje nie mogą przydzielić ani zażyczyć qubits lub wywoływać operacji.</span><span class="sxs-lookup"><span data-stu-id="5323c-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="5323c-219">Częściowe stosowanie operacji lub przekazywanie wartości z wartościami z określonym typem operacji jest dokładne.</span><span class="sxs-lookup"><span data-stu-id="5323c-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="5323c-220">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="5323c-220">For example,</span></span>

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


## <a name="internal-declarations"></a><span data-ttu-id="5323c-221">Deklaracje wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="5323c-221">Internal Declarations</span></span>

<span data-ttu-id="5323c-222">Typy zdefiniowane przez użytkownika, operacje i funkcje mogą być również deklarowane jako *wewnętrzne*.</span><span class="sxs-lookup"><span data-stu-id="5323c-222">User-defined types, operations, and functions can also be declared as *internal*.</span></span>
<span data-ttu-id="5323c-223">Oznacza to, że dostęp do nich można uzyskać tylko z poziomu projektu Q #, w którym są one zadeklarowane.</span><span class="sxs-lookup"><span data-stu-id="5323c-223">This means that they can only be accessed from within the Q# project that they are declared in.</span></span>
<span data-ttu-id="5323c-224">Gdy projekt jest używany jako odwołanie, wszystkie jego *publiczne* deklaracje (inne niż wewnętrzne) są udostępniane, ale próba użycia wewnętrznej deklaracji z innego projektu spowoduje wystąpienie błędu.</span><span class="sxs-lookup"><span data-stu-id="5323c-224">When a project is used as a reference, all of its *public* (non-internal) declarations are made available, but trying to use an internal declaration from another project will produce an error.</span></span>
<span data-ttu-id="5323c-225">Deklaracje wewnętrzne są przydatne do pisania kodu modularnego, który może być używany przez inne części projektu, ale nadal można je później zmienić bez przerywania innych projektów, które mogą być od niego zależne.</span><span class="sxs-lookup"><span data-stu-id="5323c-225">Internal declarations are useful for writing modular code that can be reused by other parts of your project, but still be changed later without breaking other projects that might depend on it.</span></span>

<span data-ttu-id="5323c-226">Wewnętrzny typ zdefiniowany przez użytkownika, operację lub funkcję można zadeklarować po prostu przez dodanie `internal` na początku deklaracji.</span><span class="sxs-lookup"><span data-stu-id="5323c-226">An internal user-defined type, operation, or function can be declared simply by adding `internal` at the beginning of the declaration.</span></span>
<span data-ttu-id="5323c-227">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="5323c-227">For example,</span></span>

```qsharp
internal newtype PairOfQubits = (Qubit, Qubit);

internal operation PrepareEntangledPair(pair : PairOfQubits) : Unit 
is Adj + Ctl {
    let (q1, q2) = pair!;
    H(q2);
    CNOT(q2, q1);
}

internal function DotProduct(a : Double[], b : Double[]) : Double {
    ...
}
```

> [!WARNING]
> <span data-ttu-id="5323c-228">Typy wewnętrzne zdefiniowane przez użytkownika mogą być używane tylko w sygnaturach lub typach bazowych, jeśli odpowiadające im typy lub typ zdefiniowany przez użytkownika są również wewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="5323c-228">Internal user-defined types can only be used in signatures or underlying types if the corresponding callable or user-defined type is also internal.</span></span>
> <span data-ttu-id="5323c-229">Na przykład jeśli istnieje typ zdefiniowany przez użytkownika `InternalOptions`, który został zadeklarowany za pomocą słowa kluczowego `internal`, następujące deklaracje spowodują błędy:</span><span class="sxs-lookup"><span data-stu-id="5323c-229">For example, if there is a user-defined type `InternalOptions` that was declared with the `internal` keyword, then the following declarations will result in errors:</span></span>
>
> ```qsharp
> // Error: Can't use InternalOptions as an output type of a public function.
> function DefaultInternalOptions() : InternalOptions { ... }
>
> // Error: Can't use InternalOptions as an item in a public user-defined type.
> newtype ExtendedOptions = (Internal : InternalOptions);
> ```

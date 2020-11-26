---
title: Q#Przewodnik po stylu Microsoft
description: Poznaj konwencje nazewnictwa, wprowadzania, dokumentacji i formatowania dla Q# programów i bibliotek.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
no-loc:
- Q#
- $$v
ms.openlocfilehash: cfc201a16b1b42c82314220f77ae120076291759
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231659"
---
# <a name="no-locq-style-guide"></a><span data-ttu-id="c3687-103">Q# Styl — Przewodnik</span><span class="sxs-lookup"><span data-stu-id="c3687-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="c3687-104">Konwencje ogólne</span><span class="sxs-lookup"><span data-stu-id="c3687-104">General Conventions</span></span> ##

<span data-ttu-id="c3687-105">Konwencje sugerowane w tym przewodniku mają na celu ułatwienie Q# odczytywania i zrozumienia programów oraz bibliotek.</span><span class="sxs-lookup"><span data-stu-id="c3687-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="c3687-106">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-106">Guidance</span></span>

<span data-ttu-id="c3687-107">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-107">We suggest:</span></span>

- <span data-ttu-id="c3687-108">Nigdy nie należy ignorować Konwencji, chyba że jest to celowe w celu zapewnienia bardziej czytelnego i zrozumiałego kodu dla użytkowników.</span><span class="sxs-lookup"><span data-stu-id="c3687-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="c3687-109">Konwencje nazewnictwa</span><span class="sxs-lookup"><span data-stu-id="c3687-109">Naming Conventions</span></span> ##

<span data-ttu-id="c3687-110">W ofercie zestawu Quantum Development Kit dążymy do nazywania funkcji i operacji, które ułatwiają deweloperom Quantum pisanie programów łatwych w odczytaniu i minimalizujących niespodziewane działanie.</span><span class="sxs-lookup"><span data-stu-id="c3687-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="c3687-111">Ważną częścią tego jest to, że w przypadku wybrania nazw dla funkcji, operacji i typów firma Microsoft ustala *słownictwo* , którego programiści używają do wyrażania koncepcji Quantum; Dzięki naszym wyborom firma Microsoft może powstrzymywać i utrudniać ich wysiłki w celu wyraźnego komunikowania się.</span><span class="sxs-lookup"><span data-stu-id="c3687-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="c3687-112">Dzięki temu firma Microsoft musi upewnić się, że wprowadzone nazwy oferują przejrzystość, a nie przesłania.</span><span class="sxs-lookup"><span data-stu-id="c3687-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="c3687-113">W tej sekcji szczegółowo opisano sposób, w jaki firma Microsoft spełnia ten obowiązek w zakresie jawnych wskazówek, które ułatwiają nam optymalne działanie Q# społeczności deweloperów.</span><span class="sxs-lookup"><span data-stu-id="c3687-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="c3687-114">Operacje i funkcje</span><span class="sxs-lookup"><span data-stu-id="c3687-114">Operations and Functions</span></span> ###

<span data-ttu-id="c3687-115">Jedną z najważniejszych rzeczy, które powinien określić nazwa, jest to, czy dany symbol reprezentuje funkcję czy operację.</span><span class="sxs-lookup"><span data-stu-id="c3687-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="c3687-116">Różnica między funkcjami i operacjami ma kluczowe znaczenie dla zrozumienie, jak działa blok kodu.</span><span class="sxs-lookup"><span data-stu-id="c3687-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="c3687-117">Aby komunikować się z rozróżnieniem między funkcjami i operacjami użytkowników, korzystamy z tych Q# modeli operacji Quantum przy użyciu efektów ubocznych.</span><span class="sxs-lookup"><span data-stu-id="c3687-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="c3687-118">Oznacza to, że operacja *wykonuje* coś.</span><span class="sxs-lookup"><span data-stu-id="c3687-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="c3687-119">Z kolei funkcje opisują relacje matematyczne między danymi.</span><span class="sxs-lookup"><span data-stu-id="c3687-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="c3687-120">Wyrażenie `Sin(PI() / 2.0)` *jest* `1.0` i oznacza brak informacji o stanie programu lub jego qubits.</span><span class="sxs-lookup"><span data-stu-id="c3687-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="c3687-121">Podsumowywanie, operacje wykonywane w trakcie wykonywania funkcji.</span><span class="sxs-lookup"><span data-stu-id="c3687-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="c3687-122">Takie rozróżnienie sugeruje, że nazwy operacji są nazywane czasownikami i funkcjami jako rzeczownikami.</span><span class="sxs-lookup"><span data-stu-id="c3687-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="c3687-123">Po zadeklarowaniu typu zdefiniowanego przez użytkownika, Nowa funkcja, która konstruuje wystąpienia tego typu jest niejawnie zdefiniowana w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="c3687-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="c3687-124">W tej perspektywie typy zdefiniowane przez użytkownika powinny być nazwane jako rzeczowniki, tak aby oba typy i funkcje konstruktora miały spójne nazwy.</span><span class="sxs-lookup"><span data-stu-id="c3687-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="c3687-125">W odpowiednim przypadku upewnij się, że nazwy operacji zaczynają się od czasowników jasno wskazujących wpływ operacji.</span><span class="sxs-lookup"><span data-stu-id="c3687-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="c3687-126">Przykład:</span><span class="sxs-lookup"><span data-stu-id="c3687-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="c3687-127">Jeden przypadek, który zachowuje szczególną wzmiankę, jest, gdy operacja wykonuje inną operację jako dane wejściowe i wywołuje ją.</span><span class="sxs-lookup"><span data-stu-id="c3687-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="c3687-128">W takich przypadkach Akcja podejmowana przez operację wejściową nie jest wyczyszczona, gdy została zdefiniowana operacja zewnętrzna, w taki sposób, że właściwe zlecenie nie jest natychmiast czyszczone.</span><span class="sxs-lookup"><span data-stu-id="c3687-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="c3687-129">Zalecamy zlecenie `Apply` , jak w `ApplyIf` , `ApplyToEach` i `ApplyToFirst` .</span><span class="sxs-lookup"><span data-stu-id="c3687-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="c3687-130">Inne zlecenia mogą być również przydatne w tym przypadku, jak w `IterateThroughCartesianPower` .</span><span class="sxs-lookup"><span data-stu-id="c3687-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="c3687-131">Czasownik</span><span class="sxs-lookup"><span data-stu-id="c3687-131">Verb</span></span> | <span data-ttu-id="c3687-132">Oczekiwany efekt</span><span class="sxs-lookup"><span data-stu-id="c3687-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="c3687-133">Zastosuj</span><span class="sxs-lookup"><span data-stu-id="c3687-133">Apply</span></span> | <span data-ttu-id="c3687-134">Operacja podana jako dane wejściowe jest wywoływana</span><span class="sxs-lookup"><span data-stu-id="c3687-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="c3687-135">Assert</span><span class="sxs-lookup"><span data-stu-id="c3687-135">Assert</span></span> | <span data-ttu-id="c3687-136">Hipoteza dotycząca wyniku możliwego pomiaru Quantum jest sprawdzana przez symulator</span><span class="sxs-lookup"><span data-stu-id="c3687-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="c3687-137">Szacowanie</span><span class="sxs-lookup"><span data-stu-id="c3687-137">Estimate</span></span> | <span data-ttu-id="c3687-138">Wartość jest zwracana, reprezentująca oszacowanie pobrane z co najmniej jednego pomiaru</span><span class="sxs-lookup"><span data-stu-id="c3687-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="c3687-139">Measure</span><span class="sxs-lookup"><span data-stu-id="c3687-139">Measure</span></span> | <span data-ttu-id="c3687-140">Pomiar Quantum jest wykonywany, a jego wynik jest zwracany do użytkownika</span><span class="sxs-lookup"><span data-stu-id="c3687-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="c3687-141">Przygotowywanie</span><span class="sxs-lookup"><span data-stu-id="c3687-141">Prepare</span></span> | <span data-ttu-id="c3687-142">Dana Rejestracja qubits jest inicjowana w określonym stanie</span><span class="sxs-lookup"><span data-stu-id="c3687-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="c3687-143">Przykład</span><span class="sxs-lookup"><span data-stu-id="c3687-143">Sample</span></span> | <span data-ttu-id="c3687-144">Wartość klasyczna jest zwracana losowo z pewnej dystrybucji</span><span class="sxs-lookup"><span data-stu-id="c3687-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="c3687-145">W przypadku funkcji sugerujemy unikanie korzystania z czasowników na rzecz typowych rzeczowników (Zobacz wskazówki dotyczące odpowiednich rzeczowników poniżej) lub przymiotników:</span><span class="sxs-lookup"><span data-stu-id="c3687-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="c3687-146">W szczególności we wszystkich przypadkach sugerujemy użycie Past participles, gdzie jest to konieczne, aby wskazać, że nazwa funkcji jest silnie połączona z akcją lub efektem ubocznym w innym miejscu w programie Quantum.</span><span class="sxs-lookup"><span data-stu-id="c3687-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="c3687-147">Na przykład  `ControlledOnInt` używa części Participle form czasownika "Control", aby wskazać, że funkcja działa jako przymiotnik, aby zmodyfikować jego argument.</span><span class="sxs-lookup"><span data-stu-id="c3687-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="c3687-148">Ta nazwa ma dodatkową korzyść do dopasowania semantyki wbudowanych `Controlled` Funktor, zgodnie z poniższym opisem poniżej.</span><span class="sxs-lookup"><span data-stu-id="c3687-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="c3687-149">Podobnie _rzeczowniki agentów_ mogą służyć do konstruowania nazw funkcji i UDT z nazw operacji, tak jak w przypadku nazwy `Encoder` typu UDT, która jest silnie skojarzona z `Encode` .</span><span class="sxs-lookup"><span data-stu-id="c3687-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="c3687-150">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="c3687-151">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-151">We suggest:</span></span>

- <span data-ttu-id="c3687-152">Użyj czasowników dla nazw operacji.</span><span class="sxs-lookup"><span data-stu-id="c3687-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="c3687-153">Używaj rzeczowników lub przymiotników dla nazw funkcji.</span><span class="sxs-lookup"><span data-stu-id="c3687-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="c3687-154">Używaj rzeczowników dla typów i atrybutów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c3687-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="c3687-155">Dla wszystkich nazwanych nazw można użyć `CamelCase` w silnym preferencjzie do `pascalCase` , `snake_case` , lub `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="c3687-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="c3687-156">W szczególności upewnij się, że nazwy, które można wywołać, zaczynają się wielką literą.</span><span class="sxs-lookup"><span data-stu-id="c3687-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="c3687-157">Dla wszystkich zmiennych lokalnych Użyj `pascalCase` w silnym preferencjzie do `CamelCase` , `snake_case` lub `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="c3687-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="c3687-158">W szczególności upewnij się, że zmienne lokalne zaczynają się od małych liter.</span><span class="sxs-lookup"><span data-stu-id="c3687-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="c3687-159">Unikaj używania podkreśleń `_` w nazwach funkcji i operacji. Jeśli potrzebujesz dodatkowych poziomów hierarchii, użyj przestrzeni nazw i aliasów przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="c3687-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-160">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-160">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="c3687-161">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c3687-161">Name</span></span> | <span data-ttu-id="c3687-162">Opis</span><span class="sxs-lookup"><span data-stu-id="c3687-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="c3687-163">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="c3687-164">Wyczyść użycie czasownika ("odbicie"), aby wskazać efekt operacji.</span><span class="sxs-lookup"><span data-stu-id="c3687-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="c3687-165">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="c3687-166">Użycie funkcji z sugestią typu rzeczownik zamiast operacji.</span><span class="sxs-lookup"><span data-stu-id="c3687-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="c3687-167">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="c3687-168">Użycie `snake_case` Q# notacji contravenes.</span><span class="sxs-lookup"><span data-stu-id="c3687-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="c3687-169">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="c3687-170">Użycie podkreśleń wewnętrznych dla nazwy operacji Q# notacji contravenes.</span><span class="sxs-lookup"><span data-stu-id="c3687-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="c3687-171">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="c3687-172">Użycie frazy rzeczownik sugeruje, że funkcja zwraca operację.</span><span class="sxs-lookup"><span data-stu-id="c3687-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="c3687-173">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="c3687-174">Wyczyść użycie rzeczownika ("fakt"), aby wskazać, że jest to funkcja, natomiast przymiotnik.</span><span class="sxs-lookup"><span data-stu-id="c3687-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="c3687-175">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="c3687-176">Użycie czasownika ("Get") sugeruje, że jest to operacja.</span><span class="sxs-lookup"><span data-stu-id="c3687-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="c3687-177">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="c3687-178">Użycie frazy rzeczownik jasno odwołuje się do wyniku wywołania konstruktora UDT.</span><span class="sxs-lookup"><span data-stu-id="c3687-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="c3687-179">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="c3687-180">Użycie wyrażenia orzeczenia sugeruje, że Konstruktor UDT jest operacją.</span><span class="sxs-lookup"><span data-stu-id="c3687-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="c3687-181">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="c3687-182">Użycie frazy rzeczownik komunikuje się z użyciem atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c3687-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="entry-points"></a><span data-ttu-id="c3687-183">Punkty wejścia</span><span class="sxs-lookup"><span data-stu-id="c3687-183">Entry Points</span></span>

<span data-ttu-id="c3687-184">Podczas definiowania punktu wejścia do Q# programu Q# kompilator rozpoznaje [ `@EntryPoint()` atrybut](xref:Microsoft.Quantum.Core.EntryPoint) , a nie wymaga, aby punkty wejścia miały określoną nazwę (np.: `main` , `Main` lub `__main__` ).</span><span class="sxs-lookup"><span data-stu-id="c3687-184">When defining an entry point into a Q# program, the Q# compiler recognizes the [`@EntryPoint()` attribute](xref:Microsoft.Quantum.Core.EntryPoint) rather requiring that entry points have a particular name (e.g.: `main`, `Main`, or `__main__`).</span></span>
<span data-ttu-id="c3687-185">Oznacza to, że w perspektywie Q# dewelopera punkty wejścia to zwykłe operacje opatrzone adnotacją `@EntryPoint()` .</span><span class="sxs-lookup"><span data-stu-id="c3687-185">That is, from the perspective of a Q# developer, entry points are ordinary operations annotated with `@EntryPoint()`.</span></span>
<span data-ttu-id="c3687-186">Ponadto Q# punkty wejścia mogą być punktami wejścia dla całej aplikacji (na przykład w Q# autonomicznych programach wykonywalnych) lub mogą być interfejsem między Q# programem i programem hosta dla aplikacji (tj. przy użyciu języka Q# Python lub .NET), w taki sposób, że nazwa "główna" może być myląca w przypadku zastosowania do Q# punktu wejścia.</span><span class="sxs-lookup"><span data-stu-id="c3687-186">Moreover, Q# entry points may be entry points for an entire application (for example, in Q# standalone executable programs), or may be an interface between a Q# program and the host program for an application (i.e.: when using Q# with Python or .NET), such that the name "main" could be misleading when applied to a Q# entry point.</span></span>

<span data-ttu-id="c3687-187">Sugerujemy używanie punktów wejścia nazw w celu odzwierciedlenia użycia `@EntryPoint()` atrybutu przy użyciu ogólnej porady dotyczącej nazw operacji wymienionych powyżej.</span><span class="sxs-lookup"><span data-stu-id="c3687-187">We suggest using naming entry points to reflect the use of the `@EntryPoint()` attribute by using the general advice for naming operations listed above.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="c3687-188">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-188">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="c3687-189">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-189">We suggest:</span></span>

- <span data-ttu-id="c3687-190">Nie należy nazywać operacji punktu wejścia jako "Main".</span><span class="sxs-lookup"><span data-stu-id="c3687-190">Do not name entry point operations as "main."</span></span>
- <span data-ttu-id="c3687-191">Wprowadzanie nazw operacji punktu wejścia jako zwykłych operacji.</span><span class="sxs-lookup"><span data-stu-id="c3687-191">Name entry point operations as ordinary operations.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-192">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-192">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="c3687-193">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c3687-193">Name</span></span> | <span data-ttu-id="c3687-194">Opis</span><span class="sxs-lookup"><span data-stu-id="c3687-194">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="c3687-195">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-195">☑</span></span> | `@EntryPoint() operation RunSimulation` | <span data-ttu-id="c3687-196">Jasno komunikuje przeznaczenie punktu wejścia przez nazwę operacji.</span><span class="sxs-lookup"><span data-stu-id="c3687-196">Clearly communicates purpose of entry point through operation name.</span></span> |
| <span data-ttu-id="c3687-197">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-197">☒</span></span> | <s>`@EntryPoint() operation Main`</s> | <span data-ttu-id="c3687-198">Użycie `Main` nie jest jasno przekazane do celów punktu wejścia i jest nadmiarowe z `@EntryPoint()` atrybutem.</span><span class="sxs-lookup"><span data-stu-id="c3687-198">Use of `Main` doesn't clearly communicate purpose of entry point, and is redundant with `@EntryPoint()` attribute.</span></span> |

<span data-ttu-id="c3687-199">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c3687-199">\*\*_</span></span>

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="c3687-200">Skróty i skróty</span><span class="sxs-lookup"><span data-stu-id="c3687-200">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="c3687-201">Powyższe porady nie poprzednia, istnieje wiele form skróconych, które widzą typowe i powszechne użycie w ramach przetwarzania Quantum.</span><span class="sxs-lookup"><span data-stu-id="c3687-201">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="c3687-202">Sugerujemy używanie istniejących i wspólnych skrótów, gdzie istnieje, szczególnie w przypadku operacji, które są wewnętrzne dla działania maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="c3687-202">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="c3687-203">Na przykład wybieramy nazwę `X` zamiast `ApplyX` , a `Rz` nie `RotateAboutZ` .</span><span class="sxs-lookup"><span data-stu-id="c3687-203">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="c3687-204">W przypadku korzystania z takich skrótów skróty nazw operacji powinny mieć wielkie litery (np.: `MAJ` ).</span><span class="sxs-lookup"><span data-stu-id="c3687-204">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="c3687-205">W przypadku stosowania niniejszej Konwencji w przypadku powszechnie używanych akronimów i initialisms takich jak "QFT" dla "transformacji Fouriera Quantum" wymagane jest pewne uwagi.</span><span class="sxs-lookup"><span data-stu-id="c3687-205">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="c3687-206">Sugerujemy następujące ogólne konwencje platformy .NET na potrzeby używania akronimów i initialisms w pełnych nazwach, które określają, że:</span><span class="sxs-lookup"><span data-stu-id="c3687-206">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="c3687-207">Dwuliterowe akronimy i initialisms są nazwane wielkimi literami (np.: `BE` dla "Big-Endian"),</span><span class="sxs-lookup"><span data-stu-id="c3687-207">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="c3687-208">wszystkie dłuższe akronimy i initialisms są nazywane w `CamelCase` (np.: `Qft` dla "Quantum Fouriera Transform")</span><span class="sxs-lookup"><span data-stu-id="c3687-208">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="c3687-209">W ten sposób operacja implementująca QFT może zostać wywołana `QFT` jako skrót lub zapisywana jako `ApplyQft` .</span><span class="sxs-lookup"><span data-stu-id="c3687-209">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="c3687-210">Dla szczególnie często używanych operacji i funkcji może być pożądane podanie nazwy skróconej jako _aliasu_ dla dłuższej postaci:</span><span class="sxs-lookup"><span data-stu-id="c3687-210">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="c3687-211">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-211">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="c3687-212">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-212">We suggest:</span></span>

- <span data-ttu-id="c3687-213">W razie potrzeby Rozważ często akceptowane i powszechnie używane nazwy skrócone.</span><span class="sxs-lookup"><span data-stu-id="c3687-213">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="c3687-214">Używaj wielkich liter dla skróconej składni.</span><span class="sxs-lookup"><span data-stu-id="c3687-214">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="c3687-215">Używaj wielkich liter dla krótkich (dwuliterowych) akronimów i initialisms.</span><span class="sxs-lookup"><span data-stu-id="c3687-215">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="c3687-216">Użyj `CamelCase` do dłuższej (trzy lub więcej liter) akronimów i initialisms.</span><span class="sxs-lookup"><span data-stu-id="c3687-216">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-217">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-217">Examples</span></span>](#tab/examples)

| &nbsp;   | <span data-ttu-id="c3687-218">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c3687-218">Name</span></span> | <span data-ttu-id="c3687-219">Opis</span><span class="sxs-lookup"><span data-stu-id="c3687-219">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="c3687-220">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-220">☑</span></span> | `X` | <span data-ttu-id="c3687-221">Dobrze zrozumiały skrót dla "Zastosuj transformację $X $"</span><span class="sxs-lookup"><span data-stu-id="c3687-221">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="c3687-222">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-222">☑</span></span> | `CNOT` | <span data-ttu-id="c3687-223">Dobrze zrozumiałe skróty dla "kontrolowane-nie"</span><span class="sxs-lookup"><span data-stu-id="c3687-223">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="c3687-224">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-224">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="c3687-225">Skrót nie powinien znajdować się w `CamelCase` .</span><span class="sxs-lookup"><span data-stu-id="c3687-225">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="c3687-226">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-226">☑</span></span> | `ApplyQft` | <span data-ttu-id="c3687-227">Wspólna początkowa wartość "QFT" jest wyświetlana jako część nazwy długiej.</span><span class="sxs-lookup"><span data-stu-id="c3687-227">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="c3687-228">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-228">☑</span></span> | `QFT` | <span data-ttu-id="c3687-229">Wspólna początkowa wartość "QFT" jest wyświetlana jako część nazwy skróconej.</span><span class="sxs-lookup"><span data-stu-id="c3687-229">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



_*_


### <a name="proper-nouns-in-names"></a><span data-ttu-id="c3687-230">Poprawne rzeczowniki w nazwach</span><span class="sxs-lookup"><span data-stu-id="c3687-230">Proper Nouns in Names</span></span> ###

<span data-ttu-id="c3687-231">W czasie, gdy chodzi o to, często należy nazywać się tą osobą po pierwszej stronie, aby opublikować na ich temat, a większość z nich nie jest znana.</span><span class="sxs-lookup"><span data-stu-id="c3687-231">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="c3687-232">Użycie zbyt dużej liczby konwencji nazewnictwa z fizyką może w ten sposób stanowić znaczną barierę do wejścia, ponieważ użytkownicy z innych teł muszą poznać dużą liczbę nieprzezroczystych nazw, aby używać typowych operacji i koncepcji.</span><span class="sxs-lookup"><span data-stu-id="c3687-232">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="c3687-233">Z tego względu zalecamy, aby w miarę rozsądnych, wspólnych rzeczowników, które opisują koncepcję, zostały przyjęte w silnym preferencjzie dla właściwych rzeczowników opisujących historię publikacji koncepcji.</span><span class="sxs-lookup"><span data-stu-id="c3687-233">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="c3687-234">Na przykład, pojedynczo kontrolowane operacje SWAP i podwójnie kontrolowane nie są często nazywane operacjami "Fredkin" i "Toffoli" w literaturze akademickiej, ale są one identyfikowane Q# głównie jako `CSWAP` i `CCNOT` .</span><span class="sxs-lookup"><span data-stu-id="c3687-234">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="c3687-235">W obu przypadkach komentarze dokumentacji interfejsu API zawierają nazwy synonimów na podstawie odpowiednich rzeczowników wraz ze wszystkimi odpowiednimi cytatami.</span><span class="sxs-lookup"><span data-stu-id="c3687-235">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="c3687-236">Ta preferencja jest szczególnie ważna w przypadku, gdy pewne użycie właściwych rzeczowników będzie zawsze konieczne — zgodnie Q# z tradycją dla wielu języków klasycznych, na przykład, i odwołuje się do `Bool` typów w odniesieniu do logiki logicznej, która jest z kolei przyznana jako "George bool".</span><span class="sxs-lookup"><span data-stu-id="c3687-236">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="c3687-237">Kilka koncepcji Quantum podobnie nazywa się w podobny sposób, łącznie z `Pauli` typem wbudowanym do Q# języka.</span><span class="sxs-lookup"><span data-stu-id="c3687-237">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="c3687-238">Minimalizując użycie właściwych rzeczowników, w których takie użycie nie jest niezbędne, zmniejszamy wpływ na to, gdzie nie można rozsądnie uniknąć odpowiednich rzeczowników.</span><span class="sxs-lookup"><span data-stu-id="c3687-238">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="c3687-239">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-239">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="c3687-240">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-240">We suggest:</span></span>

- <span data-ttu-id="c3687-241">Unikaj używania właściwych rzeczowników w nazwach.</span><span class="sxs-lookup"><span data-stu-id="c3687-241">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-242">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-242">Examples</span></span>](#tab/examples)

_*_

### <a name="type-conversions"></a><span data-ttu-id="c3687-243">Konwersje typu</span><span class="sxs-lookup"><span data-stu-id="c3687-243">Type Conversions</span></span> ###

<span data-ttu-id="c3687-244">Ponieważ Q# jest silnie i statycznie wpisanym językiem, wartość jednego typu może być używana tylko jako wartość innego typu za pomocą jawnego wywołania funkcji konwersji typu.</span><span class="sxs-lookup"><span data-stu-id="c3687-244">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="c3687-245">Jest to w przeciwieństwie do języków, które umożliwiają niejawną zmianę typów wartości (np.: Promocja typu) lub poprzez rzutowanie.</span><span class="sxs-lookup"><span data-stu-id="c3687-245">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="c3687-246">W związku z tym funkcje konwersji typów odgrywają ważną rolę w Q# tworzeniu biblioteki i składają się z jednej z najczęściej wykrytych decyzji dotyczących nazewnictwa.</span><span class="sxs-lookup"><span data-stu-id="c3687-246">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="c3687-247">Pamiętaj jednak, że ponieważ konwersje typów są zawsze _deterministyczne_, można je napisać jako funkcje i w związku z tym powyższym.</span><span class="sxs-lookup"><span data-stu-id="c3687-247">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="c3687-248">W szczególności sugerujemy, aby funkcje konwersji typów nigdy nie były nazwane jako czasowniki (np.: `ConvertToX` ) lub parametrów przedpozycyjnych fraz ( `ToX` ), ale powinny być nazwane jako niezależne wyrażenia przymiotników, które wskazują typy źródłowe i docelowe ( `XAsY` ).</span><span class="sxs-lookup"><span data-stu-id="c3687-248">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="c3687-249">Podczas wyświetlania listy typów tablicowych w nazwach funkcji konwersji typów zaleca się użycie skrótu `Arr` .</span><span class="sxs-lookup"><span data-stu-id="c3687-249">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="c3687-250">Z zablokowaniem wyjątkowej sytuacji zalecamy, aby wszystkie funkcje konwersji typów były nazwane przy użyciu, `As` Aby można je było szybko zidentyfikować.</span><span class="sxs-lookup"><span data-stu-id="c3687-250">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="c3687-251">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-251">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="c3687-252">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-252">We suggest:</span></span>

- <span data-ttu-id="c3687-253">Jeśli funkcja konwertuje wartość typu `X` na wartość typu `Y` , należy użyć nazwy `AsY` lub `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="c3687-253">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-254">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-254">Examples</span></span>](#tab/examples)

| &nbsp;   | <span data-ttu-id="c3687-255">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c3687-255">Name</span></span> | <span data-ttu-id="c3687-256">Opis</span><span class="sxs-lookup"><span data-stu-id="c3687-256">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="c3687-257">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-257">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="c3687-258">Pozycja "do" powoduje wyrażenie orzeczenia, wskazujące operację, a nie funkcję.</span><span class="sxs-lookup"><span data-stu-id="c3687-258">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="c3687-259">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-259">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="c3687-260">Typ danych wejściowych nie jest wyczyszczony z nazwy funkcji.</span><span class="sxs-lookup"><span data-stu-id="c3687-260">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="c3687-261">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-261">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="c3687-262">Typy wejściowe i wyjściowe są wyświetlane w niewłaściwej kolejności.</span><span class="sxs-lookup"><span data-stu-id="c3687-262">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="c3687-263">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-263">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="c3687-264">Typy wejściowe i typy wyjściowe są jasne.</span><span class="sxs-lookup"><span data-stu-id="c3687-264">Both the input types and output types are clear.</span></span> |

_*_

### <a name="private-or-internal-names"></a><span data-ttu-id="c3687-265">Nazwy prywatne lub wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="c3687-265">Private or Internal Names</span></span> ###

<span data-ttu-id="c3687-266">W wielu przypadkach nazwa jest przeznaczona wyłącznie do użytku wewnętrznego dla biblioteki lub projektu i nie jest zagwarantowanam elementem interfejsu API oferowanym przez bibliotekę.</span><span class="sxs-lookup"><span data-stu-id="c3687-266">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="c3687-267">Warto jasno wskazać, że jest to przypadek w przypadku nazywania funkcji i operacji, tak aby przypadkowe zależności w kodzie wewnętrznym były oczywiste.</span><span class="sxs-lookup"><span data-stu-id="c3687-267">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="c3687-268">Jeśli operacja lub funkcja nie jest przeznaczona do użytku bezpośredniego, ale powinna być używana przez pasujące zadanie, które działa przez częściową aplikację, rozważ użycie nazwy rozpoczynającej się od `internal` słowa kluczowego dla możliwego do odtworzenia.</span><span class="sxs-lookup"><span data-stu-id="c3687-268">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with the `internal` keyword for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="c3687-269">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-269">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="c3687-270">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-270">We suggest:</span></span>

- <span data-ttu-id="c3687-271">Gdy funkcja, operacja lub typ zdefiniowany przez użytkownika nie jest częścią publicznego interfejsu API dla Q# biblioteki lub programu, upewnij się, że jest oznaczona jako wewnętrzna poprzez umieszczenie `internal` słowa kluczowego przed `function` `operation` `newtype` deklaracją, lub.</span><span class="sxs-lookup"><span data-stu-id="c3687-271">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that it is marked as internal by placing the `internal` keyword before the `function`, `operation`, or `newtype` declaration.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-272">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-272">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="c3687-273">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c3687-273">Name</span></span> | <span data-ttu-id="c3687-274">Opis</span><span class="sxs-lookup"><span data-stu-id="c3687-274">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="c3687-275">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-275">☒</span></span> | <s>`operation _ApplyDecomposedOperation`</s> | <span data-ttu-id="c3687-276">Nie używaj znaku podkreślenia `_` , aby wskazać, że ta operacja jest tylko do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="c3687-276">Do not use an underscore `_` to indicate that this operation is for internal use only.</span></span> |
| <span data-ttu-id="c3687-277">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-277">☑</span></span> | `internal operation ApplyDecomposedOperation` | <span data-ttu-id="c3687-278">`internal`Słowo kluczowe na początku jasno wskazuje, że ta operacja jest tylko do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="c3687-278">The `internal` keyword at the beginning clearly indicates that this operation is for internal use only.</span></span> |

_*_
### <a name="variants"></a><span data-ttu-id="c3687-279">elementy Variant</span><span class="sxs-lookup"><span data-stu-id="c3687-279">Variants</span></span> ###

<span data-ttu-id="c3687-280">Mimo że to ograniczenie może nie pogorszyć w przyszłych wersjach programu, jest to gotowe do użycia w Q# przypadku często grup powiązanych operacji lub funkcji, które są rozróżniane przez funktory ich obsługę danych wejściowych lub konkretne typy argumentów.</span><span class="sxs-lookup"><span data-stu-id="c3687-280">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="c3687-281">Te grupy można rozróżnić przy użyciu tej samej nazwy głównej, po której następuje jedna lub dwie litery wskazujące jej wariant.</span><span class="sxs-lookup"><span data-stu-id="c3687-281">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="c3687-282">Przedrostk</span><span class="sxs-lookup"><span data-stu-id="c3687-282">Suffix</span></span> | <span data-ttu-id="c3687-283">Znaczenie</span><span class="sxs-lookup"><span data-stu-id="c3687-283">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="c3687-284">Oczekiwano danych wejściowych do obsługi `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="c3687-284">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="c3687-285">Oczekiwano danych wejściowych do obsługi `Controlled`</span><span class="sxs-lookup"><span data-stu-id="c3687-285">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="c3687-286">Oczekiwano danych wejściowych do obsługi `Controlled` i `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="c3687-286">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="c3687-287">Dane wejściowe lub wejścia są typu `Int`</span><span class="sxs-lookup"><span data-stu-id="c3687-287">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="c3687-288">Dane wejściowe lub wejścia są typu `Double`</span><span class="sxs-lookup"><span data-stu-id="c3687-288">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="c3687-289">Dane wejściowe lub wejścia są typu `BigInt`</span><span class="sxs-lookup"><span data-stu-id="c3687-289">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="c3687-290">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-290">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="c3687-291">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-291">We suggest:</span></span>

- <span data-ttu-id="c3687-292">Jeśli funkcja lub operacja nie jest powiązana z żadną podobną funkcją lub operacji według typów i obsługi danych wejściowych Funktor, nie należy używać sufiksu.</span><span class="sxs-lookup"><span data-stu-id="c3687-292">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="c3687-293">Jeśli funkcja lub operacja jest powiązana z innymi podobnymi funkcjami lub operacjami przez typy i obsługę Funktor ich danych wejściowych, użyj sufiksów jak w powyższej tabeli, aby rozróżnić warianty.</span><span class="sxs-lookup"><span data-stu-id="c3687-293">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-294">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-294">Examples</span></span>](#tab/examples)

_*_

### <a name="arguments-and-variables"></a><span data-ttu-id="c3687-295">Argumenty i zmienne</span><span class="sxs-lookup"><span data-stu-id="c3687-295">Arguments and Variables</span></span> ###

<span data-ttu-id="c3687-296">Kluczowy cel Q# kodu dla funkcji lub operacji jest przeznaczony do łatwego odczytywania i interpretowania.</span><span class="sxs-lookup"><span data-stu-id="c3687-296">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="c3687-297">Podobnie nazwy danych wejściowych i argumentów typu powinny komunikować się, w jaki sposób funkcja lub argument będą używane po podaniu.</span><span class="sxs-lookup"><span data-stu-id="c3687-297">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="c3687-298">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-298">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="c3687-299">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-299">We suggest:</span></span>

- <span data-ttu-id="c3687-300">Dla wszystkich nazw zmiennych i wejściowych Użyj `pascalCase` w silnym preferencjzie do `CamelCase` , `snake_case` lub `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="c3687-300">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="c3687-301">Nazwy wejściowe powinny być opisowe; należy unikać jednej lub dwóch nazw liter, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="c3687-301">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="c3687-302">Operacje i funkcje akceptujące dokładnie jeden argument typu powinny wskazywać ten argument typu przez, `T` gdy jego rola jest oczywista.</span><span class="sxs-lookup"><span data-stu-id="c3687-302">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="c3687-303">Jeśli funkcja lub operacja przyjmuje wiele argumentów typu lub Jeśli rola pojedynczego typu argumentu nie jest oczywista, należy rozważyć użycie krótkiego wyrazu z prefiksem `T` (np.: `TOutput` ) dla każdego typu.</span><span class="sxs-lookup"><span data-stu-id="c3687-303">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="c3687-304">Nie dołączaj nazw typów w nazwach argumentów i zmiennych; te informacje mogą być udostępniane przez środowisko deweloperskie.</span><span class="sxs-lookup"><span data-stu-id="c3687-304">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="c3687-305">Należy zauważyć typy skalarne według ich nazw literałów ( `flagQubit` ) i typów tablicowych w liczbie mnogiej ( `measResults` ).</span><span class="sxs-lookup"><span data-stu-id="c3687-305">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="c3687-306">W szczególności dla tablic qubits należy rozważyć określenie takich typów, `Register` gdzie nazwa odwołuje się do sekwencji qubits, które są ściśle powiązane w jakiś sposób.</span><span class="sxs-lookup"><span data-stu-id="c3687-306">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="c3687-307">Zmienne używane jako indeksy w tablicach powinny zaczynać się od `idx` i powinny być pojedyncze (np.: `things[idxThing]` ).</span><span class="sxs-lookup"><span data-stu-id="c3687-307">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="c3687-308">W szczególności zdecydowanie Unikaj używania nazw zmiennych o pojedynczej literze jako indeksów; Rozważ użycie `idx` co najmniej.</span><span class="sxs-lookup"><span data-stu-id="c3687-308">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="c3687-309">Zmienne używane do przechowywania długości tablic powinny zaczynać się od `n` i powinny być w liczbie mnogiej (np.: `nThings` ).</span><span class="sxs-lookup"><span data-stu-id="c3687-309">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-310">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-310">Examples</span></span>](#tab/examples)

_*_

### <a name="user-defined-type-named-items"></a><span data-ttu-id="c3687-311">User-Defined typ o nazwie Items</span><span class="sxs-lookup"><span data-stu-id="c3687-311">User-Defined Type Named Items</span></span> ###

<span data-ttu-id="c3687-312">Nazwane elementy w typach zdefiniowanych przez użytkownika powinny być nazwane jako `CamelCase` , nawet w danych wejściowych dla konstruktorów UDT.</span><span class="sxs-lookup"><span data-stu-id="c3687-312">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="c3687-313">Ułatwia to łatwe oddzielenie nazwanych elementów od odwołań do zmiennych w zakresie lokalnie podczas korzystania z notacji metody dostępu (np.: `callable::Apply` ) lub notacji kopiowania i aktualizacji ( `set arr w/= Data <- newData` ).</span><span class="sxs-lookup"><span data-stu-id="c3687-313">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="c3687-314">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-314">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="c3687-315">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-315">We suggest:</span></span>

- <span data-ttu-id="c3687-316">Nazwane elementy w konstruktorach UDT powinny mieć nazwę `CamelCase` ; oznacza to, że powinny rozpoczynać się od początkowej wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="c3687-316">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="c3687-317">Nazwane elementy, które są rozpoznawane jako operacje, powinny być nazwane jako etapy zleceń.</span><span class="sxs-lookup"><span data-stu-id="c3687-317">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="c3687-318">Nazwane elementy, które nie są rozpoznawane do operacji, powinny być nazwane jako frazy rzeczowników.</span><span class="sxs-lookup"><span data-stu-id="c3687-318">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="c3687-319">Dla UDTs, które zawijają operacje, należy zdefiniować pojedynczy nazwany element o nazwie `Apply` .</span><span class="sxs-lookup"><span data-stu-id="c3687-319">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-320">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-320">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="c3687-321">Fragment kodu</span><span class="sxs-lookup"><span data-stu-id="c3687-321">Snippet</span></span> | <span data-ttu-id="c3687-322">Opis</span><span class="sxs-lookup"><span data-stu-id="c3687-322">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="c3687-323">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-323">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="c3687-324">Nazwa `Apply` jest `CamelCase` podsformatowaną frazą czasownikową, sugerując, że nazwany element jest operacją.</span><span class="sxs-lookup"><span data-stu-id="c3687-324">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="c3687-325">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-325">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="c3687-326">Nazwane elementy powinny rozpoczynać się od początkowej wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="c3687-326">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="c3687-327">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-327">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="c3687-328">Nazwane elementy, które rozwiązują funkcje, powinny być nazwane jako frazy rzeczownikowe, a nie jako wyrażenia czasownikowe.</span><span class="sxs-lookup"><span data-stu-id="c3687-328">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

_*_

## <a name="input-conventions"></a><span data-ttu-id="c3687-329">Konwencje wejściowe</span><span class="sxs-lookup"><span data-stu-id="c3687-329">Input Conventions</span></span> ##

<span data-ttu-id="c3687-330">Gdy deweloper wywołuje operację lub funkcję, różne dane wejściowe do tej operacji lub funkcji muszą być określone w określonej kolejności, zwiększając obciążenie poznawcze, które są używane przez twarzy dla deweloperów.</span><span class="sxs-lookup"><span data-stu-id="c3687-330">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="c3687-331">W szczególności zadanie zapamiętywania kolejności danych wejściowych jest często rozpraszane z zadania: Programowanie implementacji algorytmu Quantum.</span><span class="sxs-lookup"><span data-stu-id="c3687-331">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="c3687-332">Chociaż rozbudowana obsługa środowiska IDE może w dużym stopniu ograniczyć, dobry projekt i przestrzeganie wspólnych Konwencji może również pomóc w zminimalizowaniu obciążenia poznawczego narzuconego przez interfejs API.</span><span class="sxs-lookup"><span data-stu-id="c3687-332">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="c3687-333">Tam, gdzie to możliwe, może być pomocne zmniejszenie liczby wejść oczekiwanych przez operację lub funkcję, dzięki czemu rola każdego danych wejściowych jest bardziej oczywista bezpośrednio dla deweloperów wywołujących tę operację lub funkcję, a także do deweloperów odczytujących ten kod później.</span><span class="sxs-lookup"><span data-stu-id="c3687-333">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="c3687-334">Szczególnie gdy nie jest możliwe lub uzasadnione zmniejszanie liczby argumentów do operacji lub funkcji, ważne jest, aby mieć spójne porządkowanie, które minimalizuje nieoczekiwane działanie użytkownika podczas przewidywania kolejności danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="c3687-334">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="c3687-335">Zalecamy konwencje określania danych wejściowych, które w znacznym stopniu wynikają z działania częściowej aplikacji jako generalizacji currying f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="c3687-335">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="c3687-336">W związku z tym, częściowe stosowanie pierwszych argumentów powinno skutkować wywoływaniem, który jest przydatny we własnym imieniu, gdy jest to uzasadnione.</span><span class="sxs-lookup"><span data-stu-id="c3687-336">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="c3687-337">Zgodnie z tą zasadą należy rozważyć użycie następującej kolejności argumentów:</span><span class="sxs-lookup"><span data-stu-id="c3687-337">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="c3687-338">Klasyczne argumenty, które nie można wywołać, takie jak kąty, wektory uprawnień itp.</span><span class="sxs-lookup"><span data-stu-id="c3687-338">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="c3687-339">Wywoływane argumenty (funkcje i argumenty).</span><span class="sxs-lookup"><span data-stu-id="c3687-339">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="c3687-340">Jeśli obie funkcje i operacje są traktowane jako argumenty, Rozważ umieszczenie operacji po funkcjach.</span><span class="sxs-lookup"><span data-stu-id="c3687-340">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="c3687-341">Kolekcje działały na podstawie wywoływanych argumentów w podobny sposób do `Map` ,, `Iter` `Enumerate` i `Fold` .</span><span class="sxs-lookup"><span data-stu-id="c3687-341">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="c3687-342">Argumenty qubit używane jako formanty.</span><span class="sxs-lookup"><span data-stu-id="c3687-342">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="c3687-343">Argumenty qubit używane jako elementy docelowe.</span><span class="sxs-lookup"><span data-stu-id="c3687-343">Qubit arguments used as targets.</span></span>

<span data-ttu-id="c3687-344">Rozważmy operację `ApplyPhaseEstimationIteration` do użycia w ocenie fazy, która przyjmuje kąt i Oracle, przekazuje kąt do `Rz` modyfikacji przez tablicę różnych czynników skalowania, a następnie kontroluje aplikacje firmy Oracle.</span><span class="sxs-lookup"><span data-stu-id="c3687-344">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="c3687-345">Dane wejściowe można zamówić `ApplyPhaseEstimationIteration` w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c3687-345">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="c3687-346">W specjalnym przypadku minimalizowania niespodziewania niektóre funkcje i operacje naśladowania zachowania wbudowanej funktory `Adjoint` i `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="c3687-346">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="c3687-347">Na przykład `ControlledOnInt<'T>` ma typ `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` , który `ControlledOnInt<Qubit[]>(5, _)` działa podobnie jak `Controlled` Funktor, ale na stanie, w którym Rejestr sterowania reprezentuje stan $ \ket {5} = \ket {101} $.</span><span class="sxs-lookup"><span data-stu-id="c3687-347">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="c3687-348">W ten sposób deweloper oczekuje, że dane wejściowe, które mają zostać `ControlledOnInt` przekształcone w dół, są ostatnio i że wynikowa operacja przyjmuje jako wartość wejściową `(Qubit[], 'T)` ---tej samej kolejności, a następnie dane wyjściowe `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="c3687-348">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="c3687-349">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-349">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="c3687-350">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-350">We suggest:</span></span>

- <span data-ttu-id="c3687-351">Użyj kolejności danych wejściowych spójnej z użyciem częściowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c3687-351">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="c3687-352">Użyj kolejności danych wejściowych spójnych z wbudowanym funktory.</span><span class="sxs-lookup"><span data-stu-id="c3687-352">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="c3687-353">Umieść wszystkie klasyczne dane wejściowe przed wszelkimi danymi wejściowymi Quantum.</span><span class="sxs-lookup"><span data-stu-id="c3687-353">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-354">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-354">Examples</span></span>](#tab/examples)

_*_

## <a name="documentation-conventions"></a><span data-ttu-id="c3687-355">Konwencje dokumentacji</span><span class="sxs-lookup"><span data-stu-id="c3687-355">Documentation Conventions</span></span> ##

<span data-ttu-id="c3687-356">Q#Język umożliwia dołączanie dokumentacji do operacji, funkcji i typów zdefiniowanych przez użytkownika za pomocą specjalnie sformatowanych komentarzy do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="c3687-356">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="c3687-357">Oznacza to `///` , że komentarze w dokumentacji to małe ukośniki (), które mogą [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) być używane do opisywania przeznaczenia każdej operacji, funkcji i typu zdefiniowanego przez użytkownika, jakie dane muszą oczekiwać i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="c3687-357">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="c3687-358">Kompilator dostarczany z zestawem SDK Quantum wyodrębnia te komentarze i korzysta z nich, aby pomóc w poziomego złożenia dokumentacji podobnej do tej https://docs.microsoft.com/quantum .</span><span class="sxs-lookup"><span data-stu-id="c3687-358">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="c3687-359">Podobnie serwer językowy dostarczony z zestawem Quantum Development Kit używa tych komentarzy, aby zapewnić użytkownikom Pomoc po umieszczeniu wskaźnika myszy na symbolach w Q# kodzie.</span><span class="sxs-lookup"><span data-stu-id="c3687-359">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="c3687-360">Korzystanie z komentarzy do dokumentacji może ułatwić użytkownikom zrozumienie kodu przez udostępnienie przydatnego odwołania do szczegółów, które nie są łatwo wyrażone przy użyciu innych konwencji zawartych w tym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="c3687-360">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="c3687-361">[Odwołanie do składni komentarza do dokumentacji](xref:microsoft.quantum.qsharp.comments#documentation-comments).</span><span class="sxs-lookup"><span data-stu-id="c3687-361">[Documentation comment syntax reference](xref:microsoft.quantum.qsharp.comments#documentation-comments).</span></span>

<span data-ttu-id="c3687-362">Aby efektywnie korzystać z tej funkcji w celu ułatwienia użytkownikom, zalecamy zachowywanie kilku rzeczy podczas pisania komentarzy do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="c3687-362">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="c3687-363">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-363">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="c3687-364">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-364">We suggest:</span></span>

- <span data-ttu-id="c3687-365">Każda funkcja publiczna, operacja i typ zdefiniowany przez użytkownika powinny być bezpośrednio poprzedzone komentarzem do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="c3687-365">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="c3687-366">Co najmniej każdy komentarz dokumentacji powinien zawierać następujące sekcje:</span><span class="sxs-lookup"><span data-stu-id="c3687-366">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="c3687-367">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="c3687-367">Summary</span></span>
    - <span data-ttu-id="c3687-368">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c3687-368">Input</span></span>
    - <span data-ttu-id="c3687-369">Dane wyjściowe (jeśli dotyczy)</span><span class="sxs-lookup"><span data-stu-id="c3687-369">Output (if applicable)</span></span>
- <span data-ttu-id="c3687-370">Upewnij się, że wszystkie podsumowania są dwa zdania lub mniej.</span><span class="sxs-lookup"><span data-stu-id="c3687-370">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="c3687-371">Jeśli potrzebujesz więcej miejsca, podaj `# Description` sekcję bezpośrednio po `# Summary` zakończeniu szczegółowego.</span><span class="sxs-lookup"><span data-stu-id="c3687-371">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="c3687-372">W odpowiednich przypadkach nie należy uwzględniać obliczeń matematycznych, ponieważ nie wszyscy klienci obsługują notację TeX w podsumowaniu.</span><span class="sxs-lookup"><span data-stu-id="c3687-372">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="c3687-373">Należy pamiętać, że podczas pisania dokumentów Prose (np. TeX lub promocji) może być zalecane użycie dłuższych długości wierszy.</span><span class="sxs-lookup"><span data-stu-id="c3687-373">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="c3687-374">Podaj wszystkie odpowiednie wyrażenia matematyczne w `# Description` sekcji.</span><span class="sxs-lookup"><span data-stu-id="c3687-374">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="c3687-375">Podczas opisywania danych wejściowych nie należy powtarzać typów poszczególnych danych wejściowych, ponieważ mogą one zostać wywnioskowane przez kompilator i ryzyko wprowadzające niespójność.</span><span class="sxs-lookup"><span data-stu-id="c3687-375">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="c3687-376">Podaj odpowiednie przykłady, z których każda znajduje się w osobnej `# Example` sekcji.</span><span class="sxs-lookup"><span data-stu-id="c3687-376">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="c3687-377">Zwięźle opisz każdy przykład przed listą kodów.</span><span class="sxs-lookup"><span data-stu-id="c3687-377">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="c3687-378">Pocite wszystkie odpowiednie Publikacje akademickie (np.: dokumenty, postępowania, wpisy w blogu i alternatywne implementacje) w `# References` sekcji jako lista punktowana łączy.</span><span class="sxs-lookup"><span data-stu-id="c3687-378">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="c3687-379">Upewnij się, że w miarę możliwości wszystkie linki cytatu mają stałe i niezmienne identyfikatory (DOIs lub z wersjami arXiv).</span><span class="sxs-lookup"><span data-stu-id="c3687-379">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="c3687-380">Gdy operacja lub funkcja jest powiązana z innymi operacjami lub funkcjami według wariantów Funktor, wystaw inne warianty jako punktory w `# See Also` sekcji.</span><span class="sxs-lookup"><span data-stu-id="c3687-380">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="c3687-381">Pozostaw pustą linię komentarza między sekcjami poziom-1 ( `/// #` ), ale nie pozostawiaj pustego wiersza między sekcjami poziom-2 ( `/// ##` ).</span><span class="sxs-lookup"><span data-stu-id="c3687-381">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-382">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-382">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="c3687-383">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-383">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

_*_

## <a name="formatting-conventions"></a><span data-ttu-id="c3687-384">Konwencje formatowania</span><span class="sxs-lookup"><span data-stu-id="c3687-384">Formatting Conventions</span></span> ##

<span data-ttu-id="c3687-385">Oprócz powyższych sugestii pomocne może być wprowadzenie kodu jako czytelnego do używania spójnych reguł formatowania.</span><span class="sxs-lookup"><span data-stu-id="c3687-385">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="c3687-386">Takie reguły formatowania według natury mają być nieco dowolne i silnie do osobistych estetycznych.</span><span class="sxs-lookup"><span data-stu-id="c3687-386">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="c3687-387">Niemniej zalecamy utrzymywanie spójnego zestawu Konwencji formatowania w grupie współpracowników i szczególnie w przypadku dużych Q# projektów, takich jak zestaw Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="c3687-387">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="c3687-388">Te reguły mogą być automatycznie stosowane przy użyciu narzędzia formatowania zintegrowanego z Q# kompilatorem.</span><span class="sxs-lookup"><span data-stu-id="c3687-388">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="c3687-389">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="c3687-389">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="c3687-390">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="c3687-390">We suggest:</span></span>

- <span data-ttu-id="c3687-391">Używaj czterech spacji zamiast kart do przenoszenia.</span><span class="sxs-lookup"><span data-stu-id="c3687-391">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="c3687-392">Na przykład w VS Code:</span><span class="sxs-lookup"><span data-stu-id="c3687-392">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="c3687-393">Zawijanie wierszy o 79 znaków, gdy jest to uzasadnione.</span><span class="sxs-lookup"><span data-stu-id="c3687-393">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="c3687-394">Używaj spacji wokół operatorów binarnych.</span><span class="sxs-lookup"><span data-stu-id="c3687-394">Use spaces around binary operators.</span></span>
- <span data-ttu-id="c3687-395">Używaj spacji po obu stronach dwukropków używanych do adnotacji typu.</span><span class="sxs-lookup"><span data-stu-id="c3687-395">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="c3687-396">Użyj pojedynczej spacji po przecinkach używanych w literałach tablicowych i krotek (np. w danych wejściowych do funkcji i operacji).</span><span class="sxs-lookup"><span data-stu-id="c3687-396">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="c3687-397">Nie używaj spacji po funkcjach, operacjach lub nazwach UDT ani po `@` deklaracjach atrybutów.</span><span class="sxs-lookup"><span data-stu-id="c3687-397">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="c3687-398">Każda deklaracja atrybutu powinna znajdować się w osobnym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c3687-398">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="c3687-399">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c3687-399">Examples</span></span>](#tab/examples)

| &nbsp; | <span data-ttu-id="c3687-400">Fragment kodu</span><span class="sxs-lookup"><span data-stu-id="c3687-400">Snippet</span></span> | <span data-ttu-id="c3687-401">Opis</span><span class="sxs-lookup"><span data-stu-id="c3687-401">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="c3687-402">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-402">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="c3687-403">Używaj spacji wokół operatorów binarnych.</span><span class="sxs-lookup"><span data-stu-id="c3687-403">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="c3687-404">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-404">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="c3687-405">Używaj spacji wokół dwukropka adnotacji typu.</span><span class="sxs-lookup"><span data-stu-id="c3687-405">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="c3687-406">☑</span><span class="sxs-lookup"><span data-stu-id="c3687-406">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="c3687-407">Elementy w spójnej kolekcji są poprawnie wprowadzane do czytelności.</span><span class="sxs-lookup"><span data-stu-id="c3687-407">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="c3687-408">☒</span><span class="sxs-lookup"><span data-stu-id="c3687-408">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="c3687-409">Spacje powinny być pomijane po nazwach funkcji, operacji lub UDT.</span><span class="sxs-lookup"><span data-stu-id="c3687-409">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

<span data-ttu-id="c3687-410">_\*\*</span><span class="sxs-lookup"><span data-stu-id="c3687-410">_\*\*</span></span>

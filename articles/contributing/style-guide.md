---
title: 'Przewodnik po stylu Q # | Microsoft Docs'
description: 'Przewodnik po stylu Q #'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 56455e9d5cd452b8620ee794f40563d1d3040193
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183849"
---
# <a name="q-style-guide"></a><span data-ttu-id="90a92-103">Przewodnik po stylu Q #</span><span class="sxs-lookup"><span data-stu-id="90a92-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="90a92-104">Konwencje ogólne</span><span class="sxs-lookup"><span data-stu-id="90a92-104">General Conventions</span></span> ##

<span data-ttu-id="90a92-105">Konwencje sugerowane w tym przewodniku mają na celu ułatwienie odczytywania i zrozumienia programów oraz bibliotek utworzonych w usłudze Q.</span><span class="sxs-lookup"><span data-stu-id="90a92-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-106">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-106">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="90a92-107">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-107">We suggest:</span></span>

- <span data-ttu-id="90a92-108">Nigdy nie należy ignorować Konwencji, chyba że jest to celowe w celu zapewnienia bardziej czytelnego i zrozumiałego kodu dla użytkowników.</span><span class="sxs-lookup"><span data-stu-id="90a92-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-109">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-109">Examples</span></span>](#tab/examples)

***

## <a name="naming-conventions"></a><span data-ttu-id="90a92-110">Konwencje nazewnictwa</span><span class="sxs-lookup"><span data-stu-id="90a92-110">Naming Conventions</span></span> ##

<span data-ttu-id="90a92-111">W ofercie zestawu Quantum Development Kit dążymy do nazywania funkcji i operacji, które ułatwiają deweloperom Quantum pisanie programów łatwych w odczytaniu i minimalizujących niespodziewane działanie.</span><span class="sxs-lookup"><span data-stu-id="90a92-111">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="90a92-112">Ważną częścią tego jest to, że w przypadku wybrania nazw dla funkcji, operacji i typów firma Microsoft ustala *słownictwo* , którego programiści używają do wyrażania koncepcji Quantum; Dzięki naszym wyborom firma Microsoft może powstrzymywać i utrudniać ich wysiłki w celu wyraźnego komunikowania się.</span><span class="sxs-lookup"><span data-stu-id="90a92-112">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="90a92-113">Dzięki temu firma Microsoft musi upewnić się, że wprowadzone nazwy oferują przejrzystość, a nie przesłania.</span><span class="sxs-lookup"><span data-stu-id="90a92-113">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="90a92-114">W tej sekcji szczegółowo opisano sposób, w jaki firma Microsoft spełnia ten obowiązek w zakresie jawnych wskazówek, które ułatwiają nam najlepszą realizację przez społeczność deweloperów rozwiązań Q.</span><span class="sxs-lookup"><span data-stu-id="90a92-114">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="90a92-115">Operacje i funkcje</span><span class="sxs-lookup"><span data-stu-id="90a92-115">Operations and Functions</span></span> ###

<span data-ttu-id="90a92-116">Jedną z najważniejszych rzeczy, które powinien określić nazwa, jest to, czy dany symbol reprezentuje funkcję czy operację.</span><span class="sxs-lookup"><span data-stu-id="90a92-116">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="90a92-117">Różnica między funkcjami i operacjami ma kluczowe znaczenie dla zrozumienie, jak działa blok kodu.</span><span class="sxs-lookup"><span data-stu-id="90a92-117">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="90a92-118">Aby komunikować się z rozróżnieniem między funkcjami i operacjami użytkowników, opieramy się na tym, że te wyniki są obsługiwane przez funkcję Quantum w ramach operacji ubocznych.</span><span class="sxs-lookup"><span data-stu-id="90a92-118">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="90a92-119">Oznacza to, że operacja *wykonuje* coś.</span><span class="sxs-lookup"><span data-stu-id="90a92-119">That is, an operation *does* something.</span></span>

<span data-ttu-id="90a92-120">Z kolei funkcje opisują relacje matematyczne między danymi.</span><span class="sxs-lookup"><span data-stu-id="90a92-120">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="90a92-121">Wyrażenie `Sin(PI() / 2.0)` *jest* `1.0`i oznacza brak informacji o stanie programu lub jego qubits.</span><span class="sxs-lookup"><span data-stu-id="90a92-121">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="90a92-122">Podsumowywanie, operacje wykonywane w trakcie wykonywania funkcji.</span><span class="sxs-lookup"><span data-stu-id="90a92-122">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="90a92-123">Takie rozróżnienie sugeruje, że nazwy operacji są nazywane czasownikami i funkcjami jako rzeczownikami.</span><span class="sxs-lookup"><span data-stu-id="90a92-123">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="90a92-124">Po zadeklarowaniu typu zdefiniowanego przez użytkownika, Nowa funkcja, która konstruuje wystąpienia tego typu jest niejawnie zdefiniowana w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="90a92-124">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="90a92-125">W tej perspektywie typy zdefiniowane przez użytkownika powinny być nazwane jako rzeczowniki, tak aby oba typy i funkcje konstruktora miały spójne nazwy.</span><span class="sxs-lookup"><span data-stu-id="90a92-125">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="90a92-126">W odpowiednim przypadku upewnij się, że nazwy operacji zaczynają się od czasowników jasno wskazujących wpływ operacji.</span><span class="sxs-lookup"><span data-stu-id="90a92-126">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="90a92-127">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="90a92-127">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="90a92-128">Jeden przypadek, który zachowuje szczególną wzmiankę, jest, gdy operacja wykonuje inną operację jako dane wejściowe i wywołuje ją.</span><span class="sxs-lookup"><span data-stu-id="90a92-128">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="90a92-129">W takich przypadkach Akcja podejmowana przez operację wejściową nie jest wyczyszczona, gdy została zdefiniowana operacja zewnętrzna, w taki sposób, że właściwe zlecenie nie jest natychmiast czyszczone.</span><span class="sxs-lookup"><span data-stu-id="90a92-129">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="90a92-130">Zalecamy, aby zlecenie `Apply`, jak `ApplyIf`, `ApplyToEach`i `ApplyToFirst`.</span><span class="sxs-lookup"><span data-stu-id="90a92-130">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="90a92-131">Inne zlecenia mogą być również przydatne w tym przypadku, jak w `IterateThroughCartesianPower`.</span><span class="sxs-lookup"><span data-stu-id="90a92-131">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="90a92-132">Czasownik</span><span class="sxs-lookup"><span data-stu-id="90a92-132">Verb</span></span> | <span data-ttu-id="90a92-133">Oczekiwany efekt</span><span class="sxs-lookup"><span data-stu-id="90a92-133">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="90a92-134">Składanie wniosku o przyjęcie do programu</span><span class="sxs-lookup"><span data-stu-id="90a92-134">Apply</span></span> | <span data-ttu-id="90a92-135">Operacja podana jako dane wejściowe jest wywoływana</span><span class="sxs-lookup"><span data-stu-id="90a92-135">An operation provided as input is called</span></span> |
| <span data-ttu-id="90a92-136">Stanowcz</span><span class="sxs-lookup"><span data-stu-id="90a92-136">Assert</span></span> | <span data-ttu-id="90a92-137">Hipoteza dotycząca wyniku możliwego pomiaru Quantum jest sprawdzana przez symulator</span><span class="sxs-lookup"><span data-stu-id="90a92-137">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="90a92-138">Szacowany</span><span class="sxs-lookup"><span data-stu-id="90a92-138">Estimate</span></span> | <span data-ttu-id="90a92-139">Wartość jest zwracana, reprezentująca oszacowanie pobrane z co najmniej jednego pomiaru</span><span class="sxs-lookup"><span data-stu-id="90a92-139">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="90a92-140">Mierzyć</span><span class="sxs-lookup"><span data-stu-id="90a92-140">Measure</span></span> | <span data-ttu-id="90a92-141">Pomiar Quantum jest wykonywany, a jego wynik jest zwracany do użytkownika</span><span class="sxs-lookup"><span data-stu-id="90a92-141">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="90a92-142">Przygotowanie</span><span class="sxs-lookup"><span data-stu-id="90a92-142">Prepare</span></span> | <span data-ttu-id="90a92-143">Dana Rejestracja qubits jest inicjowana w określonym stanie</span><span class="sxs-lookup"><span data-stu-id="90a92-143">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="90a92-144">Przykład</span><span class="sxs-lookup"><span data-stu-id="90a92-144">Sample</span></span> | <span data-ttu-id="90a92-145">Wartość klasyczna jest zwracana losowo z pewnej dystrybucji</span><span class="sxs-lookup"><span data-stu-id="90a92-145">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="90a92-146">W przypadku funkcji sugerujemy unikanie korzystania z czasowników na rzecz typowych rzeczowników (Zobacz wskazówki dotyczące odpowiednich rzeczowników poniżej) lub przymiotników:</span><span class="sxs-lookup"><span data-stu-id="90a92-146">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="90a92-147">W szczególności we wszystkich przypadkach sugerujemy użycie Past participles, gdzie jest to konieczne, aby wskazać, że nazwa funkcji jest silnie połączona z akcją lub efektem ubocznym w innym miejscu w programie Quantum.</span><span class="sxs-lookup"><span data-stu-id="90a92-147">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="90a92-148">Na przykład, `ControlledOnInt` używa częściowej formy "kontrolki" zlecenia "Participle", aby wskazać, że funkcja działa jako przymiotnik, aby zmodyfikować jego argument.</span><span class="sxs-lookup"><span data-stu-id="90a92-148">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="90a92-149">Ta nazwa ma dodatkową korzyść do dopasowania semantyki wbudowanych `Controlled` Funktor, jak opisano poniżej.</span><span class="sxs-lookup"><span data-stu-id="90a92-149">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="90a92-150">Podobnie _rzeczowniki agentów_ mogą służyć do konstruowania nazw funkcji i UDT z nazw operacji, tak jak w przypadku `Encoder` nazw dla UDT, które jest silnie powiązane z `Encode`.</span><span class="sxs-lookup"><span data-stu-id="90a92-150">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-151">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-151">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="90a92-152">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-152">We suggest:</span></span>

- <span data-ttu-id="90a92-153">Użyj czasowników dla nazw operacji.</span><span class="sxs-lookup"><span data-stu-id="90a92-153">Use verbs for operation names.</span></span>
- <span data-ttu-id="90a92-154">Używaj rzeczowników lub przymiotników dla nazw funkcji.</span><span class="sxs-lookup"><span data-stu-id="90a92-154">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="90a92-155">Używaj rzeczowników dla typów i atrybutów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="90a92-155">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="90a92-156">Dla wszystkich nazwanych nazw można użyć `CamelCase` w silnym preferencjzie do `pascalCase`, `snake_case`lub `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="90a92-156">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="90a92-157">W szczególności upewnij się, że nazwy, które można wywołać, zaczynają się wielką literą.</span><span class="sxs-lookup"><span data-stu-id="90a92-157">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="90a92-158">Dla wszystkich zmiennych lokalnych Użyj `pascalCase` w silnym preferencjzie, aby `CamelCase`, `snake_case`lub `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="90a92-158">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="90a92-159">W szczególności upewnij się, że zmienne lokalne zaczynają się od małych liter.</span><span class="sxs-lookup"><span data-stu-id="90a92-159">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="90a92-160">Unikaj używania podkreśleń `_` w nazwach funkcji i operacji; Jeśli potrzebujesz dodatkowych poziomów hierarchii, użyj przestrzeni nazw i aliasów przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="90a92-160">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-161">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-161">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="90a92-162">Nazwa</span><span class="sxs-lookup"><span data-stu-id="90a92-162">Name</span></span> | <span data-ttu-id="90a92-163">Opis</span><span class="sxs-lookup"><span data-stu-id="90a92-163">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="90a92-164">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-164">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="90a92-165">Wyczyść użycie czasownika ("odbicie"), aby wskazać efekt operacji.</span><span class="sxs-lookup"><span data-stu-id="90a92-165">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="90a92-166">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-166">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="90a92-167">Użycie funkcji z sugestią typu rzeczownik zamiast operacji.</span><span class="sxs-lookup"><span data-stu-id="90a92-167">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="90a92-168">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-168">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="90a92-169">Korzystanie z notacji `snake_case` contravenes Q #.</span><span class="sxs-lookup"><span data-stu-id="90a92-169">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="90a92-170">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-170">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="90a92-171">Użycie podkreśleń wewnętrznych dla nazwy operacji contravenes Q # Notation.</span><span class="sxs-lookup"><span data-stu-id="90a92-171">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="90a92-172">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-172">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="90a92-173">Użycie frazy rzeczownik sugeruje, że funkcja zwraca operację.</span><span class="sxs-lookup"><span data-stu-id="90a92-173">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="90a92-174">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-174">☑</span></span> | `function EqualityFact` | <span data-ttu-id="90a92-175">Wyczyść użycie rzeczownika ("fakt"), aby wskazać, że jest to funkcja, natomiast przymiotnik.</span><span class="sxs-lookup"><span data-stu-id="90a92-175">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="90a92-176">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-176">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="90a92-177">Użycie czasownika ("Get") sugeruje, że jest to operacja.</span><span class="sxs-lookup"><span data-stu-id="90a92-177">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="90a92-178">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-178">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="90a92-179">Użycie frazy rzeczownik jasno odwołuje się do wyniku wywołania konstruktora UDT.</span><span class="sxs-lookup"><span data-stu-id="90a92-179">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="90a92-180">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-180">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="90a92-181">Użycie wyrażenia orzeczenia sugeruje, że Konstruktor UDT jest operacją.</span><span class="sxs-lookup"><span data-stu-id="90a92-181">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="90a92-182">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-182">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="90a92-183">Użycie frazy rzeczownik komunikuje się z użyciem atrybutu.</span><span class="sxs-lookup"><span data-stu-id="90a92-183">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="90a92-184">Skróty i skróty</span><span class="sxs-lookup"><span data-stu-id="90a92-184">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="90a92-185">Powyższe porady nie poprzednia, istnieje wiele form skróconych, które widzą typowe i powszechne użycie w ramach przetwarzania Quantum.</span><span class="sxs-lookup"><span data-stu-id="90a92-185">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="90a92-186">Sugerujemy używanie istniejących i wspólnych skrótów, gdzie istnieje, szczególnie w przypadku operacji, które są wewnętrzne dla działania maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="90a92-186">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="90a92-187">Na przykład wybierz nazwę `X` zamiast `ApplyX`i `Rz` zamiast `RotateAboutZ`.</span><span class="sxs-lookup"><span data-stu-id="90a92-187">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="90a92-188">Korzystając z takich skrótów, nazwy operacji powinny mieć wielkie litery (np.: `MAJ`).</span><span class="sxs-lookup"><span data-stu-id="90a92-188">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="90a92-189">W przypadku stosowania niniejszej Konwencji w przypadku powszechnie używanych akronimów i initialisms takich jak "QFT" dla "transformacji Fouriera Quantum" wymagane jest pewne uwagi.</span><span class="sxs-lookup"><span data-stu-id="90a92-189">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="90a92-190">Sugerujemy następujące ogólne konwencje platformy .NET na potrzeby używania akronimów i initialisms w pełnych nazwach, które określają, że:</span><span class="sxs-lookup"><span data-stu-id="90a92-190">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="90a92-191">Dwuliterowe akronimy i initialisms są nazwane wielkimi literami (np.: `BE` dla "Big-Endian"),</span><span class="sxs-lookup"><span data-stu-id="90a92-191">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="90a92-192">wszystkie dłuższe akronimy i initialisms są nazwane w `CamelCase` (np.: `Qft` dla "Quantum Fouriera Transform")</span><span class="sxs-lookup"><span data-stu-id="90a92-192">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="90a92-193">W ten sposób operacja implementująca QFT może być wywoływana `QFT` jako skrót lub zapisywana jako `ApplyQft`.</span><span class="sxs-lookup"><span data-stu-id="90a92-193">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="90a92-194">Dla szczególnie często używanych operacji i funkcji może być pożądane podanie nazwy skróconej jako _aliasu_ dla dłuższej postaci:</span><span class="sxs-lookup"><span data-stu-id="90a92-194">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-195">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-195">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="90a92-196">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-196">We suggest:</span></span>

- <span data-ttu-id="90a92-197">W razie potrzeby Rozważ często akceptowane i powszechnie używane nazwy skrócone.</span><span class="sxs-lookup"><span data-stu-id="90a92-197">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="90a92-198">Używaj wielkich liter dla skróconej składni.</span><span class="sxs-lookup"><span data-stu-id="90a92-198">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="90a92-199">Używaj wielkich liter dla krótkich (dwuliterowych) akronimów i initialisms.</span><span class="sxs-lookup"><span data-stu-id="90a92-199">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="90a92-200">Użyj `CamelCase` więcej (co najmniej trzy litery) akronimów i initialisms.</span><span class="sxs-lookup"><span data-stu-id="90a92-200">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-201">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-201">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="90a92-202">Nazwa</span><span class="sxs-lookup"><span data-stu-id="90a92-202">Name</span></span> | <span data-ttu-id="90a92-203">Opis</span><span class="sxs-lookup"><span data-stu-id="90a92-203">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="90a92-204">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-204">☑</span></span> | `X` | <span data-ttu-id="90a92-205">Dobrze zrozumiały skrót dla "Zastosuj transformację $X $"</span><span class="sxs-lookup"><span data-stu-id="90a92-205">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="90a92-206">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-206">☑</span></span> | `CNOT` | <span data-ttu-id="90a92-207">Dobrze zrozumiałe skróty dla "kontrolowane-nie"</span><span class="sxs-lookup"><span data-stu-id="90a92-207">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="90a92-208">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-208">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="90a92-209">Skrót nie powinien znajdować się w `CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="90a92-209">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="90a92-210">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-210">☑</span></span> | `ApplyQft` | <span data-ttu-id="90a92-211">Wspólna początkowa wartość "QFT" jest wyświetlana jako część nazwy długiej.</span><span class="sxs-lookup"><span data-stu-id="90a92-211">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="90a92-212">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-212">☑</span></span> | `QFT` | <span data-ttu-id="90a92-213">Wspólna początkowa wartość "QFT" jest wyświetlana jako część nazwy skróconej.</span><span class="sxs-lookup"><span data-stu-id="90a92-213">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="90a92-214">Poprawne rzeczowniki w nazwach</span><span class="sxs-lookup"><span data-stu-id="90a92-214">Proper Nouns in Names</span></span> ###

<span data-ttu-id="90a92-215">W czasie, gdy chodzi o to, często należy nazywać się tą osobą po pierwszej stronie, aby opublikować na ich temat, a większość z nich nie jest znana.</span><span class="sxs-lookup"><span data-stu-id="90a92-215">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="90a92-216">Użycie zbyt dużej liczby konwencji nazewnictwa z fizyką może w ten sposób stanowić znaczną barierę do wejścia, ponieważ użytkownicy z innych teł muszą poznać dużą liczbę nieprzezroczystych nazw, aby używać typowych operacji i koncepcji.</span><span class="sxs-lookup"><span data-stu-id="90a92-216">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="90a92-217">Z tego względu zalecamy, aby w miarę rozsądnych, wspólnych rzeczowników, które opisują koncepcję, zostały przyjęte w silnym preferencjzie dla właściwych rzeczowników opisujących historię publikacji koncepcji.</span><span class="sxs-lookup"><span data-stu-id="90a92-217">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="90a92-218">Na przykład, pojedynczo kontrolowane operacje SWAP i podwójnie kontrolowane nie są często nazywane operacjami "Fredkin" i "Toffoli" w literaturze akademickiej, ale są one identyfikowane w Q # głównie jako `CSWAP` i `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="90a92-218">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="90a92-219">W obu przypadkach komentarze dokumentacji interfejsu API zawierają nazwy synonimów na podstawie odpowiednich rzeczowników wraz ze wszystkimi odpowiednimi cytatami.</span><span class="sxs-lookup"><span data-stu-id="90a92-219">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="90a92-220">Ta preferencja jest szczególnie ważna w przypadku, gdy pewne użycie właściwych rzeczowników będzie zawsze konieczne — Q # jest zgodna z tradycją ustawioną przez wiele klasycznych języków, na przykład i odwołuje się do typów `Bool` w odniesieniu do logiki logicznej, która jest z kolei nazywana w honorie wartości logicznej George.</span><span class="sxs-lookup"><span data-stu-id="90a92-220">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="90a92-221">Kilka koncepcji Quantum podobnie nazywa się w podobny sposób, łącznie z typem `Pauli` wbudowanym do języka Q #.</span><span class="sxs-lookup"><span data-stu-id="90a92-221">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="90a92-222">Minimalizując użycie właściwych rzeczowników, w których takie użycie nie jest niezbędne, zmniejszamy wpływ na to, gdzie nie można rozsądnie uniknąć odpowiednich rzeczowników.</span><span class="sxs-lookup"><span data-stu-id="90a92-222">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-223">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-223">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="90a92-224">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-224">We suggest:</span></span>

- <span data-ttu-id="90a92-225">Unikaj używania właściwych rzeczowników w nazwach.</span><span class="sxs-lookup"><span data-stu-id="90a92-225">Avoid the use of proper nouns in names.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-226">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-226">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="90a92-227">Konwersje typów</span><span class="sxs-lookup"><span data-stu-id="90a92-227">Type Conversions</span></span> ###

<span data-ttu-id="90a92-228">Ponieważ Q # jest silnie i statycznie wpisanym językiem, wartość jednego typu może być używana tylko jako wartość innego typu za pomocą jawnego wywołania funkcji konwersji typu.</span><span class="sxs-lookup"><span data-stu-id="90a92-228">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="90a92-229">Jest to w przeciwieństwie do języków, które umożliwiają niejawną zmianę typów wartości (np.: Promocja typu) lub poprzez rzutowanie.</span><span class="sxs-lookup"><span data-stu-id="90a92-229">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="90a92-230">W związku z tym funkcje konwersji typu odgrywają ważną rolę w opracowywaniu biblioteki Q # i składają się z jednej z najczęściej wykrytych decyzji dotyczących nazewnictwa.</span><span class="sxs-lookup"><span data-stu-id="90a92-230">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="90a92-231">Pamiętaj jednak, że ponieważ konwersje typów są zawsze _deterministyczne_, można je napisać jako funkcje i w związku z tym powyższym.</span><span class="sxs-lookup"><span data-stu-id="90a92-231">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="90a92-232">W szczególności sugerujemy, aby funkcje konwersji typów nigdy nie były nazwane jako czasowniki (np.: `ConvertToX`) lub parametrów przedpozycyjnych fraz (`ToX`), ale powinny być nazwane jako niezależne wyrażenia przymiotników wskazujące typy źródłowe i docelowe (`XAsY`).</span><span class="sxs-lookup"><span data-stu-id="90a92-232">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="90a92-233">Podczas wyświetlania listy typów tablicowych w nazwach funkcji konwersji typów zaleca się używanie skróconej `Arr`.</span><span class="sxs-lookup"><span data-stu-id="90a92-233">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="90a92-234">Z zablokowaniem wyjątkowej sytuacji zalecamy, aby wszystkie funkcje konwersji typów były nazwane przy użyciu `As`, aby można je było szybko zidentyfikować.</span><span class="sxs-lookup"><span data-stu-id="90a92-234">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-235">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-235">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="90a92-236">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-236">We suggest:</span></span>

- <span data-ttu-id="90a92-237">Jeśli funkcja konwertuje wartość typu `X` na wartość typu `Y`, użyj nazwy `AsY` lub `XAsY`.</span><span class="sxs-lookup"><span data-stu-id="90a92-237">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-238">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-238">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="90a92-239">Nazwa</span><span class="sxs-lookup"><span data-stu-id="90a92-239">Name</span></span> | <span data-ttu-id="90a92-240">Opis</span><span class="sxs-lookup"><span data-stu-id="90a92-240">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="90a92-241">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-241">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="90a92-242">Pozycja "do" powoduje wyrażenie orzeczenia, wskazujące operację, a nie funkcję.</span><span class="sxs-lookup"><span data-stu-id="90a92-242">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="90a92-243">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-243">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="90a92-244">Typ danych wejściowych nie jest wyczyszczony z nazwy funkcji.</span><span class="sxs-lookup"><span data-stu-id="90a92-244">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="90a92-245">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-245">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="90a92-246">Typy wejściowe i wyjściowe są wyświetlane w niewłaściwej kolejności.</span><span class="sxs-lookup"><span data-stu-id="90a92-246">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="90a92-247">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-247">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="90a92-248">Typy wejściowe i typy wyjściowe są jasne.</span><span class="sxs-lookup"><span data-stu-id="90a92-248">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="90a92-249">Nazwy prywatne lub wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="90a92-249">Private or Internal Names</span></span> ###

<span data-ttu-id="90a92-250">W wielu przypadkach nazwa jest przeznaczona wyłącznie do użytku wewnętrznego dla biblioteki lub projektu i nie jest zagwarantowanam elementem interfejsu API oferowanym przez bibliotekę.</span><span class="sxs-lookup"><span data-stu-id="90a92-250">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="90a92-251">Warto jasno wskazać, że jest to przypadek w przypadku nazywania funkcji i operacji, tak aby przypadkowe zależności w kodzie wewnętrznym były oczywiste.</span><span class="sxs-lookup"><span data-stu-id="90a92-251">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="90a92-252">Jeśli operacja lub funkcja nie jest przeznaczona do użytku bezpośredniego, ale powinna być używana przez pasujące zadanie, które działa przez częściową aplikację, rozważ użycie nazwy rozpoczynającej się od `_` dla możliwego do odłożenia.</span><span class="sxs-lookup"><span data-stu-id="90a92-252">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-253">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-253">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="90a92-254">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-254">We suggest:</span></span>

- <span data-ttu-id="90a92-255">Gdy funkcja, operacja lub typ zdefiniowany przez użytkownika nie jest częścią publicznego interfejsu API dla biblioteki lub programu Q #, należy się upewnić, że jego nazwa zaczyna się od znaku podkreślenia wiodącego (`_`).</span><span class="sxs-lookup"><span data-stu-id="90a92-255">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-256">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-256">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="90a92-257">Nazwa</span><span class="sxs-lookup"><span data-stu-id="90a92-257">Name</span></span> | <span data-ttu-id="90a92-258">Opis</span><span class="sxs-lookup"><span data-stu-id="90a92-258">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="90a92-259">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-259">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="90a92-260">`_` podkreślenia nie powinna pojawić się na końcu nazwy.</span><span class="sxs-lookup"><span data-stu-id="90a92-260">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="90a92-261">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-261">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="90a92-262">Podkreślenie `_` na początku jasno wskazuje, że ta operacja jest tylko do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="90a92-262">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="90a92-263">Variant</span><span class="sxs-lookup"><span data-stu-id="90a92-263">Variants</span></span> ###

<span data-ttu-id="90a92-264">Mimo że to ograniczenie może nie pogorszyć w przyszłych wersjach funkcji Q #, jest to gotowe do użycia w przypadku często grup powiązanych operacji lub funkcji, które są rozróżniane przez funktory ich dane wejściowe lub przez konkretne typy argumentów.</span><span class="sxs-lookup"><span data-stu-id="90a92-264">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="90a92-265">Te grupy można rozróżnić przy użyciu tej samej nazwy głównej, po której następuje jedna lub dwie litery wskazujące jej wariant.</span><span class="sxs-lookup"><span data-stu-id="90a92-265">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="90a92-266">Przedrostk</span><span class="sxs-lookup"><span data-stu-id="90a92-266">Suffix</span></span> | <span data-ttu-id="90a92-267">Znaczenie</span><span class="sxs-lookup"><span data-stu-id="90a92-267">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="90a92-268">Oczekiwano danych wejściowych do obsługi `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="90a92-268">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="90a92-269">Oczekiwano danych wejściowych do obsługi `Controlled`</span><span class="sxs-lookup"><span data-stu-id="90a92-269">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="90a92-270">Oczekiwano danych wejściowych do obsługi `Controlled` i `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="90a92-270">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="90a92-271">Dane wejściowe lub wejścia są typu `Int`</span><span class="sxs-lookup"><span data-stu-id="90a92-271">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="90a92-272">Dane wejściowe lub wejścia są typu `Double`</span><span class="sxs-lookup"><span data-stu-id="90a92-272">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="90a92-273">Dane wejściowe lub wejścia są typu `BigInt`</span><span class="sxs-lookup"><span data-stu-id="90a92-273">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-274">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-274">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="90a92-275">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-275">We suggest:</span></span>

- <span data-ttu-id="90a92-276">Jeśli funkcja lub operacja nie jest powiązana z żadną podobną funkcją lub operacji według typów i obsługi danych wejściowych Funktor, nie należy używać sufiksu.</span><span class="sxs-lookup"><span data-stu-id="90a92-276">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="90a92-277">Jeśli funkcja lub operacja jest powiązana z innymi podobnymi funkcjami lub operacjami przez typy i obsługę Funktor ich danych wejściowych, użyj sufiksów jak w powyższej tabeli, aby rozróżnić warianty.</span><span class="sxs-lookup"><span data-stu-id="90a92-277">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-278">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-278">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="90a92-279">Argumenty i zmienne</span><span class="sxs-lookup"><span data-stu-id="90a92-279">Arguments and Variables</span></span> ###

<span data-ttu-id="90a92-280">Kluczowy cel kodu Q # dla funkcji lub operacji ma na celu łatwe odczytywanie i zrozumienie.</span><span class="sxs-lookup"><span data-stu-id="90a92-280">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="90a92-281">Podobnie nazwy danych wejściowych i argumentów typu powinny komunikować się, w jaki sposób funkcja lub argument będą używane po podaniu.</span><span class="sxs-lookup"><span data-stu-id="90a92-281">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-282">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-282">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="90a92-283">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-283">We suggest:</span></span>

- <span data-ttu-id="90a92-284">Dla wszystkich nazw zmiennych i wejściowych Użyj `pascalCase` w silnym preferencjie, aby `CamelCase`, `snake_case`lub `ANGRY_CASE`.</span><span class="sxs-lookup"><span data-stu-id="90a92-284">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="90a92-285">Nazwy wejściowe powinny być opisowe; należy unikać jednej lub dwóch nazw liter, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="90a92-285">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="90a92-286">Operacje i funkcje akceptujące dokładnie jeden argument typu należy zauważyć, że argument typu przez `T`, gdy jego rola jest oczywista.</span><span class="sxs-lookup"><span data-stu-id="90a92-286">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="90a92-287">Jeśli funkcja lub operacja przyjmuje wiele argumentów typu lub Jeśli rola pojedynczego typu argumentu nie jest oczywista, należy rozważyć użycie krótkiego wyrazu z prefiksem `T` (np.: `TOutput`) dla każdego typu.</span><span class="sxs-lookup"><span data-stu-id="90a92-287">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="90a92-288">Nie dołączaj nazw typów w nazwach argumentów i zmiennych; te informacje mogą być udostępniane przez środowisko deweloperskie.</span><span class="sxs-lookup"><span data-stu-id="90a92-288">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="90a92-289">Należy zauważyć typy skalarne według ich nazw literałów (`flagQubit`) i typów tablicowych w liczbie mnogiej (`measResults`).</span><span class="sxs-lookup"><span data-stu-id="90a92-289">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="90a92-290">W szczególności dla tablic qubits należy rozważyć określenie takich typów przez `Register`, gdzie nazwa odwołuje się do sekwencji qubits, które są ściśle powiązane w jakiś sposób.</span><span class="sxs-lookup"><span data-stu-id="90a92-290">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="90a92-291">Zmienne używane jako indeksy w tablicach powinny rozpoczynać się od `idx` i powinny być pojedyncze (np.: `things[idxThing]`).</span><span class="sxs-lookup"><span data-stu-id="90a92-291">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="90a92-292">W szczególności zdecydowanie Unikaj używania nazw zmiennych o pojedynczej literze jako indeksów; Rozważ użycie `idx` w minimalnym czasie.</span><span class="sxs-lookup"><span data-stu-id="90a92-292">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="90a92-293">Zmienne używane do przechowywania długości tablic powinny rozpoczynać się od `n` i powinny być w liczbie mnogiej (np.: `nThings`).</span><span class="sxs-lookup"><span data-stu-id="90a92-293">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-294">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-294">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="90a92-295">Typ zdefiniowany przez użytkownika o nazwie Items</span><span class="sxs-lookup"><span data-stu-id="90a92-295">User Defined Type Named Items</span></span> ###

<span data-ttu-id="90a92-296">Nazwane elementy w typach zdefiniowanych przez użytkownika powinny być nazwane jako `CamelCase`, nawet w danych wejściowych dla konstruktorów UDT.</span><span class="sxs-lookup"><span data-stu-id="90a92-296">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="90a92-297">Ułatwia to łatwe oddzielenie nazwanych elementów od odwołań do zmiennych w zakresie lokalnie podczas korzystania z notacji metody dostępu (np.: `callable::Apply`) lub notacji kopiowania i aktualizacji (`set arr w/= Data <- newData`).</span><span class="sxs-lookup"><span data-stu-id="90a92-297">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-298">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-298">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="90a92-299">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-299">We suggest:</span></span>

- <span data-ttu-id="90a92-300">Nazwane elementy w konstruktorach UDT powinny mieć nazwę `CamelCase`; oznacza to, że powinny zaczynać się od początkowej wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="90a92-300">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="90a92-301">Nazwane elementy, które są rozpoznawane jako operacje, powinny być nazwane jako etapy zleceń.</span><span class="sxs-lookup"><span data-stu-id="90a92-301">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="90a92-302">Nazwane elementy, które nie są rozpoznawane do operacji, powinny być nazwane jako frazy rzeczowników.</span><span class="sxs-lookup"><span data-stu-id="90a92-302">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="90a92-303">Dla UDTs, które zawijają operacje, należy zdefiniować pojedynczy nazwany element o nazwie `Apply`.</span><span class="sxs-lookup"><span data-stu-id="90a92-303">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-304">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-304">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="90a92-305">Fragment kodu</span><span class="sxs-lookup"><span data-stu-id="90a92-305">Snippet</span></span> | <span data-ttu-id="90a92-306">Opis</span><span class="sxs-lookup"><span data-stu-id="90a92-306">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="90a92-307">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-307">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="90a92-308">Nazwa `Apply` jest wyrażeniem, które jest sformatowane w `CamelCase`, sugerując, że nazwany element jest operacją.</span><span class="sxs-lookup"><span data-stu-id="90a92-308">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="90a92-309">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-309">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="90a92-310">Nazwane elementy powinny rozpoczynać się od początkowej wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="90a92-310">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="90a92-311">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-311">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="90a92-312">Nazwane elementy, które rozwiązują funkcje, powinny być nazwane jako frazy rzeczownikowe, a nie jako wyrażenia czasownikowe.</span><span class="sxs-lookup"><span data-stu-id="90a92-312">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="90a92-313">Konwencje wejściowe</span><span class="sxs-lookup"><span data-stu-id="90a92-313">Input Conventions</span></span> ##

<span data-ttu-id="90a92-314">Gdy deweloper wywołuje operację lub funkcję, różne dane wejściowe do tej operacji lub funkcji muszą być określone w określonej kolejności, zwiększając obciążenie poznawcze, które są używane przez twarzy dla deweloperów.</span><span class="sxs-lookup"><span data-stu-id="90a92-314">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="90a92-315">W szczególności zadanie zapamiętywania kolejności danych wejściowych jest często rozpraszane z zadania: Programowanie implementacji algorytmu Quantum.</span><span class="sxs-lookup"><span data-stu-id="90a92-315">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="90a92-316">Chociaż rozbudowana obsługa środowiska IDE może w dużym stopniu ograniczyć, dobry projekt i przestrzeganie wspólnych Konwencji może również pomóc w zminimalizowaniu obciążenia poznawczego narzuconego przez interfejs API.</span><span class="sxs-lookup"><span data-stu-id="90a92-316">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="90a92-317">Tam, gdzie to możliwe, może być pomocne zmniejszenie liczby wejść oczekiwanych przez operację lub funkcję, dzięki czemu rola każdego danych wejściowych jest bardziej oczywista bezpośrednio dla deweloperów wywołujących tę operację lub funkcję, a także do deweloperów odczytujących ten kod później.</span><span class="sxs-lookup"><span data-stu-id="90a92-317">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="90a92-318">Szczególnie gdy nie jest możliwe lub uzasadnione zmniejszanie liczby argumentów do operacji lub funkcji, ważne jest, aby mieć spójne porządkowanie, które minimalizuje nieoczekiwane działanie użytkownika podczas przewidywania kolejności danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="90a92-318">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="90a92-319">Zalecamy konwencje określania danych wejściowych, które w znacznym stopniu wynikają z działania częściowej aplikacji jako generalizacji currying f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="90a92-319">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="90a92-320">W związku z tym, częściowe stosowanie pierwszych argumentów powinno skutkować wywoływaniem, który jest przydatny we własnym imieniu, gdy jest to uzasadnione.</span><span class="sxs-lookup"><span data-stu-id="90a92-320">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="90a92-321">Zgodnie z tą zasadą należy rozważyć użycie następującej kolejności argumentów:</span><span class="sxs-lookup"><span data-stu-id="90a92-321">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="90a92-322">Klasyczne argumenty, które nie można wywołać, takie jak kąty, wektory uprawnień itp.</span><span class="sxs-lookup"><span data-stu-id="90a92-322">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="90a92-323">Wywoływane argumenty (funkcje i argumenty).</span><span class="sxs-lookup"><span data-stu-id="90a92-323">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="90a92-324">Jeśli obie funkcje i operacje są traktowane jako argumenty, Rozważ umieszczenie operacji po funkcjach.</span><span class="sxs-lookup"><span data-stu-id="90a92-324">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="90a92-325">Kolekcje działały na podstawie wywoływanych argumentów w podobny sposób do `Map`, `Iter`, `Enumerate`i `Fold`.</span><span class="sxs-lookup"><span data-stu-id="90a92-325">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="90a92-326">Argumenty qubit używane jako formanty.</span><span class="sxs-lookup"><span data-stu-id="90a92-326">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="90a92-327">Argumenty qubit używane jako elementy docelowe.</span><span class="sxs-lookup"><span data-stu-id="90a92-327">Qubit arguments used as targets.</span></span>

<span data-ttu-id="90a92-328">Rozważmy `ApplyPhaseEstimationIteration` operacji do użycia w ocenie fazy, która ma kąt i Oracle, przekazuje kąt do `Rz` zmodyfikowany przez tablicę różnych czynników skalowania, a następnie kontroluje aplikacje firmy Oracle.</span><span class="sxs-lookup"><span data-stu-id="90a92-328">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="90a92-329">Firma Microsoft chce, aby dane wejściowe były `ApplyPhaseEstimationIteration` w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="90a92-329">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

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
<span data-ttu-id="90a92-330">W specjalnym przypadku minimalizowania niespodziewania niektóre funkcje i operacje naśladowania zachowania wbudowanej `Adjoint` funktory i `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="90a92-330">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="90a92-331">Na przykład `ControlledOnInt<'T>` ma typ `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, tak że `ControlledOnInt<Qubit[]>(5, _)` działa podobnie jak `Controlled` Funktor, ale na stanie, w którym Rejestr sterowania reprezentuje stan $ \ket{5} = \ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="90a92-331">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="90a92-332">W ten sposób deweloper oczekuje, że dane wejściowe `ControlledOnInt` umieścić w ostatniej kolejności, a wynikowa operacja przyjmuje jako `(Qubit[], 'T)` danych wejściowych---taką samą kolejność, jak dane wyjściowe `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="90a92-332">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-333">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-333">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="90a92-334">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-334">We suggest:</span></span>

- <span data-ttu-id="90a92-335">Użyj kolejności danych wejściowych spójnej z użyciem częściowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="90a92-335">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="90a92-336">Użyj kolejności danych wejściowych spójnych z wbudowanym funktory.</span><span class="sxs-lookup"><span data-stu-id="90a92-336">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="90a92-337">Umieść wszystkie klasyczne dane wejściowe przed wszelkimi danymi wejściowymi Quantum.</span><span class="sxs-lookup"><span data-stu-id="90a92-337">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-338">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-338">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="90a92-339">Konwencje dokumentacji</span><span class="sxs-lookup"><span data-stu-id="90a92-339">Documentation Conventions</span></span> ##

<span data-ttu-id="90a92-340">Język Q # umożliwia dołączanie dokumentacji do operacji, funkcji i typów zdefiniowanych przez użytkownika za pomocą specjalnie sformatowanych komentarzy do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="90a92-340">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="90a92-341">Oznacza to, że komentarze w dokumentacji są małymi ukośnikami (`///`), ale są to małe dokumenty z [DocFXą](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) , które mogą być używane do opisywania przeznaczenia każdej operacji, funkcji i typu zdefiniowanego przez użytkownika, jakie dane muszą oczekiwać i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="90a92-341">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="90a92-342">Kompilator dostarczany z zestawem SDK Quantum wyodrębnia te komentarze i korzysta z nich, aby pomóc w poziomego złożenia dokumentacji podobnej do https://docs.microsoft.com/quantum.</span><span class="sxs-lookup"><span data-stu-id="90a92-342">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="90a92-343">Podobnie serwer językowy dostarczony z zestawem Quantum Development Kit używa tych komentarzy, aby zapewnić użytkownikom Pomoc po umieszczeniu wskaźnika myszy na symbolach w kodzie Q.</span><span class="sxs-lookup"><span data-stu-id="90a92-343">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="90a92-344">Korzystanie z komentarzy do dokumentacji może ułatwić użytkownikom zrozumienie kodu przez udostępnienie przydatnego odwołania do szczegółów, które nie są łatwo wyrażone przy użyciu innych konwencji zawartych w tym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="90a92-344">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="90a92-345">
    [Informacje o składni komentarzy do dokumentacji](xref:microsoft.quantum.language.statements#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="90a92-345">
    [Documentation comment syntax reference](xref:microsoft.quantum.language.statements#documentation-comments)
</span></span></div>

<span data-ttu-id="90a92-346">Aby efektywnie korzystać z tej funkcji w celu ułatwienia użytkownikom, zalecamy zachowywanie kilku rzeczy podczas pisania komentarzy do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="90a92-346">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-347">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-347">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="90a92-348">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-348">We suggest:</span></span>

- <span data-ttu-id="90a92-349">Każda funkcja publiczna, operacja i typ zdefiniowany przez użytkownika powinny być bezpośrednio poprzedzone komentarzem do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="90a92-349">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="90a92-350">Co najmniej każdy komentarz dokumentacji powinien zawierać następujące sekcje:</span><span class="sxs-lookup"><span data-stu-id="90a92-350">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="90a92-351">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="90a92-351">Summary</span></span>
    - <span data-ttu-id="90a92-352">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="90a92-352">Input</span></span>
    - <span data-ttu-id="90a92-353">Dane wyjściowe (jeśli dotyczy)</span><span class="sxs-lookup"><span data-stu-id="90a92-353">Output (if applicable)</span></span>
- <span data-ttu-id="90a92-354">Upewnij się, że wszystkie podsumowania są dwa zdania lub mniej.</span><span class="sxs-lookup"><span data-stu-id="90a92-354">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="90a92-355">Jeśli potrzebujesz więcej miejsca, Udostępnij sekcję `# Description` bezpośrednio po `# Summary` z pełnymi szczegółami.</span><span class="sxs-lookup"><span data-stu-id="90a92-355">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="90a92-356">W odpowiednich przypadkach nie należy uwzględniać obliczeń matematycznych, ponieważ nie wszyscy klienci obsługują notację TeX w podsumowaniu.</span><span class="sxs-lookup"><span data-stu-id="90a92-356">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="90a92-357">Należy pamiętać, że podczas pisania dokumentów Prose (np. TeX lub promocji) może być zalecane użycie dłuższych długości wierszy.</span><span class="sxs-lookup"><span data-stu-id="90a92-357">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="90a92-358">Podaj wszystkie odpowiednie wyrażenia matematyczne w sekcji `# Description`.</span><span class="sxs-lookup"><span data-stu-id="90a92-358">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="90a92-359">Podczas opisywania danych wejściowych nie należy powtarzać typów poszczególnych danych wejściowych, ponieważ mogą one zostać wywnioskowane przez kompilator i ryzyko wprowadzające niespójność.</span><span class="sxs-lookup"><span data-stu-id="90a92-359">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="90a92-360">Podaj odpowiednie przykłady, z których każda znajduje się w oddzielnej sekcji `# Example`.</span><span class="sxs-lookup"><span data-stu-id="90a92-360">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="90a92-361">Zwięźle opisz każdy przykład przed listą kodów.</span><span class="sxs-lookup"><span data-stu-id="90a92-361">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="90a92-362">Pocite wszystkie odpowiednie Publikacje akademickie (np.: dokumenty, postępowania, wpisy w blogu i implementacje alternatywne) w sekcji `# References` jako listę punktowaną.</span><span class="sxs-lookup"><span data-stu-id="90a92-362">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="90a92-363">Upewnij się, że w miarę możliwości wszystkie linki cytatu mają stałe i niezmienne identyfikatory (DOIs lub z wersjami arXiv).</span><span class="sxs-lookup"><span data-stu-id="90a92-363">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="90a92-364">Gdy operacja lub funkcja jest powiązana z innymi operacjami lub funkcjami według wariantów Funktor, Utwórz listę innych wariantów jako punktorów w sekcji `# See Also`.</span><span class="sxs-lookup"><span data-stu-id="90a92-364">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="90a92-365">Pozostaw pustą linię komentarza między sekcjami poziom-1 (`/// #`), ale nie pozostawiaj pustego wiersza między sekcjami poziom-2 (`/// ##`).</span><span class="sxs-lookup"><span data-stu-id="90a92-365">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-366">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-366">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="90a92-367">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-367">☑</span></span> ####

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

***

## <a name="formatting-conventions"></a><span data-ttu-id="90a92-368">Konwencje formatowania</span><span class="sxs-lookup"><span data-stu-id="90a92-368">Formatting Conventions</span></span> ##

<span data-ttu-id="90a92-369">Oprócz powyższych sugestii pomocne może być wprowadzenie kodu jako czytelnego do używania spójnych reguł formatowania.</span><span class="sxs-lookup"><span data-stu-id="90a92-369">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="90a92-370">Takie reguły formatowania według natury mają być nieco dowolne i silnie do osobistych estetycznych.</span><span class="sxs-lookup"><span data-stu-id="90a92-370">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="90a92-371">Niemniej zalecamy utrzymywanie spójnego zestawu Konwencji formatowania w grupie współpracowników i szczególnie w przypadku dużych projektów Q #, takich jak zestaw Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="90a92-371">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="90a92-372">Te reguły mogą być automatycznie stosowane przy użyciu narzędzia formatowania zintegrowanego z kompilatorem Q #.</span><span class="sxs-lookup"><span data-stu-id="90a92-372">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="90a92-373">Wskazówki</span><span class="sxs-lookup"><span data-stu-id="90a92-373">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="90a92-374">Sugerujemy:</span><span class="sxs-lookup"><span data-stu-id="90a92-374">We suggest:</span></span>

- <span data-ttu-id="90a92-375">Używaj czterech spacji zamiast kart do przenoszenia.</span><span class="sxs-lookup"><span data-stu-id="90a92-375">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="90a92-376">Na przykład w VS Code:</span><span class="sxs-lookup"><span data-stu-id="90a92-376">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="90a92-377">Zawijanie wierszy o 79 znaków, gdy jest to uzasadnione.</span><span class="sxs-lookup"><span data-stu-id="90a92-377">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="90a92-378">Używaj spacji wokół operatorów binarnych.</span><span class="sxs-lookup"><span data-stu-id="90a92-378">Use spaces around binary operators.</span></span>
- <span data-ttu-id="90a92-379">Używaj spacji po obu stronach dwukropków używanych do adnotacji typu.</span><span class="sxs-lookup"><span data-stu-id="90a92-379">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="90a92-380">Użyj pojedynczej spacji po przecinkach używanych w literałach tablicowych i krotek (np. w danych wejściowych do funkcji i operacji).</span><span class="sxs-lookup"><span data-stu-id="90a92-380">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="90a92-381">Nie używaj spacji po nazwach funkcji, operacji lub UDT lub po `@` w deklaracjach atrybutów.</span><span class="sxs-lookup"><span data-stu-id="90a92-381">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="90a92-382">Każda deklaracja atrybutu powinna znajdować się w osobnym wierszu.</span><span class="sxs-lookup"><span data-stu-id="90a92-382">Each attribute declaration should be on its own line.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="90a92-383">Przykłady</span><span class="sxs-lookup"><span data-stu-id="90a92-383">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="90a92-384">Fragment kodu</span><span class="sxs-lookup"><span data-stu-id="90a92-384">Snippet</span></span> | <span data-ttu-id="90a92-385">Opis</span><span class="sxs-lookup"><span data-stu-id="90a92-385">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="90a92-386">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-386">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="90a92-387">Używaj spacji wokół operatorów binarnych.</span><span class="sxs-lookup"><span data-stu-id="90a92-387">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="90a92-388">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-388">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="90a92-389">Używaj spacji wokół dwukropka adnotacji typu.</span><span class="sxs-lookup"><span data-stu-id="90a92-389">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="90a92-390">☑</span><span class="sxs-lookup"><span data-stu-id="90a92-390">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="90a92-391">Elementy w spójnej kolekcji są poprawnie wprowadzane do czytelności.</span><span class="sxs-lookup"><span data-stu-id="90a92-391">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="90a92-392">☒</span><span class="sxs-lookup"><span data-stu-id="90a92-392">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="90a92-393">Spacje powinny być pomijane po nazwach funkcji, operacji lub UDT.</span><span class="sxs-lookup"><span data-stu-id="90a92-393">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***


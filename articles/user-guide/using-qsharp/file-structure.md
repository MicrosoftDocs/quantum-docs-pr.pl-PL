---
title: 'Struktura pliku Q #'
description: 'Opisuje strukturę i składnię pliku Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: 54efc2b9d6b7f1956cdf9a335c88620b29f7729d
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884185"
---
# <a name="q-file-structure"></a><span data-ttu-id="89aa2-103">Struktura pliku Q #</span><span class="sxs-lookup"><span data-stu-id="89aa2-103">Q# File Structure</span></span>

<span data-ttu-id="89aa2-104">Plik Q # składa się z sekwencji *nazw deklaracji*.</span><span class="sxs-lookup"><span data-stu-id="89aa2-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="89aa2-105">Każda deklaracja przestrzeni nazw zawiera deklaracje dla typów, operacji i funkcji zdefiniowanych przez użytkownika, a także może zawierać dowolną liczbę poszczególnych typów deklaracji i w dowolnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="89aa2-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="89aa2-106">Aby uzyskać więcej informacji na temat deklaracji w przestrzeni nazw, zobacz Typy, [operacje](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)i [funkcje](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [zdefiniowane przez użytkownika](xref:microsoft.quantum.guide.types#user-defined-types).</span><span class="sxs-lookup"><span data-stu-id="89aa2-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="89aa2-107">Jedynym tekstem, który może występować poza deklaracją przestrzeni nazw, jest komentarz.</span><span class="sxs-lookup"><span data-stu-id="89aa2-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="89aa2-108">W szczególności Komentarze do dokumentacji dla przestrzeni nazw poprzedzają deklarację.</span><span class="sxs-lookup"><span data-stu-id="89aa2-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="89aa2-109">Aby uzyskać więcej informacji, zobacz [Komentarze do dokumentacji](#documentation-comments) w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="89aa2-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="89aa2-110">Deklaracje przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="89aa2-110">Namespace Declarations</span></span>

<span data-ttu-id="89aa2-111">Plik Q # ma zwykle tylko jedną deklarację przestrzeni nazw, ale może mieć wartość None (i być pusty lub zawierać komentarze) lub może zawierać wiele przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="89aa2-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="89aa2-112">Deklaracje przestrzeni nazw nie mogą być zagnieżdżane.</span><span class="sxs-lookup"><span data-stu-id="89aa2-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="89aa2-113">Można zadeklarować tę samą przestrzeń nazw w wielu plikach Q #, które są kompilowane ze sobą, o ile nie ma deklaracji typu, operacji lub funkcji o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="89aa2-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="89aa2-114">W szczególności nie można zdefiniować tego samego typu w tej samej przestrzeni nazw w wielu plikach, nawet jeśli deklaracje są identyczne.</span><span class="sxs-lookup"><span data-stu-id="89aa2-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="89aa2-115">Deklaracja przestrzeni nazw składa się ze słowa kluczowego `namespace` , po którym następuje nazwa przestrzeni nazw i deklaracji zawartych w przestrzeni nazw ujętej w nawiasy klamrowe `{ }` .</span><span class="sxs-lookup"><span data-stu-id="89aa2-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="89aa2-116">Nazwy przestrzeni nazw są zgodne ze wzorcem .NET sekwencji jednego lub więcej symboli dozwolonych oddzielonych kropkami `.` .</span><span class="sxs-lookup"><span data-stu-id="89aa2-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="89aa2-117">Na przykład `MyQuantumStuff` i `Microsoft.Quantum.Intrinsic` są prawidłowymi nazwami przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="89aa2-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="89aa2-118">Zgodnie z Konwencją wielkie litery symboli w nazwie przestrzeni nazw nie są jednak wymagane.</span><span class="sxs-lookup"><span data-stu-id="89aa2-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="89aa2-119">Odwołania do typów lub wartości, które zostały zgłoszone w dalszej postaci w pliku, są prawidłowo rozwiązywane; nie ma potrzeby składania deklaracji typu, operacji lub funkcji przed odwołaniem do niej.</span><span class="sxs-lookup"><span data-stu-id="89aa2-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="89aa2-120">Otwarte dyrektywy</span><span class="sxs-lookup"><span data-stu-id="89aa2-120">Open Directives</span></span>

<span data-ttu-id="89aa2-121">W bloku przestrzeni nazw, należy użyć `open` dyrektywy do zaimportowania wszystkich typów i wywoływanych deklaracji zadeklarowanych w określonym obszarze nazw i odwoływania się do nich według ich nazwy niekwalifikowanej.</span><span class="sxs-lookup"><span data-stu-id="89aa2-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="89aa2-122">Taka `open` dyrektywa składa się ze `open` słowa kluczowego, po którym następuje przestrzeń nazw, która ma zostać otwarta i kończąca się średnikiem.</span><span class="sxs-lookup"><span data-stu-id="89aa2-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="89aa2-123">Wszystkie `open` dyrektywy muszą występować przed dowolnymi `function` `operation` `newtype` deklaracjami w bloku przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="89aa2-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="89aa2-124">Opcjonalnie można zdefiniować krótką nazwę otwartej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="89aa2-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="89aa2-125">Jeśli zdefiniowano krótką nazwę, należy zakwalifikować wszystkie elementy z tej przestrzeni nazw według zdefiniowanej krótkiej nazwy.</span><span class="sxs-lookup"><span data-stu-id="89aa2-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="89aa2-126">Na przykład uwzględniając następującą deklarację przestrzeni nazw i otwarte dyrektywy,</span><span class="sxs-lookup"><span data-stu-id="89aa2-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="89aa2-127">Jeśli zadeklarowana operacja używa operacji `Op` z `Microsoft.Quantum.Intrinsic` , należy wywołać ją po prostu przy użyciu `Op` .</span><span class="sxs-lookup"><span data-stu-id="89aa2-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="89aa2-128">Aby jednak wywołać określoną funkcję `Fn` z `Microsoft.Quantum.Math` , należy wywołać ją przy użyciu polecenia `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="89aa2-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="89aa2-129">`open`Dyrektywa ma zastosowanie do całego bloku przestrzeni nazw w pliku.</span><span class="sxs-lookup"><span data-stu-id="89aa2-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="89aa2-130">W związku z tym, jeśli zdefiniujesz dodatkową przestrzeń nazw w tym samym pliku Q # jak `NS` wcześniej, wszystkie operacje/funkcje/typy zdefiniowane w drugim obszarze nazw nie będą miały dostępu do niczego z `Microsoft.Quantum.Intrinsic` lub, `Microsoft.Quantum.Math` chyba że zostaną powtórzone otwarte dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="89aa2-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="89aa2-131">Aby odwołać się do typu lub możliwego do odłożenia zdefiniowanego w innej przestrzeni nazw, która *nie* jest otwarta w bieżącym obszarze nazw, należy odwołać się do niej przy użyciu w pełni kwalifikowanej nazwy.</span><span class="sxs-lookup"><span data-stu-id="89aa2-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="89aa2-132">Na przykład, dana operacja o nazwie `Op` z `X.Y` przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="89aa2-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="89aa2-133">Należy odwołać się do niego za pomocą jego w pełni kwalifikowanej nazwy `X.Y.Op` , chyba że `X.Y` przestrzeń nazw została otwarta wcześniej w bieżącym bloku.</span><span class="sxs-lookup"><span data-stu-id="89aa2-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="89aa2-134">Nawet jeśli `X` przestrzeń nazw jest otwarta, nie można odwołać się do operacji jako `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="89aa2-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="89aa2-135">Jeśli zdefiniowano krótką nazwę `Z` dla `X.Y` w tej przestrzeni nazw i pliku, należy odwołać się do `Op` `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="89aa2-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="89aa2-136">Zwykle lepiej jest dołączyć przestrzeń nazw przy użyciu `open` dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="89aa2-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="89aa2-137">Użycie w pełni kwalifikowanej nazwy jest wymagane, jeśli dwie przestrzenie nazw definiują konstrukcje o tej samej nazwie, a bieżące źródło używa konstrukcji z obu tych typów.</span><span class="sxs-lookup"><span data-stu-id="89aa2-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="89aa2-138">Pytania i odpowiedzi są zgodne z tymi samymi regułami dotyczącymi nazewnictwa w innych językach .NET.</span><span class="sxs-lookup"><span data-stu-id="89aa2-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="89aa2-139">Jednak polecenie Q # nie obsługuje względnych odwołań do przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="89aa2-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="89aa2-140">Na przykład jeśli przestrzeń nazw `a.b` jest otwarta, odwołanie do operacji o nazwie nie `c.d` jest rozpoznawane jako operacja o pełnej nazwie *not* `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="89aa2-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="89aa2-141">Formatowanie</span><span class="sxs-lookup"><span data-stu-id="89aa2-141">Formatting</span></span>

<span data-ttu-id="89aa2-142">Większość instrukcji i dyrektyw Q # kończy się średnikiem, `;` .</span><span class="sxs-lookup"><span data-stu-id="89aa2-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="89aa2-143">Instrukcje i deklaracje, takie jak `for` i `operation` kończące się blokiem instrukcji (patrz Poniższa sekcja) nie wymagają kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="89aa2-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="89aa2-144">Każdy opis instrukcji wskazuje, czy jest wymagany średnik kończący.</span><span class="sxs-lookup"><span data-stu-id="89aa2-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="89aa2-145">Instrukcje, takie jak wyrażenia, deklaracje i dyrektywy, można rozdzielić między wiele wierszy.</span><span class="sxs-lookup"><span data-stu-id="89aa2-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="89aa2-146">Unikaj umieszczania wielu instrukcji w pojedynczym wierszu.</span><span class="sxs-lookup"><span data-stu-id="89aa2-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="89aa2-147">Bloki instrukcji</span><span class="sxs-lookup"><span data-stu-id="89aa2-147">Statement Blocks</span></span>

<span data-ttu-id="89aa2-148">Instrukcje Q # są pogrupowane w bloki instrukcji, które są zawarte w nawiasach klamrowych `{ }` .</span><span class="sxs-lookup"><span data-stu-id="89aa2-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="89aa2-149">Blok instrukcji rozpoczyna się od otwarcia `{` i kończącego się zamykaniem `}` .</span><span class="sxs-lookup"><span data-stu-id="89aa2-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="89aa2-150">Blok instrukcji, który jest leksykalny w innym bloku, jest traktowany jako podblok bloku zawierającego; bloki zawierające i podrzędne są również nazywane blokami zewnętrznymi i wewnętrznymi.</span><span class="sxs-lookup"><span data-stu-id="89aa2-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="89aa2-151">Komentarze</span><span class="sxs-lookup"><span data-stu-id="89aa2-151">Comments</span></span>

<span data-ttu-id="89aa2-152">Komentarze zaczynają się od dwóch ukośników `//` i są kontynuowane do końca wiersza.</span><span class="sxs-lookup"><span data-stu-id="89aa2-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="89aa2-153">Komentarz może pojawić się w dowolnym miejscu w pliku źródłowym Q #.</span><span class="sxs-lookup"><span data-stu-id="89aa2-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="89aa2-154">Komentarze dokumentacji</span><span class="sxs-lookup"><span data-stu-id="89aa2-154">Documentation Comments</span></span>

<span data-ttu-id="89aa2-155">Komentarze zaczynające się od trzech ukośników, `///` są traktowane specjalnie przez kompilator, gdy są wyświetlane bezpośrednio przed przestrzenią nazw, operacją, specjalizacją, funkcją lub definicją typu.</span><span class="sxs-lookup"><span data-stu-id="89aa2-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="89aa2-156">W takim przypadku kompilator traktuje je jako dokumentację dla zdefiniowanego typu wywoływanego lub zdefiniowanego przez użytkownika, tak samo jak w przypadku innych języków .NET.</span><span class="sxs-lookup"><span data-stu-id="89aa2-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="89aa2-157">W `///` komentarzach tekst, który ma być wyświetlany jako część dokumentacji interfejsu API, jest sformatowany jako [promocji](https://daringfireball.net/projects/markdown/syntax), z różnymi częściami dokumentacji wskazywanych przez nagłówki o specjalnie określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="89aa2-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="89aa2-158">W obszarze promocji Użyj `@"<ref target>"` rozszerzenia, aby wykonać operacje między odwołaniami, funkcje i typy zdefiniowane przez użytkownika w Q #.</span><span class="sxs-lookup"><span data-stu-id="89aa2-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="89aa2-159">Zamień na w `<ref target>` pełni kwalifikowaną nazwę obiektu kodu, do którego istnieje odwołanie.</span><span class="sxs-lookup"><span data-stu-id="89aa2-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="89aa2-160">Różne aparaty dokumentacji mogą również obsługiwać dodatkowe rozszerzenia promocji.</span><span class="sxs-lookup"><span data-stu-id="89aa2-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="89aa2-161">Przykład:</span><span class="sxs-lookup"><span data-stu-id="89aa2-161">For example:</span></span>

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="89aa2-162">Następujące nazwy są prawidłowe jako nagłówki komentarzy dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="89aa2-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="89aa2-163">**Podsumowanie**: krótkie podsumowanie zachowania funkcji lub operacji lub celu typu.</span><span class="sxs-lookup"><span data-stu-id="89aa2-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="89aa2-164">Pierwszy akapit podsumowania jest używany na potrzeby informacji o aktywowaniu.</span><span class="sxs-lookup"><span data-stu-id="89aa2-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="89aa2-165">Powinien być zwykły tekst.</span><span class="sxs-lookup"><span data-stu-id="89aa2-165">It should be plain text.</span></span>
- <span data-ttu-id="89aa2-166">**Opis**: Opis zachowania funkcji lub operacji lub celu typu.</span><span class="sxs-lookup"><span data-stu-id="89aa2-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="89aa2-167">Razem podsumowanie i opis tworzą wygenerowany plik dokumentacji dla funkcji, operacji lub typu.</span><span class="sxs-lookup"><span data-stu-id="89aa2-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="89aa2-168">Opis obsługuje symbole i równania sformatowane w wierszu.</span><span class="sxs-lookup"><span data-stu-id="89aa2-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="89aa2-169">**Dane wejściowe**: Opis krotki wejściowej dla operacji lub funkcji.</span><span class="sxs-lookup"><span data-stu-id="89aa2-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="89aa2-170">Może zawierać dodatkowe podsekcje promocji wskazujące każdy element krotki wejściowej.</span><span class="sxs-lookup"><span data-stu-id="89aa2-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="89aa2-171">**Dane wyjściowe**: Opis krotki zwracanej przez operację lub funkcję.</span><span class="sxs-lookup"><span data-stu-id="89aa2-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="89aa2-172">**Parametry typu**: pusta sekcja, która zawiera jedną dodatkową podsekcję dla każdego parametru typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="89aa2-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="89aa2-173">**Przykład**: krótki przykład operacji, funkcji lub typu w użyciu.</span><span class="sxs-lookup"><span data-stu-id="89aa2-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="89aa2-174">**Uwagi**: różne Prose opisujące aspekt operacji, funkcji lub typu.</span><span class="sxs-lookup"><span data-stu-id="89aa2-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="89aa2-175">**Zobacz również**: Lista w pełni kwalifikowanych nazw wskazujących powiązane funkcje, operacje lub typy zdefiniowane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="89aa2-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="89aa2-176">**Odwołania**: lista odwołań i cytatów dla udokumentowanego elementu.</span><span class="sxs-lookup"><span data-stu-id="89aa2-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="89aa2-177">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="89aa2-177">Next steps</span></span>

<span data-ttu-id="89aa2-178">Informacje o [operacjach i funkcjach](xref:microsoft.quantum.guide.operationsfunctions) w usłudze Q #.</span><span class="sxs-lookup"><span data-stu-id="89aa2-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>
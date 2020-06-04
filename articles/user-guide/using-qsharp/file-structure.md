---
title: 'Struktura pliku Q #'
description: 'Opisuje strukturę i składnię pliku Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327462"
---
# <a name="q-file-structure"></a><span data-ttu-id="fdb50-103">Struktura pliku Q #</span><span class="sxs-lookup"><span data-stu-id="fdb50-103">Q# File Structure</span></span>

<span data-ttu-id="fdb50-104">Każda operacja Q #, funkcja i typ zdefiniowany przez użytkownika są zdefiniowane w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="fdb50-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="fdb50-105">Plik Q # składa się z sekwencji *nazw deklaracji*.</span><span class="sxs-lookup"><span data-stu-id="fdb50-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="fdb50-106">Każda deklaracja przestrzeni nazw zawiera deklaracje dla typów, operacji i funkcji zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fdb50-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="fdb50-107">Deklaracja przestrzeni nazw może zawierać dowolną liczbę typów deklaracji i w dowolnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="fdb50-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="fdb50-108">Skorzystaj z poniższych linków, aby uzyskać więcej informacji na temat deklarowania typów, [operacji](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)i [funkcji](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [zdefiniowanych przez użytkownika](xref:microsoft.quantum.guide.types#user-defined-types)w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="fdb50-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="fdb50-109">Jedynym tekstem, który może występować poza deklaracją przestrzeni nazw, jest komentarz.</span><span class="sxs-lookup"><span data-stu-id="fdb50-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="fdb50-110">W szczególności Komentarze do dokumentacji (więcej szczegółów poniżej) dla przestrzeni nazw poprzedzają deklarację.</span><span class="sxs-lookup"><span data-stu-id="fdb50-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="fdb50-111">Deklaracje przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="fdb50-111">Namespace Declarations</span></span>

<span data-ttu-id="fdb50-112">Plik Q # zazwyczaj ma dokładnie jedną deklarację przestrzeni nazw, ale może mieć wartość None (i być pusty lub zawierać komentarze) lub może zawierać wiele przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="fdb50-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="fdb50-113">Deklaracje przestrzeni nazw nie mogą być zagnieżdżane.</span><span class="sxs-lookup"><span data-stu-id="fdb50-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="fdb50-114">Ta sama przestrzeń nazw może być zadeklarowana w wielu plikach Q #, które są kompilowane razem, o ile nie istnieją deklaracje typu, operacji lub funkcji o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="fdb50-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="fdb50-115">W szczególności nie można zdefiniować tego samego typu w tej samej przestrzeni nazw w wielu plikach, nawet jeśli deklaracje są identyczne.</span><span class="sxs-lookup"><span data-stu-id="fdb50-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="fdb50-116">Deklaracja przestrzeni nazw składa się ze słowa kluczowego `namespace` , po którym następuje nazwa przestrzeni nazw, otwierającego nawiasu klamrowego `{` , deklaracji zawartych w przestrzeni nazw i zamykającego nawiasu klamrowego `}` .</span><span class="sxs-lookup"><span data-stu-id="fdb50-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="fdb50-117">Nazwy przestrzeni nazw są zgodne ze wzorcem .NET sekwencji jednego lub więcej symboli dozwolonych oddzielonych kropkami `.` .</span><span class="sxs-lookup"><span data-stu-id="fdb50-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="fdb50-118">Na przykład `MyQuantumStuff` i `Microsoft.Quantum.Intrinsic` są prawidłowymi nazwami przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="fdb50-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="fdb50-119">Według Konwencji symbole w nazwie przestrzeni nazw są pisane wielkimi literami, ale nie jest to wymagane.</span><span class="sxs-lookup"><span data-stu-id="fdb50-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="fdb50-120">Odwołania do typów lub wartości, które zostały zadeklarowane w sposób nieokreślony w pliku, są rozwiązywane prawidłowo; nie ma potrzeby składania deklaracji typu, operacji lub funkcji przed odwołaniem do niej.</span><span class="sxs-lookup"><span data-stu-id="fdb50-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="fdb50-121">Otwarte dyrektywy</span><span class="sxs-lookup"><span data-stu-id="fdb50-121">Open Directives</span></span>

<span data-ttu-id="fdb50-122">W bloku przestrzeni nazw `open` dyrektywa może być używana do importowania wszystkich typów i wywoływanych deklaracji w określonym obszarze nazw i odwoływania się do nich według ich nazwy niekwalifikowanej.</span><span class="sxs-lookup"><span data-stu-id="fdb50-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="fdb50-123">Taka `open` dyrektywa składa się ze `open` słowa kluczowego, po którym następuje przestrzeń nazw, która ma zostać otwarta i kończąca się średnikiem.</span><span class="sxs-lookup"><span data-stu-id="fdb50-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="fdb50-124">Wszystkie `open` dyrektywy muszą występować przed dowolnymi `function` `operation` `newtype` deklaracjami w bloku przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="fdb50-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="fdb50-125">Opcjonalnie, krótka nazwa otwartej przestrzeni nazw może być zdefiniowana, tak że wszystkie elementy z tej przestrzeni nazw mogą (i muszą) być kwalifikowane przez zdefiniowaną krótką nazwę.</span><span class="sxs-lookup"><span data-stu-id="fdb50-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="fdb50-126">Na przykład uwzględniając następującą deklarację przestrzeni nazw i otwarte dyrektywy,</span><span class="sxs-lookup"><span data-stu-id="fdb50-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="fdb50-127">Jeśli operacja, którą deklarujemy, używa operacji `Op` z `Microsoft.Quantum.Intrinsic` , możemy ją wywołać za pomocą polecenia `Op` .</span><span class="sxs-lookup"><span data-stu-id="fdb50-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="fdb50-128">Jeśli jednak chciałem wywołać określoną funkcję `Fn` z usługi `Microsoft.Quantum.Math` , musimy ją wywołać przy użyciu `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="fdb50-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="fdb50-129">`open`Dyrektywa ma zastosowanie do całego bloku przestrzeni nazw w pliku.</span><span class="sxs-lookup"><span data-stu-id="fdb50-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="fdb50-130">W związku z tym, jeśli wcześniej zdefiniujesz dodatkową przestrzeń nazw w tym samym pliku Q # jak `NS` powyżej, wówczas wszystkie operacje/funkcje/typy zdefiniowane w drugim obszarze nazw nie będą miały dostępu do niczego z `Microsoft.Quantum.Intrinsic` lub `Microsoft.Quantum.Math` , chyba że powtarzają otwarte dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="fdb50-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="fdb50-131">Typ lub możliwy do odłożenia zdefiniowany w innej przestrzeni nazw, który *nie* jest otwarty w bieżącej przestrzeni nazw, musi odwoływać się do jego w pełni kwalifikowanej nazwy.</span><span class="sxs-lookup"><span data-stu-id="fdb50-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="fdb50-132">Na przykład operacja o nazwie `Op` z `X.Y` przestrzeni nazw musi być przywoływana przez jej w pełni kwalifikowaną nazwę `X.Y.Op` , chyba że `X.Y` przestrzeń nazw została otwarta wcześniej w bieżącym bloku.</span><span class="sxs-lookup"><span data-stu-id="fdb50-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="fdb50-133">Jak wspomniano powyżej, nawet jeśli `X` przestrzeń nazw została otwarta, nie można odwołać się do operacji jako `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="fdb50-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="fdb50-134">Jeśli krótka nazwa `Z` `X.Y` została zdefiniowana w tej przestrzeni nazw i pliku, `Op` musi być określona jako `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="fdb50-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="fdb50-135">Zwykle lepiej jest dołączyć przestrzeń nazw przy użyciu `open` dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="fdb50-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="fdb50-136">Użycie w pełni kwalifikowanej nazwy jest wymagane, jeśli dwie przestrzenie nazw definiują konstrukcje o tej samej nazwie, a bieżące źródło używa konstrukcji z obu tych typów.</span><span class="sxs-lookup"><span data-stu-id="fdb50-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="fdb50-137">Pytania i odpowiedzi są zgodne z tymi samymi regułami dotyczącymi nazewnictwa w innych językach .NET.</span><span class="sxs-lookup"><span data-stu-id="fdb50-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="fdb50-138">Jednak polecenie Q # nie obsługuje względnych odwołań do przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="fdb50-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="fdb50-139">Oznacza to, że jeśli przestrzeń nazw `a.b` została otwarta, odwołanie do operacji o nazwie `c.d` *nie* zostanie rozpoznane do operacji o pełnej nazwie `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="fdb50-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="fdb50-140">Formatowanie</span><span class="sxs-lookup"><span data-stu-id="fdb50-140">Formatting</span></span>

<span data-ttu-id="fdb50-141">Większość instrukcji i dyrektyw Q # kończy się średnikiem, `;` .</span><span class="sxs-lookup"><span data-stu-id="fdb50-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="fdb50-142">Instrukcje i deklaracje, takie jak `for` i `operation` kończące się blokiem instrukcji (patrz poniżej) nie wymagają kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="fdb50-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="fdb50-143">Każdy opis instrukcji wskazuje, czy jest wymagany średnik kończący.</span><span class="sxs-lookup"><span data-stu-id="fdb50-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="fdb50-144">Instrukcje, takie jak wyrażenia, deklaracje i dyrektywy, mogą być rozbite w wielu wierszach.</span><span class="sxs-lookup"><span data-stu-id="fdb50-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="fdb50-145">Należy unikać wielu instrukcji w pojedynczym wierszu.</span><span class="sxs-lookup"><span data-stu-id="fdb50-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="fdb50-146">Bloki instrukcji</span><span class="sxs-lookup"><span data-stu-id="fdb50-146">Statement Blocks</span></span>

<span data-ttu-id="fdb50-147">Instrukcje Q # są pogrupowane w bloki instrukcji.</span><span class="sxs-lookup"><span data-stu-id="fdb50-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="fdb50-148">Blok instrukcji rozpoczyna się od otwarcia `{` i kończącego się zamykaniem `}` .</span><span class="sxs-lookup"><span data-stu-id="fdb50-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="fdb50-149">Blok instrukcji, który jest leksykalny w innym bloku, jest traktowany jako podblok bloku zawierającego; bloki zawierające i podrzędne są również nazywane blokami zewnętrznymi i wewnętrznymi.</span><span class="sxs-lookup"><span data-stu-id="fdb50-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="fdb50-150">Komentarze</span><span class="sxs-lookup"><span data-stu-id="fdb50-150">Comments</span></span>

<span data-ttu-id="fdb50-151">Komentarze zaczynają się od dwóch ukośników `//` i są kontynuowane do końca wiersza.</span><span class="sxs-lookup"><span data-stu-id="fdb50-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="fdb50-152">Komentarz może pojawić się w dowolnym miejscu w pliku źródłowym Q #.</span><span class="sxs-lookup"><span data-stu-id="fdb50-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="fdb50-153">Komentarze dokumentacji</span><span class="sxs-lookup"><span data-stu-id="fdb50-153">Documentation Comments</span></span>

<span data-ttu-id="fdb50-154">Komentarze zaczynające się od trzech ukośników, `///` są traktowane specjalnie przez kompilator, gdy są wyświetlane bezpośrednio przed przestrzenią nazw, operacją, specjalizacją, funkcją lub definicją typu.</span><span class="sxs-lookup"><span data-stu-id="fdb50-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="fdb50-155">W takim przypadku ich zawartość jest pobierana jako Dokumentacja dla zdefiniowanego lub zdefiniowanego przez użytkownika typu, tak jak w przypadku innych języków .NET.</span><span class="sxs-lookup"><span data-stu-id="fdb50-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="fdb50-156">W `///` komentarzach tekst, który ma być wyświetlany jako część dokumentacji interfejsu API, jest sformatowany jako [promocji](https://daringfireball.net/projects/markdown/syntax), z różnymi częściami dokumentacji wskazywanych przez nagłówki o specjalnie określonym nazwie.</span><span class="sxs-lookup"><span data-stu-id="fdb50-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="fdb50-157">Jako rozszerzenie do promocji, odwołania krzyżowe do operacji, funkcji i typów zdefiniowanych przez użytkownika w Q # można uwzględnić przy użyciu `@"<ref target>"` , gdzie `<ref target>` jest zastępowana w pełni kwalifikowana nazwa obiektu kodu, do którego istnieje odwołanie.</span><span class="sxs-lookup"><span data-stu-id="fdb50-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="fdb50-158">Opcjonalnie aparat dokumentacji może również obsługiwać dodatkowe rozszerzenia promocji.</span><span class="sxs-lookup"><span data-stu-id="fdb50-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="fdb50-159">Przykład:</span><span class="sxs-lookup"><span data-stu-id="fdb50-159">For example:</span></span>

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

<span data-ttu-id="fdb50-160">Następujące nazwy są rozpoznawane jako nagłówki komentarzy do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="fdb50-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="fdb50-161">**Podsumowanie**: krótkie podsumowanie zachowania funkcji lub operacji albo do celu typu.</span><span class="sxs-lookup"><span data-stu-id="fdb50-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="fdb50-162">Pierwszy akapit podsumowania jest używany na potrzeby informacji o aktywowaniu.</span><span class="sxs-lookup"><span data-stu-id="fdb50-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="fdb50-163">Powinien być zwykły tekst.</span><span class="sxs-lookup"><span data-stu-id="fdb50-163">It should be plain text.</span></span>
- <span data-ttu-id="fdb50-164">**Opis**: Opis zachowania funkcji lub operacji lub do celu typu.</span><span class="sxs-lookup"><span data-stu-id="fdb50-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="fdb50-165">Podsumowanie i opis są łączone w celu utworzenia wygenerowanego pliku dokumentacji dla funkcji, operacji lub typu.</span><span class="sxs-lookup"><span data-stu-id="fdb50-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="fdb50-166">Opis może zawierać symbole i równania sformatowane w wierszu.</span><span class="sxs-lookup"><span data-stu-id="fdb50-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="fdb50-167">**Dane wejściowe**: Opis krotki wejściowej dla operacji lub funkcji.</span><span class="sxs-lookup"><span data-stu-id="fdb50-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="fdb50-168">Może zawierać dodatkowe podsekcje promocji wskazujące każdy pojedynczy element spójnej kolekcji wejściowej.</span><span class="sxs-lookup"><span data-stu-id="fdb50-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="fdb50-169">**Dane wyjściowe**: Opis krotki zwracanej przez operację lub funkcję.</span><span class="sxs-lookup"><span data-stu-id="fdb50-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="fdb50-170">**Parametry typu**: pusta sekcja, która zawiera jedną dodatkową podsekcję dla każdego parametru typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="fdb50-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="fdb50-171">**Przykład**: krótki przykład operacji, funkcji lub typu w użyciu.</span><span class="sxs-lookup"><span data-stu-id="fdb50-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="fdb50-172">**Uwagi**: różne Prose opisujące aspekt operacji, funkcji lub typu.</span><span class="sxs-lookup"><span data-stu-id="fdb50-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="fdb50-173">**Zobacz również**: Lista w pełni kwalifikowanych nazw wskazujących powiązane funkcje, operacje lub typy zdefiniowane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fdb50-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="fdb50-174">**Odwołania**: lista odwołań i cytatów dla udokumentowanego elementu.</span><span class="sxs-lookup"><span data-stu-id="fdb50-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fdb50-175">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="fdb50-175">Next steps</span></span>

<span data-ttu-id="fdb50-176">Informacje o [operacjach i funkcjach](xref:microsoft.quantum.guide.operationsfunctions) w usłudze Q #.</span><span class="sxs-lookup"><span data-stu-id="fdb50-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>
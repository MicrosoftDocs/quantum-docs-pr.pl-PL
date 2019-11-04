---
title: 'Instrukcje Q # | Microsoft Docs'
description: 'Instrukcje Q #'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5bcbee868c76aaf53d0b7969e6e634da62689aaa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184869"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="41d9b-103">Instrukcje i inne konstrukcje</span><span class="sxs-lookup"><span data-stu-id="41d9b-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="41d9b-104">Komentarze</span><span class="sxs-lookup"><span data-stu-id="41d9b-104">Comments</span></span>

<span data-ttu-id="41d9b-105">Komentarze zaczynają się od dwóch ukośników, `//`i kontynuować do końca wiersza.</span><span class="sxs-lookup"><span data-stu-id="41d9b-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="41d9b-106">Komentarz może pojawić się w dowolnym miejscu w pliku źródłowym Q #.</span><span class="sxs-lookup"><span data-stu-id="41d9b-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="41d9b-107">Komentarze dokumentacji</span><span class="sxs-lookup"><span data-stu-id="41d9b-107">Documentation Comments</span></span>

<span data-ttu-id="41d9b-108">Komentarze zaczynające się od trzech ukośników, `///`, są traktowane specjalnie przez kompilator, gdy są wyświetlane bezpośrednio przed przestrzenią nazw, operacją, specjalizacją, funkcją lub definicją typu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="41d9b-109">W takim przypadku ich zawartość jest pobierana jako Dokumentacja dla zdefiniowanego lub zdefiniowanego przez użytkownika typu, tak jak w przypadku innych języków .NET.</span><span class="sxs-lookup"><span data-stu-id="41d9b-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="41d9b-110">W `///` komentarzach tekst, który ma być [wyświetlany jako część](https://daringfireball.net/projects/markdown/syntax)dokumentacji interfejsu API, jest sformatowany jako przestawny, a różne części dokumentacji są wskazywane przez nagłówki o specjalnej nazwie.</span><span class="sxs-lookup"><span data-stu-id="41d9b-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="41d9b-111">Jako rozszerzenie do promocji, odwołania krzyżowe do operacji, funkcji i typów zdefiniowanych przez użytkownika w Q # można uwzględnić przy użyciu `@"<ref target>"`, gdzie `<ref target>` jest zastępowana przez w pełni kwalifikowaną nazwę obiektu kodu, do którego się odwołuje.</span><span class="sxs-lookup"><span data-stu-id="41d9b-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="41d9b-112">Opcjonalnie aparat dokumentacji może również obsługiwać dodatkowe rozszerzenia promocji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="41d9b-113">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="41d9b-113">For example:</span></span>

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
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit
{
    op(target);
    op(target);
}
```

<span data-ttu-id="41d9b-114">Następujące nazwy są rozpoznawane jako nagłówki komentarzy do dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="41d9b-115">**Podsumowanie**: krótkie podsumowanie zachowania funkcji lub operacji albo do celu typu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="41d9b-116">Pierwszy akapit podsumowania jest używany na potrzeby informacji o aktywowaniu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="41d9b-117">Powinien być zwykły tekst.</span><span class="sxs-lookup"><span data-stu-id="41d9b-117">It should be plain text.</span></span>
- <span data-ttu-id="41d9b-118">**Opis**: Opis zachowania funkcji lub operacji lub do celu typu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="41d9b-119">Podsumowanie i opis są łączone w celu utworzenia wygenerowanego pliku dokumentacji dla funkcji, operacji lub typu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="41d9b-120">Opis może zawierać symbole i równania sformatowane w wierszu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="41d9b-121">**Dane wejściowe**: Opis krotki wejściowej dla operacji lub funkcji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="41d9b-122">Może zawierać dodatkowe podsekcje promocji wskazujące każdy pojedynczy element spójnej kolekcji wejściowej.</span><span class="sxs-lookup"><span data-stu-id="41d9b-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="41d9b-123">**Dane wyjściowe**: Opis krotki zwracanej przez operację lub funkcję.</span><span class="sxs-lookup"><span data-stu-id="41d9b-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="41d9b-124">**Parametry typu**: pusta sekcja, która zawiera jedną dodatkową podsekcję dla każdego parametru typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="41d9b-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="41d9b-125">**Przykład**: krótki przykład operacji, funkcji lub typu w użyciu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="41d9b-126">**Uwagi**: różne Prose opisujące aspekt operacji, funkcji lub typu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="41d9b-127">**Zobacz również**: Lista w pełni kwalifikowanych nazw wskazujących powiązane funkcje, operacje lub typy zdefiniowane przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="41d9b-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="41d9b-128">**Odwołania**: lista odwołań i cytatów dla udokumentowanego elementu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="41d9b-129">Przestrzenie nazw</span><span class="sxs-lookup"><span data-stu-id="41d9b-129">Namespaces</span></span>

<span data-ttu-id="41d9b-130">Każda operacja Q #, funkcja i typ zdefiniowany przez użytkownika są zdefiniowane w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="41d9b-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="41d9b-131">Pytania i odpowiedzi są zgodne z tymi samymi regułami dotyczącymi nazewnictwa w innych językach .NET.</span><span class="sxs-lookup"><span data-stu-id="41d9b-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="41d9b-132">Jednak polecenie Q # nie obsługuje względnych odwołań do przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="41d9b-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="41d9b-133">Oznacza to, że jeśli obszar nazw `a.b` został otwarty, odwołanie do nazw operacji `c.d` nie zostanie rozpoznane do operacji z pełną nazwą `a.b.c.d`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="41d9b-134">W bloku przestrzeni nazw dyrektywa `open` może służyć do zaimportowania wszystkich typów i żądanych, zadeklarowanych w określonej przestrzeni nazw i odwołujących się do nich według ich nazwy niekwalifikowanej.</span><span class="sxs-lookup"><span data-stu-id="41d9b-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="41d9b-135">Opcjonalnie, krótka nazwa otwartej przestrzeni nazw może być zdefiniowana, tak że wszystkie elementy z tej przestrzeni nazw mogą (i muszą) być kwalifikowane przez zdefiniowaną krótką nazwę.</span><span class="sxs-lookup"><span data-stu-id="41d9b-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="41d9b-136">Dyrektywa `open` ma zastosowanie do całego bloku przestrzeni nazw w pliku.</span><span class="sxs-lookup"><span data-stu-id="41d9b-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="41d9b-137">Typ lub możliwy do odłożenia zdefiniowany w innej przestrzeni nazw, który nie jest otwarty w bieżącej przestrzeni nazw, musi odwoływać się do jego w pełni kwalifikowanej nazwy.</span><span class="sxs-lookup"><span data-stu-id="41d9b-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="41d9b-138">Na przykład operacja o nazwie `Op` w przestrzeni nazw `X.Y` musi być odwołująca się do w pełni kwalifikowanej nazwy `X.Y.Op`, chyba że przestrzeń nazw `X.Y` została otwarta wcześniej w bieżącym bloku.</span><span class="sxs-lookup"><span data-stu-id="41d9b-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="41d9b-139">Jak wspomniano powyżej, nawet jeśli `X` przestrzeń nazw została otwarta, nie można odwołać się do operacji jako `Y.Op`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="41d9b-140">Jeśli w tej przestrzeni nazw i pliku została zdefiniowana `Z` krótka nazwa `X.Y`, `Op` musi być określana jako `Z.Op`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {

    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="41d9b-141">Zwykle lepiej jest dołączyć przestrzeń nazw za pomocą dyrektywy `open`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="41d9b-142">Użycie w pełni kwalifikowanej nazwy jest wymagane, jeśli dwie przestrzenie nazw definiują konstrukcje o tej samej nazwie, a bieżące źródło używa konstrukcji z obu tych typów.</span><span class="sxs-lookup"><span data-stu-id="41d9b-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="41d9b-143">Formatowanie</span><span class="sxs-lookup"><span data-stu-id="41d9b-143">Formatting</span></span>

<span data-ttu-id="41d9b-144">Większość instrukcji i dyrektyw Q # kończy się średnikiem, `;`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="41d9b-145">Instrukcje i deklaracje, takie jak `for` i `operation` kończące się blokiem instrukcji nie wymagają kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="41d9b-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="41d9b-146">Każdy opis instrukcji wskazuje, czy jest wymagany średnik kończący.</span><span class="sxs-lookup"><span data-stu-id="41d9b-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="41d9b-147">Instrukcje, takie jak wyrażenia, deklaracje i dyrektywy, mogą być rozbite w wielu wierszach.</span><span class="sxs-lookup"><span data-stu-id="41d9b-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="41d9b-148">Należy unikać wielu instrukcji w pojedynczym wierszu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="41d9b-149">Bloki instrukcji</span><span class="sxs-lookup"><span data-stu-id="41d9b-149">Statement Blocks</span></span>

<span data-ttu-id="41d9b-150">Instrukcje Q # są pogrupowane w bloki instrukcji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="41d9b-151">Blok instrukcji rozpoczyna się od otwierającego `{` i zamyka `}`zamknięcia.</span><span class="sxs-lookup"><span data-stu-id="41d9b-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="41d9b-152">Blok instrukcji, który jest leksykalny w innym bloku, jest traktowany jako podblok bloku zawierającego; bloki zawierające i podrzędne są również nazywane blokami zewnętrznymi i wewnętrznymi.</span><span class="sxs-lookup"><span data-stu-id="41d9b-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="41d9b-153">Powiązanie symboli i przypisanie</span><span class="sxs-lookup"><span data-stu-id="41d9b-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="41d9b-154">Q # rozróżnia symbole modyfikowalne i zmienne.</span><span class="sxs-lookup"><span data-stu-id="41d9b-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="41d9b-155">Ogólnie rzecz biorąc, zaleca się użycie niezmiennych symboli, ponieważ umożliwia kompilatorowi wykonywanie większej optymalizacji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="41d9b-156">Lewa strona powiązania składa się z krotki symboli i prawej strony wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="41d9b-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="41d9b-157">Ponieważ wszystkie typy Q # są typami wartości — przy użyciu qubits, który ma nieco specjalną rolę — jest tworzona "kopia", gdy wartość jest powiązana z symbolem lub gdy jest on powiązany.</span><span class="sxs-lookup"><span data-stu-id="41d9b-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="41d9b-158">Oznacza to, że zachowanie Q # jest takie samo, jak w przypadku tworzenia kopii podczas przypisywania.</span><span class="sxs-lookup"><span data-stu-id="41d9b-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="41d9b-159">Dotyczy to również tablic.</span><span class="sxs-lookup"><span data-stu-id="41d9b-159">This in particular also includes arrays.</span></span> <span data-ttu-id="41d9b-160">Oczywiście w praktyce tylko odpowiednie fragmenty są w rzeczywistości odtworzone w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="41d9b-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="41d9b-161">Dekonstrukcja krotki</span><span class="sxs-lookup"><span data-stu-id="41d9b-161">Tuple Deconstruction</span></span>

<span data-ttu-id="41d9b-162">Jeśli po prawej stronie powiązania jest krotka, ta krotka może zostać rozbudowana po przypisaniu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="41d9b-163">Takie dekonstrukcji mogą dotyczyć krotek zagnieżdżonych, a każda pełna lub częściowa dekonstrukcja jest prawidłowa, o ile kształt krotki po prawej stronie jest zgodny z kształtem krotki symboli.</span><span class="sxs-lookup"><span data-stu-id="41d9b-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="41d9b-164">Funkcję dekonstrukcja krotki można szczególnie użyć, gdy po prawej stronie `=` jest wyrażenie wartości krotek.</span><span class="sxs-lookup"><span data-stu-id="41d9b-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="41d9b-165">Niezmienne symbole</span><span class="sxs-lookup"><span data-stu-id="41d9b-165">Immutable Symbols</span></span>

<span data-ttu-id="41d9b-166">Zmienne symbole są powiązane przy użyciu instrukcji `let`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="41d9b-167">Jest to przybliżenie równoważne deklaracji zmiennej i inicjalizacji w językach takich jak C#, z wyjątkiem tego, że symbole Q #, po powiązaniu, nie mogą być zmieniane; powiązania `let` są niezmienne.</span><span class="sxs-lookup"><span data-stu-id="41d9b-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="41d9b-168">Niezmienne powiązanie składa się ze słowa kluczowego `let`, po którym następuje ciąg lub krotka symboli, znak równości `=`, wyrażenie służące do powiązania symboli z i kończące się średnikiem.</span><span class="sxs-lookup"><span data-stu-id="41d9b-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="41d9b-169">Typ powiązanych symboli jest wywnioskowany na podstawie wyrażenia z prawej strony.</span><span class="sxs-lookup"><span data-stu-id="41d9b-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="41d9b-170">Symbole modyfikowalne</span><span class="sxs-lookup"><span data-stu-id="41d9b-170">Mutable Symbols</span></span>

<span data-ttu-id="41d9b-171">Symbole modyfikowalne są zdefiniowane i inicjowane przy użyciu instrukcji `mutable`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="41d9b-172">Symbole zadeklarowane i powiązane jako część instrukcji `mutable` mogą być ponownie powiązane z inną wartością w kodzie.</span><span class="sxs-lookup"><span data-stu-id="41d9b-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="41d9b-173">Modyfikowalna instrukcja powiązania składa się ze słowa kluczowego `mutable`, po którym następuje ciąg lub krotka symboli, znak równości `=`, wyrażenie służące do powiązania symboli z i kończący średnik.</span><span class="sxs-lookup"><span data-stu-id="41d9b-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="41d9b-174">Typ powiązanych symboli jest wywnioskowany na podstawie wyrażenia z prawej strony.</span><span class="sxs-lookup"><span data-stu-id="41d9b-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="41d9b-175">Jeśli symbol zostanie powiązana później w kodzie, jego typ nie ulegnie zmianie, a wartość związana musi być zgodna z tym typem.</span><span class="sxs-lookup"><span data-stu-id="41d9b-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="41d9b-176">Ponowne wiązanie modyfikowalnych symboli</span><span class="sxs-lookup"><span data-stu-id="41d9b-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="41d9b-177">Zmienna modyfikowalna może być powiązana przy użyciu instrukcji `set`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="41d9b-178">Takie ponowne powiązanie składa się ze słowa kluczowego `set`, po którym następuje ciąg lub krotka symboli, znak równości `=`, wyrażenie służące do ponownego powiązania symboli z i kończące się średnikiem.</span><span class="sxs-lookup"><span data-stu-id="41d9b-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="41d9b-179">Wartość musi być zgodna z typem (-ami) symboli, z którymi jest powiązane.</span><span class="sxs-lookup"><span data-stu-id="41d9b-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="41d9b-180">Instrukcja Apply-and-Reassign</span><span class="sxs-lookup"><span data-stu-id="41d9b-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="41d9b-181">Szczególnym typem instrukcji Set, do których odwołuje się jako instrukcja Apply-and-Reassign, stanowi wygodny sposób łączenia, jeśli prawa strona składa się z aplikacji operatora binarnego, a wynik ma być ponownie powiązany z lewym argumentem operatora.</span><span class="sxs-lookup"><span data-stu-id="41d9b-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="41d9b-182">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="41d9b-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="41d9b-183">zwiększa wartość licznika `counter` w każdej iteracji pętli `for`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="41d9b-184">Powyższy kod jest równoważny z</span><span class="sxs-lookup"><span data-stu-id="41d9b-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="41d9b-185">Podobne instrukcje są dostępne dla wszystkich operatorów binarnych, w których typ po lewej stronie jest zgodny z typem wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="41d9b-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="41d9b-186">Pozwala to na przykład wygodny sposób na gromadzenie wartości:</span><span class="sxs-lookup"><span data-stu-id="41d9b-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (q in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="41d9b-187">Instrukcja Update-and-Reassign</span><span class="sxs-lookup"><span data-stu-id="41d9b-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="41d9b-188">Podobne złączenie istnieje dla wyrażeń Copy-and-Update z prawej strony.</span><span class="sxs-lookup"><span data-stu-id="41d9b-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="41d9b-189">Istnieją odpowiednie instrukcje Update-and-Reassign dla nazwanych elementów w typach zdefiniowanych przez użytkownika, a także dla elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="41d9b-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function AddAll (reals : Double[], ims : Double[]) : Complex[] {
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

<span data-ttu-id="41d9b-190">W przypadku tablic nasze biblioteki standardowe zawierają niezbędne narzędzia do wykonywania wielu typowych operacji inicjalizacji i manipulowania tablicami, co pozwala uniknąć konieczności aktualizowania elementów tablicy w pierwszym miejscu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="41d9b-191">Instrukcje Update-and-Reassign oferują alternatywę w razie konieczności:</span><span class="sxs-lookup"><span data-stu-id="41d9b-191">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {

    mutable samples = new Double[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}

operation SampleUniformDistr(nrSamples : Int, prec : Int) : Double[] {

    let normalization = 1. / IntAsDouble(prec);
    mutable samples = RandomInts(prec, nrSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <span data-ttu-id="41d9b-192">Unikaj niepotrzebnego stosowania instrukcji Update-and-Reassign, wykorzystując narzędzia dostarczone w <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="41d9b-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="41d9b-193">Funkcja</span><span class="sxs-lookup"><span data-stu-id="41d9b-193">The function</span></span>
```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
{
    mutable pauliArray = new Pauli[n];
    for (index in 0 .. n - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="41d9b-194">na przykład można po prostu uprościć przy użyciu funkcji `ConstantArray` w `Microsoft.Quantum.Arrays`i zwrócić wyrażenie Copy-and-Update:</span><span class="sxs-lookup"><span data-stu-id="41d9b-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    return ConstantArray(n, PauliI) w/ i <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="41d9b-195">Zakresy powiązań</span><span class="sxs-lookup"><span data-stu-id="41d9b-195">Binding Scopes</span></span>

<span data-ttu-id="41d9b-196">Ogólnie rzecz biorąc, powiązania symboli wykraczają poza zakres i stają się nieaktywne na końcu bloku instrukcji, w którym występują.</span><span class="sxs-lookup"><span data-stu-id="41d9b-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="41d9b-197">Istnieją dwa wyjątki od tej reguły:</span><span class="sxs-lookup"><span data-stu-id="41d9b-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="41d9b-198">Powiązanie zmiennej pętli pętli `for` jest w zakresie dla treści pętli for, ale nie po końcu pętli.</span><span class="sxs-lookup"><span data-stu-id="41d9b-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="41d9b-199">Wszystkie trzy części `repeat`/pętla `until` (treść, test i naprawa) są traktowane jako pojedynczy zakres, dlatego symbole, które są powiązane z treścią, są dostępne w teście i w naprawie.</span><span class="sxs-lookup"><span data-stu-id="41d9b-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="41d9b-200">W przypadku obu typów pętli każdy przechodzi przez pętlę do własnego zakresu, dlatego powiązania z wcześniejszych przebiegów nie są dostępne w późniejszym przebiegu.</span><span class="sxs-lookup"><span data-stu-id="41d9b-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="41d9b-201">Powiązania symboli z bloków zewnętrznych są dziedziczone przez bloki wewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="41d9b-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="41d9b-202">Symbol może być powiązany tylko raz na blok; nie można zdefiniować symbolu o takiej samej nazwie jak inny symbol znajdujący się w zakresie (bez "przesłaniania").</span><span class="sxs-lookup"><span data-stu-id="41d9b-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="41d9b-203">Następujące sekwencje byłyby dozwolone:</span><span class="sxs-lookup"><span data-stu-id="41d9b-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="41d9b-204">oraz</span><span class="sxs-lookup"><span data-stu-id="41d9b-204">and</span></span>

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
```

<span data-ttu-id="41d9b-205">Może to jednak być niedozwolone:</span><span class="sxs-lookup"><span data-stu-id="41d9b-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="41d9b-206">w takim przypadku:</span><span class="sxs-lookup"><span data-stu-id="41d9b-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="41d9b-207">Przepływ sterowania</span><span class="sxs-lookup"><span data-stu-id="41d9b-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="41d9b-208">Pętla for</span><span class="sxs-lookup"><span data-stu-id="41d9b-208">For Loop</span></span>

<span data-ttu-id="41d9b-209">Instrukcja `for` obsługuje iterację w zakresie liczb całkowitych lub za pośrednictwem tablicy.</span><span class="sxs-lookup"><span data-stu-id="41d9b-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="41d9b-210">Instrukcja składa się z słowa kluczowego `for`, otwierającego nawiasu `(`, po którym następują krotka symboli lub symboli, słowo kluczowe `in`, wyrażenie typu `Range` lub Array, `)`nawias zamykające i blok instrukcji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="41d9b-211">Blok instrukcji (treść pętli) jest wykonywany wielokrotnie ze zdefiniowanymi symbolami (zmienne pętli) powiązane z każdą wartością w zakresie lub tablicy.</span><span class="sxs-lookup"><span data-stu-id="41d9b-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="41d9b-212">Należy pamiętać, że jeśli wyrażenie zakresu szacuje pusty zakres lub tablicę, treść nie zostanie wykonana.</span><span class="sxs-lookup"><span data-stu-id="41d9b-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="41d9b-213">Wyrażenie jest w pełni oceniane przed wprowadzeniem pętli i nie zmienia się podczas wykonywania pętli.</span><span class="sxs-lookup"><span data-stu-id="41d9b-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="41d9b-214">Powiązanie zadeklarowanych symboli jest niezmienne i zgodne z tymi samymi regułami, co inne powiązania zmiennych.</span><span class="sxs-lookup"><span data-stu-id="41d9b-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="41d9b-215">W szczególności możliwe jest, aby można było zadestruktorować, np. elementy array dla iteracji przez tablicę po przypisaniu do zmiennych pętli.</span><span class="sxs-lookup"><span data-stu-id="41d9b-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="41d9b-216">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="41d9b-216">For example,</span></span>

```qsharp
// ...
for (qb in qubits) { // qubits contains a Qubit[]
    H(qb);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="41d9b-217">Zmienna pętla jest powiązana z każdym wejściem do treści pętli i niezależna na końcu treści.</span><span class="sxs-lookup"><span data-stu-id="41d9b-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="41d9b-218">W szczególności zmienna Loop nie jest powiązana po zakończeniu pętli for.</span><span class="sxs-lookup"><span data-stu-id="41d9b-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="41d9b-219">Pętla REPEAT-until-Success</span><span class="sxs-lookup"><span data-stu-id="41d9b-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="41d9b-220">Instrukcja `repeat` obsługuje wzorzec "Repeat to until".</span><span class="sxs-lookup"><span data-stu-id="41d9b-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="41d9b-221">Składa się ze słowa kluczowego `repeat`, po którym następuje blok instrukcji (treść _pętli_ ), słowo kluczowe `until`, wyrażenie logiczne, a kończące się średnik lub słowo kluczowe `fixup` następuje inny blok instrukcji ( _Naprawa_).</span><span class="sxs-lookup"><span data-stu-id="41d9b-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="41d9b-222">Treść pętli, warunek i naprawa są uważane za pojedynczy zakres, dlatego symbole powiązane z treścią są dostępne w warunku i naprawienia.</span><span class="sxs-lookup"><span data-stu-id="41d9b-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qs);
    let success = ComputeSuccessIndicator(qs);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qs);
}
```

<span data-ttu-id="41d9b-223">Zostanie wykonana treść pętli, a następnie warunek jest obliczany.</span><span class="sxs-lookup"><span data-stu-id="41d9b-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="41d9b-224">Jeśli warunek ma wartość true, instrukcja zostanie zakończona; w przeciwnym razie nastąpi wykonanie naprawy, a instrukcja jest wykonywana ponownym uruchomieniem, rozpoczynając od treści pętli.</span><span class="sxs-lookup"><span data-stu-id="41d9b-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="41d9b-225">Należy zauważyć, że Kończenie wykonywania naprawy kończy zakres instrukcji, tak aby powiązania symboli wykonane podczas treści lub naprawy nie były dostępne w kolejnych powtórzeniach.</span><span class="sxs-lookup"><span data-stu-id="41d9b-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="41d9b-226">Na przykład poniższy kod jest obwodem usługi probabilistyczne, który implementuje ważną bramę rotacji $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ przy użyciu bram Hadamard i T.</span><span class="sxs-lookup"><span data-stu-id="41d9b-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="41d9b-227">Pętla kończy się w 8/5 powtórzeniach.</span><span class="sxs-lookup"><span data-stu-id="41d9b-227">The loop terminates in 8/5 repetitions on average.</span></span>
<span data-ttu-id="41d9b-228">Aby uzyskać szczegółowe informacje, zobacz [*REPEAT-until-Success: niedeterministyczna dekompozycja qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick i Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="41d9b-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

```qsharp
using (anc = Qubit()) {
    repeat {
        H(anc);
        T(anc);
        CNOT(target,anc);
        H(anc);
        Adjoint T(anc);
        H(anc);
        T(anc);
        H(anc);
        CNOT(target,anc);
        T(anc);
        Z(target);
        H(anc);
        let result = M(anc);
    } until (result == Zero);
}
```

> [!TIP]   
> <span data-ttu-id="41d9b-229">Unikaj używania pętli REPEAT-until-Success wewnątrz funkcji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="41d9b-230">Odpowiednie funkcje są udostępniane przez pętle w funkcjach.</span><span class="sxs-lookup"><span data-stu-id="41d9b-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="41d9b-231">While — pętla</span><span class="sxs-lookup"><span data-stu-id="41d9b-231">While Loop</span></span>

<span data-ttu-id="41d9b-232">Wzorce REPEAT-until-Success mają bardzo connotation specyficzny dla Quantum.</span><span class="sxs-lookup"><span data-stu-id="41d9b-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="41d9b-233">Są one powszechnie używane w określonych klasach algorytmów Quantum — a tym samym — dedykowana konstrukcja języka w Q #.</span><span class="sxs-lookup"><span data-stu-id="41d9b-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="41d9b-234">Jednak pętle, które są przerywane w zależności od warunku, a długość wykonywania jest w tym przypadku nieznana w czasie kompilacji, muszą być obsługiwane z uwzględnieniem szczególnych informacji w środowisku uruchomieniowym Quantum.</span><span class="sxs-lookup"><span data-stu-id="41d9b-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="41d9b-235">Ich użycie w ramach funkcji z drugiej strony jest nieproblematyczne, ponieważ tylko zawierają kod, który będzie wykonywany na konwencjonalnym sprzęcie (innym niż Quantum).</span><span class="sxs-lookup"><span data-stu-id="41d9b-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="41d9b-236">W związku z tym funkcja Q # obsługuje używanie pętli while tylko wewnątrz funkcji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="41d9b-237">Instrukcja `while` składa się ze słowa kluczowego `while`, otwierającego nawiasu `(`, warunku (tj. wyrażenia logicznego), nawiasu zamykającego `)`i bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="41d9b-238">Blok instrukcji (treść pętli) jest wykonywany tak długo, jak warunek oblicza `true`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="41d9b-239">Instrukcja warunkowa</span><span class="sxs-lookup"><span data-stu-id="41d9b-239">Conditional Statement</span></span>

<span data-ttu-id="41d9b-240">Instrukcja `if` obsługuje wykonywanie warunkowe.</span><span class="sxs-lookup"><span data-stu-id="41d9b-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="41d9b-241">Składa się ze słowa kluczowego `if`, otwartego nawiasu `(`, wyrażenia logicznego, nawiasu zamykającego `)`i bloku instrukcji (bloku _then_ ).</span><span class="sxs-lookup"><span data-stu-id="41d9b-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="41d9b-242">Może to być dowolna liczba klauzul innych niż IF, z których każdy składa się ze słowa kluczowego `elif`, otwierającego nawiasu `(`, wyrażenia logicznego, nawiasu zamykającego `)`i bloku instrukcji (bloku _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="41d9b-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="41d9b-243">Na koniec instrukcja może opcjonalnie zakończyć z klauzulą else, która składa się z słowa kluczowego `else`, po którym następuje inny blok instrukcji ( _else_ Block).</span><span class="sxs-lookup"><span data-stu-id="41d9b-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="41d9b-244">Warunek jest obliczany, a jeśli ma wartość true, zostaje wykonany blok then.</span><span class="sxs-lookup"><span data-stu-id="41d9b-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="41d9b-245">Jeśli warunek ma wartość false, zostanie obliczony pierwszy warunek else-if; Jeśli wartość jest równa true, ten blok else-IF jest wykonywany.</span><span class="sxs-lookup"><span data-stu-id="41d9b-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="41d9b-246">W przeciwnym razie drugi blok else-if zostanie przetestowany, a następnie trzeci i tak dalej, dopóki nie zostanie napotkana klauzula z prawdziwym warunkiem lub nie ma żadnych klauzul else-IF.</span><span class="sxs-lookup"><span data-stu-id="41d9b-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="41d9b-247">Jeśli oryginalny warunek if i wszystkie klauzule else-if mają wartość false, blok else jest wykonywany, jeśli został podany.</span><span class="sxs-lookup"><span data-stu-id="41d9b-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="41d9b-248">Należy zauważyć, że każdy blok jest wykonywany we własnym zakresie.</span><span class="sxs-lookup"><span data-stu-id="41d9b-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="41d9b-249">Powiązania wykonane wewnątrz bloku Then, Else-if lub else nie są widoczne po zakończeniu instrukcji if.</span><span class="sxs-lookup"><span data-stu-id="41d9b-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="41d9b-250">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="41d9b-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="41d9b-251">lub</span><span class="sxs-lookup"><span data-stu-id="41d9b-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="41d9b-252">przesłać</span><span class="sxs-lookup"><span data-stu-id="41d9b-252">Return</span></span>

<span data-ttu-id="41d9b-253">Instrukcja return kończąca wykonywanie operacji lub funkcji i zwraca wartość do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="41d9b-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="41d9b-254">Składa się ze słowa kluczowego `return`, po którym następuje wyrażenie odpowiedniego typu i kończący średnik.</span><span class="sxs-lookup"><span data-stu-id="41d9b-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="41d9b-255">Wywoływanie, które zwraca pustą krotkę, `()`, nie wymaga instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="41d9b-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="41d9b-256">Jeśli pożądane jest wczesne wyjście, w tym przypadku można użyć `return ()`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="41d9b-257">Możliwe do zwrócenia wszystkie inne typy wymagają końcowej instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="41d9b-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="41d9b-258">W obrębie operacji nie ma maksymalnej liczby instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="41d9b-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="41d9b-259">Kompilator może emitować ostrzeżenie, jeśli instrukcje są zgodne z instrukcją Return w bloku.</span><span class="sxs-lookup"><span data-stu-id="41d9b-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="41d9b-260">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="41d9b-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="41d9b-261">lub</span><span class="sxs-lookup"><span data-stu-id="41d9b-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="41d9b-262">lub</span><span class="sxs-lookup"><span data-stu-id="41d9b-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="41d9b-263">Udało</span><span class="sxs-lookup"><span data-stu-id="41d9b-263">Fail</span></span>

<span data-ttu-id="41d9b-264">Instrukcja Fail kończy wykonywanie operacji i zwraca wartość błędu do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="41d9b-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="41d9b-265">Składa się ze słowa kluczowego `fail`, po którym następuje ciąg i kończący się średnik.</span><span class="sxs-lookup"><span data-stu-id="41d9b-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="41d9b-266">Ten ciąg jest zwracany do klasycznego sterownika jako komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="41d9b-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="41d9b-267">W obrębie operacji nie ma ograniczeń dotyczących liczby instrukcji zakończonych niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="41d9b-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="41d9b-268">Kompilator może emitować ostrzeżenie, jeśli instrukcje obserwują instrukcję Fail w bloku.</span><span class="sxs-lookup"><span data-stu-id="41d9b-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="41d9b-269">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="41d9b-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="41d9b-270">lub</span><span class="sxs-lookup"><span data-stu-id="41d9b-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="41d9b-271">Qubit Management</span><span class="sxs-lookup"><span data-stu-id="41d9b-271">Qubit Management</span></span>

<span data-ttu-id="41d9b-272">Należy zauważyć, że żadna z tych instrukcji nie jest dozwolona w treści funkcji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="41d9b-273">Są one prawidłowe tylko w obrębie operacji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="41d9b-274">Wyczyść Qubits</span><span class="sxs-lookup"><span data-stu-id="41d9b-274">Clean Qubits</span></span>

<span data-ttu-id="41d9b-275">Instrukcja `using` jest używana do pozyskiwania nowych qubits do użycia w bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="41d9b-276">Qubits jest gwarantowany do zainicjowania w stanie `Zero` obliczeniowym.</span><span class="sxs-lookup"><span data-stu-id="41d9b-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="41d9b-277">Qubits powinien być w stanie `Zero` obliczeniowym na końcu bloku instrukcji; symulatory są zachęcane do wymuszenia tego.</span><span class="sxs-lookup"><span data-stu-id="41d9b-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="41d9b-278">Instrukcja składa się z słowa kluczowego `using`, po którym następuje otwarty nawias `(`, powiązanie, nawias zamykający `)`oraz blok instrukcji, w ramach którego będzie dostępny qubits.</span><span class="sxs-lookup"><span data-stu-id="41d9b-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="41d9b-279">Powiązanie jest zgodne z tym samym wzorcem co `let` instrukcji: pojedynczy symbol lub krotka symboli, po którym następuje znak równości `=`i pojedyncza wartość lub zgodna krotka dla inicjatorów.</span><span class="sxs-lookup"><span data-stu-id="41d9b-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="41d9b-280">Inicjatory są dostępne dla jednego qubit, wskazanego jako `Qubit()`, lub tablicy qubits, wskazywanym przez `Qubit[`, wyrażenie `Int` i `]`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="41d9b-281">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="41d9b-281">For example,</span></span>

```qsharp
using (q = Qubit()) {
    // ...
}
using ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="dirty-qubits"></a><span data-ttu-id="41d9b-282">Zanieczyszczone Qubits</span><span class="sxs-lookup"><span data-stu-id="41d9b-282">Dirty Qubits</span></span>

<span data-ttu-id="41d9b-283">Instrukcja `borrowing` służy do uzyskania qubits do tymczasowego użycia.</span><span class="sxs-lookup"><span data-stu-id="41d9b-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="41d9b-284">Instrukcja składa się z słowa kluczowego `borrowing`, po którym następuje otwarty nawias `(`, powiązanie, nawias zamykający `)`oraz blok instrukcji, w ramach którego będzie dostępny qubits.</span><span class="sxs-lookup"><span data-stu-id="41d9b-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="41d9b-285">Powiązanie jest zgodne z tym samym wzorcem i regułami, co w instrukcji `using`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="41d9b-286">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="41d9b-286">For example,</span></span>

```qsharp
borrowing (q = Qubit()) {
    // ...
}
borrowing ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="41d9b-287">Zapożyczone qubits znajdują się w nieznanym stanie i wykracza poza zakres na końcu bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="41d9b-288">Pożyczkobiorca zatwierdzi, aby opuszczał qubits w tym samym stanie, w którym były zapożyczone, tj. ich stan na początku i na końcu bloku instrukcji powinien być taki sam.</span><span class="sxs-lookup"><span data-stu-id="41d9b-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="41d9b-289">Ten stan w szczególności nie jest stanem klasycznym, takim jak w większości przypadków, zakresy pożyczek nie powinny zawierać pomiarów.</span><span class="sxs-lookup"><span data-stu-id="41d9b-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="41d9b-290">Takie qubits są często znane jako "Dirty Ancilla".</span><span class="sxs-lookup"><span data-stu-id="41d9b-290">Such qubits are often known as “dirty ancilla”.</span></span>
<span data-ttu-id="41d9b-291">Zobacz [*Refaktoryzacja przy użyciu 2n + 2 qubits z użyciem mnożenia modularnego Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler i Svore 2017), aby zapoznać się z przykładem wartości zanieczyszczonych Ancilla.</span><span class="sxs-lookup"><span data-stu-id="41d9b-291">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of dirty ancilla use.</span></span>

<span data-ttu-id="41d9b-292">Podczas pożyczania qubits system najpierw spróbuje wypełnić żądanie z qubits, które są używane, ale nie są dostępne w treści instrukcji `borrowing`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-292">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="41d9b-293">Jeśli nie ma wystarczającej ilości takich qubits, przydzieli nowe qubits do wykonania żądania.</span><span class="sxs-lookup"><span data-stu-id="41d9b-293">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="41d9b-294">Liczby sprzężone</span><span class="sxs-lookup"><span data-stu-id="41d9b-294">Conjugations</span></span>

<span data-ttu-id="41d9b-295">W przeciwieństwie do klasycznych bitów zwalnianie pamięci Quantum jest nieco bardziej zamierzone, ponieważ niequbitse Resetowanie może mieć niepożądane skutki dla pozostałych obliczeń, jeśli qubits nadal Entangled.</span><span class="sxs-lookup"><span data-stu-id="41d9b-295">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="41d9b-296">Można to uniknąć przez prawidłowe wykonanie obliczeń przed zwolnieniem pamięci.</span><span class="sxs-lookup"><span data-stu-id="41d9b-296">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="41d9b-297">Typowym wzorcem przetwarzania Quantum jest następujące:</span><span class="sxs-lookup"><span data-stu-id="41d9b-297">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="41d9b-298">: Nowość: Rozpoczynanie pracy z naszym wydaniem 0,9, obsługujemy instrukcję sprzężenia, która implementuje przekształcenie powyżej.</span><span class="sxs-lookup"><span data-stu-id="41d9b-298">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="41d9b-299">Korzystając z tej instrukcji, `ApplyWith` operacji można zaimplementować w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="41d9b-299">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="41d9b-300">Taka instrukcja sprzężona oczywiście jest znacznie bardziej użyteczna, jeśli transformacja zewnętrzna i wewnętrzna nie jest łatwo dostępna jako operacje, ale są bardziej wygodne do opisania przez blok składający się z kilku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="41d9b-300">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="41d9b-301">Przekształcenie odwrotne dla instrukcji zdefiniowanych w bloku jest automatycznie generowane przez kompilator i wykonywane po zakończeniu stosu Apply.</span><span class="sxs-lookup"><span data-stu-id="41d9b-301">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="41d9b-302">Ponieważ żadne zmienne modyfikowalne używane jako część wewnątrz bloku nie mogą być ponownie powiązane w bloku Apply, wygenerowane przekształcenie jest gwarantowane jako sąsiadujące obliczenie w bloku.</span><span class="sxs-lookup"><span data-stu-id="41d9b-302">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="41d9b-303">Instrukcje oceny wyrażeń</span><span class="sxs-lookup"><span data-stu-id="41d9b-303">Expression Evaluation Statements</span></span>

<span data-ttu-id="41d9b-304">Jako instrukcji można użyć dowolnego wyrażenia wywołania typu `Unit`.</span><span class="sxs-lookup"><span data-stu-id="41d9b-304">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="41d9b-305">Jest to głównie używane podczas wywoływania operacji na qubits, które zwracają `Unit`, ponieważ celem instrukcji jest zmodyfikowanie niejawnego stanu Quantum.</span><span class="sxs-lookup"><span data-stu-id="41d9b-305">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="41d9b-306">Instrukcje oceny wyrażeń wymagają zakończenia średnika.</span><span class="sxs-lookup"><span data-stu-id="41d9b-306">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="41d9b-307">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="41d9b-307">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```

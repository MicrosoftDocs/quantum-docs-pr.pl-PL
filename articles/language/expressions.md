---
title: Wyrażenia | Microsoft Docs
description: Wyrażenia
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 83fe697aa07a8ab28bd64437c8f5746bc5893b27
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036318"
---
# <a name="expressions"></a><span data-ttu-id="279a3-103">Wyrażenia</span><span class="sxs-lookup"><span data-stu-id="279a3-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="279a3-104">Grupowanie</span><span class="sxs-lookup"><span data-stu-id="279a3-104">Grouping</span></span>

<span data-ttu-id="279a3-105">Uwzględniając dowolne wyrażenie, to samo wyrażenie ujęte w nawiasy jest wyrażeniem tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="279a3-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="279a3-106">Na przykład `(7)` jest wyrażeniem `Int`, `([1,2,3])` jest wyrażeniem typu Array `Int`s, a `((1,2))` jest wyrażeniem z typem `(Int, Int)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="279a3-107">Równoważność między wartościami prostymi a krotkami jednoelementowymi opisanymi w [modelu typu](xref:microsoft.quantum.language.type-model#tuple-types) usuwa niejednoznaczność między `(6)` jako grupę i `(6)` jako spójną krotkę.</span><span class="sxs-lookup"><span data-stu-id="279a3-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="279a3-108">Symbole</span><span class="sxs-lookup"><span data-stu-id="279a3-108">Symbols</span></span>

<span data-ttu-id="279a3-109">Nazwa symbolu powiązanego lub przypisana do wartości typu `'T` jest wyrażeniem typu `'T`.</span><span class="sxs-lookup"><span data-stu-id="279a3-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="279a3-110">Na przykład jeśli symbol `count` jest powiązany z wartością całkowitą `5`, wówczas `count` jest wyrażeniem liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="279a3-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="279a3-111">Wyrażenia liczbowe</span><span class="sxs-lookup"><span data-stu-id="279a3-111">Numeric Expressions</span></span>

<span data-ttu-id="279a3-112">Wyrażenia liczbowe są wyrażeniami typu `Int`, `BigInt`lub `Double`.</span><span class="sxs-lookup"><span data-stu-id="279a3-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="279a3-113">Oznacza to, że są to liczby całkowite lub zmiennoprzecinkowe.</span><span class="sxs-lookup"><span data-stu-id="279a3-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="279a3-114">literały `Int` w Q # są identyczne z literałami całkowitymi C#w, z tą różnicą, że nie są wymagane żadne końcowe litery "l" lub "l" (lub dozwolone).</span><span class="sxs-lookup"><span data-stu-id="279a3-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="279a3-115">Liczby całkowite szesnastkowe i binarne są obsługiwane odpowiednio prefiksem "0x" i "0b".</span><span class="sxs-lookup"><span data-stu-id="279a3-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="279a3-116">literały `BigInt` w Q # są identyczne z ciągami Big Integer w programie .NET, z końcowym "l" lub "L".</span><span class="sxs-lookup"><span data-stu-id="279a3-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="279a3-117">Szesnastkowe duże liczby całkowite są obsługiwane z prefiksem "0x".</span><span class="sxs-lookup"><span data-stu-id="279a3-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="279a3-118">W ten sposób wszystkie prawidłowe zastosowania literałów `BigInt` są następujące:</span><span class="sxs-lookup"><span data-stu-id="279a3-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="279a3-119">literały `Double` w Q # są takie same jak literały podwójne C#w, z tą różnicą, że nie jest wymagane końcowe "d" lub "d" (lub dozwolone).</span><span class="sxs-lookup"><span data-stu-id="279a3-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="279a3-120">Uwzględniając wyrażenie tablicy dowolnego typu elementu, wyrażenie `Int` może być utworzone przy użyciu wbudowanej funkcji `Length`, z wyrażeniem tablicy ujętym w nawiasy, `(` i `)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="279a3-121">Na przykład jeśli `a` jest powiązany z tablicą, wówczas `Length(a)` jest wyrażeniem liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="279a3-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="279a3-122">Jeśli `b` jest tablicą tablic liczb całkowitych, `Int[][]`, wówczas `Length(b)` jest liczbą tablic podrzędnych w `b`, a `Length(b[1])` to liczba liczb całkowitych w drugiej podtabeli w `b`.</span><span class="sxs-lookup"><span data-stu-id="279a3-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="279a3-123">Uwzględniając dwa wyrażenia liczbowe tego samego typu, operatory binarne `+`, `-`, `*`i `/` mogą służyć do tworzenia nowego wyrażenia liczbowego.</span><span class="sxs-lookup"><span data-stu-id="279a3-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="279a3-124">Typ nowego wyrażenia będzie taki sam jak typy wyrażeń składowych.</span><span class="sxs-lookup"><span data-stu-id="279a3-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="279a3-125">W przypadku dwóch wyrażeń całkowitych `^` operatora binarnego (potęgi) można użyć do utworzenia nowego wyrażenia liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="279a3-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="279a3-126">Podobnie `^` mogą być używane z dwoma wyrażeniami podwójnymi, aby utworzyć nowe wyrażenie podwójne.</span><span class="sxs-lookup"><span data-stu-id="279a3-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="279a3-127">Na koniec `^` mogą być używane z dużą liczbą całkowitą z lewej strony i liczbą całkowitą z prawej strony, aby utworzyć nowe wyrażenie Big Integer.</span><span class="sxs-lookup"><span data-stu-id="279a3-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="279a3-128">W takim przypadku drugi parametr musi pasować do 32 bitów; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="279a3-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="279a3-129">W przypadku dwóch wyrażeń całkowitych lub dużych liczb całkowitych można utworzyć nowe wyrażenie typu Integer lub Big Integer przy użyciu operatorów `%` (moduł), `&&&` (bitowe AND), `|||` (bitowe OR) lub `^^^` (bitowe XOR).</span><span class="sxs-lookup"><span data-stu-id="279a3-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="279a3-130">W przypadku wyrażenia typu Integer lub Big Integer po lewej stronie i wyrażenia liczb całkowitych po prawej stronie operatory `<<<` (arytmetyczne przesunięcie w lewo) lub `>>>` (arytmetyczne przesunięcie w prawo) mogą być używane do tworzenia nowego wyrażenia z tym samym typem co wyrażenie lewej strony.</span><span class="sxs-lookup"><span data-stu-id="279a3-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="279a3-131">Drugi parametr (wartość przesunięcia) dla operacji Shift musi być większy lub równy zero; zachowanie dla ujemnych kwot przesunięcia jest niezdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="279a3-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="279a3-132">Wartość przesunięcia dla operacji przesunięcia musi być również zgodna z 32 bitowymi; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="279a3-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="279a3-133">Jeśli liczba, która ma zostać przesunięta jest liczbą całkowitą, wartość przesunięcia jest interpretowana `mod 64`; oznacza to, że przesunięcie 1 i przesunięcie 65 mają ten sam efekt.</span><span class="sxs-lookup"><span data-stu-id="279a3-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="279a3-134">W przypadku wartości liczb całkowitych i dużych liczb całkowitych przesunięcia są arytmetyczne.</span><span class="sxs-lookup"><span data-stu-id="279a3-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="279a3-135">Przesunięcie wartości ujemnej w lewo lub w prawo spowoduje powstanie liczby ujemnej.</span><span class="sxs-lookup"><span data-stu-id="279a3-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="279a3-136">Oznacza to, że przesunięcie jeden krok w lewo lub w prawo jest dokładnie takie samo jak mnożenie lub dzielenie odpowiednio przez 2.</span><span class="sxs-lookup"><span data-stu-id="279a3-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="279a3-137">Dzielenie liczb całkowitych i moduł całkowity są zgodne z tym samym zachowaniem dla liczb ujemnych jako C#.</span><span class="sxs-lookup"><span data-stu-id="279a3-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="279a3-138">Oznacza to, że `a % b` będzie zawsze mieć ten sam znak co `a`, a `b * (a / b) + a % b` zawsze będą równe `a`.</span><span class="sxs-lookup"><span data-stu-id="279a3-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="279a3-139">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="279a3-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="279a3-140">5</span><span class="sxs-lookup"><span data-stu-id="279a3-140">5</span></span> | <span data-ttu-id="279a3-141">2</span><span class="sxs-lookup"><span data-stu-id="279a3-141">2</span></span> | <span data-ttu-id="279a3-142">2</span><span class="sxs-lookup"><span data-stu-id="279a3-142">2</span></span> | <span data-ttu-id="279a3-143">1</span><span class="sxs-lookup"><span data-stu-id="279a3-143">1</span></span>
 <span data-ttu-id="279a3-144">5</span><span class="sxs-lookup"><span data-stu-id="279a3-144">5</span></span> | <span data-ttu-id="279a3-145">-2</span><span class="sxs-lookup"><span data-stu-id="279a3-145">-2</span></span> | <span data-ttu-id="279a3-146">-2</span><span class="sxs-lookup"><span data-stu-id="279a3-146">-2</span></span> | <span data-ttu-id="279a3-147">1</span><span class="sxs-lookup"><span data-stu-id="279a3-147">1</span></span>
 <span data-ttu-id="279a3-148">-5</span><span class="sxs-lookup"><span data-stu-id="279a3-148">-5</span></span> | <span data-ttu-id="279a3-149">2</span><span class="sxs-lookup"><span data-stu-id="279a3-149">2</span></span> | <span data-ttu-id="279a3-150">-2</span><span class="sxs-lookup"><span data-stu-id="279a3-150">-2</span></span> | <span data-ttu-id="279a3-151">-1</span><span class="sxs-lookup"><span data-stu-id="279a3-151">-1</span></span>
 <span data-ttu-id="279a3-152">-5</span><span class="sxs-lookup"><span data-stu-id="279a3-152">-5</span></span> | <span data-ttu-id="279a3-153">-2</span><span class="sxs-lookup"><span data-stu-id="279a3-153">-2</span></span> | <span data-ttu-id="279a3-154">2</span><span class="sxs-lookup"><span data-stu-id="279a3-154">2</span></span> | <span data-ttu-id="279a3-155">-1</span><span class="sxs-lookup"><span data-stu-id="279a3-155">-1</span></span>

<span data-ttu-id="279a3-156">Dzielenie z dużymi liczbami całkowitymi i moduł działa w taki sam sposób.</span><span class="sxs-lookup"><span data-stu-id="279a3-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="279a3-157">Mając każde wyrażenie liczbowe, nowe wyrażenie może być utworzone za pomocą operatora jednoargumentowego `-`.</span><span class="sxs-lookup"><span data-stu-id="279a3-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="279a3-158">Nowe wyrażenie będzie tego samego typu co wyrażenie elementu.</span><span class="sxs-lookup"><span data-stu-id="279a3-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="279a3-159">W przypadku dowolnego wyrażenia typu Integer lub Big Integer nowe wyrażenie tego samego typu może być sformułowane przy użyciu operatora jednoargumentowego `~~~` (dopełnienie bitowe).</span><span class="sxs-lookup"><span data-stu-id="279a3-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="279a3-160">Wyrażenia logiczne</span><span class="sxs-lookup"><span data-stu-id="279a3-160">Boolean Expressions</span></span>

<span data-ttu-id="279a3-161">Dwie `Bool` wartości literału są `true` i `false`.</span><span class="sxs-lookup"><span data-stu-id="279a3-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="279a3-162">Uwzględniając wszystkie dwa wyrażenia tego samego typu pierwotnego, operatory `==` i `!=` mogą służyć do konstruowania wyrażenia `Bool`.</span><span class="sxs-lookup"><span data-stu-id="279a3-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="279a3-163">Wyrażenie będzie prawdziwe, jeśli dwa wyrażenia są równe, i wartość false, jeśli nie.</span><span class="sxs-lookup"><span data-stu-id="279a3-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="279a3-164">Wartości typów zdefiniowanych przez użytkownika mogą nie być porównywane. można porównać tylko ich nieopakowane wartości.</span><span class="sxs-lookup"><span data-stu-id="279a3-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="279a3-165">Na przykład użycie operatora "unotocz" `!` (wyjaśnione na [stronie modelu typu Q #](xref:microsoft.quantum.language.type-model#user-defined-types)),</span><span class="sxs-lookup"><span data-stu-id="279a3-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="279a3-166">Porównywanie równości dla wartości `Qubit` jest równość tożsamości; oznacza to, czy dwa wyrażenia identyfikują ten sam qubit.</span><span class="sxs-lookup"><span data-stu-id="279a3-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="279a3-167">Stan dwóch qubits nie jest porównywany, dostępny, mierzony ani modyfikowany przez to porównanie.</span><span class="sxs-lookup"><span data-stu-id="279a3-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="279a3-168">Porównanie równości dla wartości `Double` może być mylące ze względu na efekt zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="279a3-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="279a3-169">Na przykład `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="279a3-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="279a3-170">Uwzględniając wszystkie dwa wyrażenia liczbowe, operatory binarne `>`, `<`, `>=`i `<=` mogą służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli pierwsze wyrażenie jest odpowiednio większe niż, mniejsze niż lub równe lub mniejsze niż lub równe drugie wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="279a3-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="279a3-171">Uwzględniając dowolne dwa wyrażenia logiczne, `and` i `or` operatory binarne mogą służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli oba wyrażenia (centr. or lub oba) są prawdziwe.</span><span class="sxs-lookup"><span data-stu-id="279a3-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="279a3-172">Podano dowolne wyrażenie logiczne `not` operator jednoargumentowy może służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli wyrażenie elementu składowego ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="279a3-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="279a3-173">Wyrażenia ciągów</span><span class="sxs-lookup"><span data-stu-id="279a3-173">String Expressions</span></span>

<span data-ttu-id="279a3-174">Funkcja Q # umożliwia używanie ciągów w instrukcji `fail` i funkcji standardowej `Log`.</span><span class="sxs-lookup"><span data-stu-id="279a3-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="279a3-175">Ciągi w Q # są literałami lub interpolowanymi ciągami.</span><span class="sxs-lookup"><span data-stu-id="279a3-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="279a3-176">Literały ciągu są podobne do prostych literałów ciągu w większości języków: sekwencji znaków Unicode ujętych w podwójne cudzysłowy `"`.</span><span class="sxs-lookup"><span data-stu-id="279a3-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="279a3-177">Wewnątrz ciągu, znak ukośnika odwrotnego `\` może być używany do ucieczki podwójnego znaku cudzysłowu i do wstawiania nowej linii jako `\n`, powrotu karetki jako `\r`i karty jako `\t`.</span><span class="sxs-lookup"><span data-stu-id="279a3-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="279a3-178">Na wystąpienie:</span><span class="sxs-lookup"><span data-stu-id="279a3-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="279a3-179">Składnia Q # dla interpolacji ciągów jest podzbiorem składni C# 7,0; Usługa Q # nie obsługuje ciągów interpolowanych Verbatim (wiele wierszy).</span><span class="sxs-lookup"><span data-stu-id="279a3-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="279a3-180">Zobacz [*interpolowane ciągi*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) C# składni.</span><span class="sxs-lookup"><span data-stu-id="279a3-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="279a3-181">Wyrażenia wewnątrz ciągu interpolowanego są zgodne z składnią Q #, C# a nie składnią.</span><span class="sxs-lookup"><span data-stu-id="279a3-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="279a3-182">Dowolne prawidłowe wyrażenie Q # może pojawić się w ciągu interpolowanym.</span><span class="sxs-lookup"><span data-stu-id="279a3-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="279a3-183">Wyrażenia qubit</span><span class="sxs-lookup"><span data-stu-id="279a3-183">Qubit Expressions</span></span>

<span data-ttu-id="279a3-184">Jedyne wyrażenia `Qubit` są symbolami, które są powiązane z wartościami `Qubit` lub elementami tablicy tablic `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="279a3-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="279a3-185">Brak literałów `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="279a3-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="279a3-186">Wyrażenia Pauli</span><span class="sxs-lookup"><span data-stu-id="279a3-186">Pauli Expressions</span></span>

<span data-ttu-id="279a3-187">Cztery `Pauli` wartości, `PauliI`, `PauliX`, `PauliY`i `PauliZ`są prawidłowymi wyrażeniami `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="279a3-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="279a3-188">Inne niż to, jedyne wyrażenia `Pauli` są symbolami, które są powiązane z wartościami `Pauli` lub elementami tablicy tablic `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="279a3-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="279a3-189">Wyrażenia wynikowe</span><span class="sxs-lookup"><span data-stu-id="279a3-189">Result Expressions</span></span>

<span data-ttu-id="279a3-190">Dwie `Result` wartości `One` i `Zero`są prawidłowymi wyrażeniami `Result`.</span><span class="sxs-lookup"><span data-stu-id="279a3-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="279a3-191">Inne niż to, jedyne wyrażenia `Result` są symbolami, które są powiązane z wartościami `Result` lub elementami tablicy tablic `Result`.</span><span class="sxs-lookup"><span data-stu-id="279a3-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="279a3-192">W szczególności należy zauważyć, że `One` nie jest taka sama jak liczba całkowita `1`i nie ma żadnej bezpośredniej konwersji między nimi.</span><span class="sxs-lookup"><span data-stu-id="279a3-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="279a3-193">Ta sama wartość dotyczy `Zero` i `0`.</span><span class="sxs-lookup"><span data-stu-id="279a3-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="279a3-194">Wyrażenia zakresu</span><span class="sxs-lookup"><span data-stu-id="279a3-194">Range Expressions</span></span>

<span data-ttu-id="279a3-195">Uwzględniając wszystkie trzy `Int` wyrażeń `start`, `step`i `stop`, `start .. step .. stop` jest wyrażeniem zakresu, którego pierwszy element jest `start`, drugi element jest `start+step`, trzeci element jest `start+step+step`itd., dopóki nie zostanie przeniesiona `stop`.</span><span class="sxs-lookup"><span data-stu-id="279a3-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="279a3-196">Zakres może być pusty, jeśli na przykład `step` jest dodatni i `stop < start`.</span><span class="sxs-lookup"><span data-stu-id="279a3-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="279a3-197">Ostatni element zakresu będzie `stop`, jeśli różnica między `start` i `stop` jest integralną wielokrotnością `step`; oznacza to, że zakres jest włącznie na obu końcach.</span><span class="sxs-lookup"><span data-stu-id="279a3-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="279a3-198">Uwzględniając wszystkie dwa `Int` wyrażeń `start` i `stop``start .. stop` jest wyrażeniem zakresu, które jest równe `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="279a3-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="279a3-199">Należy zauważyć, że implikowane `step` jest + 1 nawet wtedy, gdy `stop` jest mniejsze niż `start`; w takim przypadku zakres jest pusty.</span><span class="sxs-lookup"><span data-stu-id="279a3-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="279a3-200">Oto kilka przykładowych zakresów:</span><span class="sxs-lookup"><span data-stu-id="279a3-200">Some example ranges are:</span></span>

- <span data-ttu-id="279a3-201">`1..3` jest zakresem 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="279a3-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="279a3-202">`2..2..5` jest zakresem od 2 do 4.</span><span class="sxs-lookup"><span data-stu-id="279a3-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="279a3-203">`2..2..6` jest zakresem 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="279a3-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="279a3-204">`6..-2..2` jest zakresem 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="279a3-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="279a3-205">`2..1` jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="279a3-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="279a3-206">`2..6..7` jest zakresem 2.</span><span class="sxs-lookup"><span data-stu-id="279a3-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="279a3-207">`2..2..1` jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="279a3-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="279a3-208">`1..-1..2` jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="279a3-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="279a3-209">Możliwe do przewyrażenia</span><span class="sxs-lookup"><span data-stu-id="279a3-209">Callable Expressions</span></span>

<span data-ttu-id="279a3-210">Możliwy do przeprowadzenia literał jest nazwą operacji lub funkcji zdefiniowanej w zakresie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="279a3-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="279a3-211">Na przykład `X` to literał operacji odwołujący się do standardowej operacji `X` biblioteki, a `Message` jest literalną funkcją, która odwołuje się do funkcji `Message` biblioteki standardowej.</span><span class="sxs-lookup"><span data-stu-id="279a3-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="279a3-212">Jeśli operacja obsługuje `Adjoint` Funktor, wówczas `Adjoint op` jest wyrażeniem operacji.</span><span class="sxs-lookup"><span data-stu-id="279a3-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="279a3-213">Podobnie, jeśli operacja obsługuje `Controlled` Funktor, wówczas `Controlled op` jest wyrażeniem operacji.</span><span class="sxs-lookup"><span data-stu-id="279a3-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="279a3-214">Typy tych wyrażeń są określone w [funktory](xref:microsoft.quantum.language.type-model#functors).</span><span class="sxs-lookup"><span data-stu-id="279a3-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="279a3-215">Funktory (`Adjoint` i `Controlled`) są bardziej ściśle powiązane niż wszystkie inne operatory, z wyjątkiem `!` operatora rozwinięcia i indeksowania tablicy z `[]`.</span><span class="sxs-lookup"><span data-stu-id="279a3-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="279a3-216">W ten sposób obowiązują wszystkie kwestie prawne, przy założeniu, że operacje obsługują użycie funktory:</span><span class="sxs-lookup"><span data-stu-id="279a3-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="279a3-217">Możliwy do oddzielenia literału można użyć jako wartości, powiedzmy, aby przypisać do zmiennej lub przekazać do innego elementu.</span><span class="sxs-lookup"><span data-stu-id="279a3-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="279a3-218">W takim przypadku, jeśli wywoływany ma parametry typu, muszą one być podane jako część wartości możliwej do napisania.</span><span class="sxs-lookup"><span data-stu-id="279a3-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="279a3-219">Wartość możliwej do odwoływać nie może mieć żadnych nieokreślonych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="279a3-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="279a3-220">Na przykład jeśli `Fun` jest funkcją z sygnaturą `'T1->Unit`:</span><span class="sxs-lookup"><span data-stu-id="279a3-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="279a3-221">Wywoływanie wyrażeń wywołania</span><span class="sxs-lookup"><span data-stu-id="279a3-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="279a3-222">Dane wyrażenie możliwego do wywołania (operacji lub funkcji) i wyrażenie spójnej kolekcji typu wejściowego w podpisie, wyrażenie wywoływania może być sformułowane przez dołączenie wyrażenia krotki do możliwego do wywołania wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="279a3-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="279a3-223">Typ wyrażenia wywołania jest typem wyjściowym podpisu, który ma zostać wywołany.</span><span class="sxs-lookup"><span data-stu-id="279a3-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="279a3-224">Na przykład jeśli `Op` jest operacją z sygnaturą `((Int, Qubit) => Double)`, `Op(3, qubit1)` jest wyrażeniem typu `Double`.</span><span class="sxs-lookup"><span data-stu-id="279a3-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="279a3-225">Podobnie, jeśli `Sin` jest funkcją z sygnaturą `(Double -> Double)`, `Sin(0.1)` jest wyrażeniem typu `Double`.</span><span class="sxs-lookup"><span data-stu-id="279a3-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="279a3-226">Na koniec Jeśli `Builder` jest funkcją z sygnaturą `(Int -> (Int -> Int))`, `Builder(3)` jest funkcją z do int.</span><span class="sxs-lookup"><span data-stu-id="279a3-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="279a3-227">Wywołanie wyniku wyrażenia z wartościami możliwymi do wywołania wymaga dodatkowej pary nawiasów wokół wartościowego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="279a3-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="279a3-228">W związku z tym, aby wywołać wynik wywołania `Builder` z poprzedniego akapitu, poprawna składnia to:</span><span class="sxs-lookup"><span data-stu-id="279a3-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="279a3-229">W przypadku wywołania sparametryzowanego typu, można określić rzeczywiste parametry typu w nawiasach kątowych `<` i `>` po wyrażeniu możliwym do wywołania.</span><span class="sxs-lookup"><span data-stu-id="279a3-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="279a3-230">Zwykle nie jest to konieczne, ponieważ kompilator Q # wykryje rzeczywiste typy.</span><span class="sxs-lookup"><span data-stu-id="279a3-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="279a3-231">Jest to wymagane w przypadku częściowej aplikacji (patrz poniżej), jeśli argument z parametrem sparametryzowanym nie został określony.</span><span class="sxs-lookup"><span data-stu-id="279a3-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="279a3-232">Jest to również czasami przydatne, gdy przekazywanie operacji z różnymi Funktor obsługuje do możliwego do odwoływać.</span><span class="sxs-lookup"><span data-stu-id="279a3-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="279a3-233">Na przykład jeśli `Func` ma sygnaturę `('T1, 'T2, 'T1) -> 'T2`, `Op1` i `Op2` mają sygnaturę `(Qubit[] => Unit is Adj)`, a `Op3` ma sygnaturę `(Qubit[] => Unit)`, aby wywoływać `Func` z `Op1` jako pierwszy argument `Op2` jako drugi, a `Op3` jako trzeci:</span><span class="sxs-lookup"><span data-stu-id="279a3-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="279a3-234">Specyfikacja typu jest wymagana, ponieważ `Op3` i `Op1` mają różne typy, więc kompilator traktuje to jako niejednoznaczne bez specyfikacji.</span><span class="sxs-lookup"><span data-stu-id="279a3-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="279a3-235">Aplikacja częściowa</span><span class="sxs-lookup"><span data-stu-id="279a3-235">Partial Application</span></span>

<span data-ttu-id="279a3-236">Po otrzymaniu możliwego do przetworzenia wyrażenia można utworzyć nowe wywoływanie, dostarczając podzestaw argumentów do obiektu.</span><span class="sxs-lookup"><span data-stu-id="279a3-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="279a3-237">Jest to nazywane _częściową aplikacją_.</span><span class="sxs-lookup"><span data-stu-id="279a3-237">This is called _partial application_.</span></span>

<span data-ttu-id="279a3-238">W Q #, częściowo zastosowane wywołanie jest wyrażane przez zapisanie wyrażenia zwykłego wywołania, ale przy użyciu podkreślenia, `_`, dla nieokreślonych argumentów.</span><span class="sxs-lookup"><span data-stu-id="279a3-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="279a3-239">Wynikowe wywoływanie ma ten sam typ wyniku co podstawowy możliwy do przetworzenie i te same specjalizacje dla operacji.</span><span class="sxs-lookup"><span data-stu-id="279a3-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="279a3-240">Typ danych wejściowych częściowej aplikacji jest po prostu oryginalnym typem z określonymi argumentami.</span><span class="sxs-lookup"><span data-stu-id="279a3-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="279a3-241">Jeśli zmienna modyfikowalna jest przenoszona jako określony argument podczas tworzenia częściowej aplikacji, używana jest bieżąca wartość zmiennej.</span><span class="sxs-lookup"><span data-stu-id="279a3-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="279a3-242">Późniejsze zmiany wartości zmiennej nie wpłyną na częściową aplikację.</span><span class="sxs-lookup"><span data-stu-id="279a3-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="279a3-243">Na przykład jeśli `Op` ma typ `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="279a3-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="279a3-244">`Op(5,(_,_))` jest typu `(((Qubit,Qubit), Double) => Unit is Adj)`i dlatego ma `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="279a3-245">`Op(_,(_,1.0))` ma `((Int, (Qubit,Qubit)) => Unit is Adj)`typu.</span><span class="sxs-lookup"><span data-stu-id="279a3-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="279a3-246">`Op(_,((q1,q2),_))` ma `((Int,Double) => Unit is Adj)`typu.</span><span class="sxs-lookup"><span data-stu-id="279a3-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="279a3-247">Należy zauważyć, że w tym miejscu zastosowano jednokrotną równoważność krotki.</span><span class="sxs-lookup"><span data-stu-id="279a3-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="279a3-248">Jeśli częściowo zastosowane wywołanie ma parametry typu, których nie można wywnioskować przez kompilator, muszą one być dostarczone w lokacji wywołania.</span><span class="sxs-lookup"><span data-stu-id="279a3-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="279a3-249">Częściowa aplikacja nie może mieć żadnych nieokreślonych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="279a3-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="279a3-250">Na przykład jeśli `Op` ma typ `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="279a3-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="279a3-251">Rekursja</span><span class="sxs-lookup"><span data-stu-id="279a3-251">Recursion</span></span>

<span data-ttu-id="279a3-252">Liczba wywoływanych Q może być bezpośrednio lub pośrednio cykliczna.</span><span class="sxs-lookup"><span data-stu-id="279a3-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="279a3-253">Oznacza to, że operacja lub funkcja może wywołać się sama lub wywołać inne wywołanie, które bezpośrednio lub pośrednio wywołuje operację, którą można wywołać.</span><span class="sxs-lookup"><span data-stu-id="279a3-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="279a3-254">Istnieją jednak dwa ważne komentarze dotyczące korzystania z rekursji:</span><span class="sxs-lookup"><span data-stu-id="279a3-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="279a3-255">Użycie rekursji w operacjach może zakłócać pewne optymalizacje.</span><span class="sxs-lookup"><span data-stu-id="279a3-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="279a3-256">Może to mieć znaczny wpływ na czas wykonywania algorytmu.</span><span class="sxs-lookup"><span data-stu-id="279a3-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="279a3-257">W przypadku wykonywania na rzeczywistym urządzeniu Quantum przestrzeń stosu może być ograniczona, a więc Szczegółowa rekursja może prowadzić do błędu czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="279a3-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="279a3-258">W szczególności kompilator Q # i środowisko wykonawcze nie identyfikują i nie optymalizują rekursji końcowego.</span><span class="sxs-lookup"><span data-stu-id="279a3-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="279a3-259">Wyrażenia krotki</span><span class="sxs-lookup"><span data-stu-id="279a3-259">Tuple Expressions</span></span>

<span data-ttu-id="279a3-260">Literał krotki jest sekwencją wyrażenia elementu odpowiedniego typu, rozdzielonych przecinkami, ujęty w `(` i `)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="279a3-261">Na przykład `(1, One)` jest wyrażeniem `(Int, Result)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="279a3-262">W przypadku innych niż literały jedynymi wyrażeniami krotek są symbole, które są powiązane z wartościami krotki, elementami tablicy tablic krotek i wywoływanie wywołań, które zwracają krotki.</span><span class="sxs-lookup"><span data-stu-id="279a3-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="279a3-263">Wyrażenia typu zdefiniowanego przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="279a3-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="279a3-264">Literał typu zdefiniowanego przez użytkownika składa się z nazwy typu, a następnie literału krotki typu krotki podstawowej typu.</span><span class="sxs-lookup"><span data-stu-id="279a3-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="279a3-265">Na przykład jeśli `IntPair` jest typem zdefiniowanym przez użytkownika na podstawie `(Int, Int)`, wówczas `IntPair(2,3)` byłby prawidłowym literałem tego typu.</span><span class="sxs-lookup"><span data-stu-id="279a3-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="279a3-266">Oprócz literałów jedynymi wyrażeniami typu zdefiniowanego przez użytkownika są symbole, które są powiązane z wartościami tego typu, elementy tablicy tablic tego typu i wywoływanie wywołań, które zwracają ten typ.</span><span class="sxs-lookup"><span data-stu-id="279a3-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="279a3-267">Odpakowywanie wyrażeń</span><span class="sxs-lookup"><span data-stu-id="279a3-267">Unwrap Expressions</span></span>

<span data-ttu-id="279a3-268">W Q # operator rozwinięcia jest końcowym znakiem wykrzyknika `!`.</span><span class="sxs-lookup"><span data-stu-id="279a3-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="279a3-269">Na przykład jeśli `IntPair` jest typem zdefiniowanym przez użytkownika o typie podstawowym `(Int, Int)`, a `s` była zmienną z wartością `IntPair(2,3)`, `s!` byłoby `(2,3)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="279a3-270">Dla typów zdefiniowanych przez użytkownika, zdefiniowanych w warunkach innych typów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="279a3-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="279a3-271">operatora rozwinięcia można powtórzyć; na przykład `s!!` wskazuje podwójnie nieopakowaną wartość `s`.</span><span class="sxs-lookup"><span data-stu-id="279a3-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="279a3-272">W takim przypadku, jeśli `WrappedPair` jest typem zdefiniowanym przez użytkownika o typie podstawowym `IntPair`, a `t` jest zmienną z wartością `WrappedPair(IntPair(1,2))`, `t!!` będzie `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="279a3-273">Operator `!` ma wyższy priorytet niż wszystkie inne operatory inne niż `[]` do indeksowania tablicy i dzielenia.</span><span class="sxs-lookup"><span data-stu-id="279a3-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="279a3-274">`!` i `[]` powiązać pozycjonowanie; oznacza to, że `a[i]![3]` powinna zostać odczytana jako `((a[i])!)[3]`: Weź element `i`"z `a`, Odpakuj go, a następnie Pobierz trzeci element nieopakowanej wartości (która musi być tablicą).</span><span class="sxs-lookup"><span data-stu-id="279a3-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="279a3-275">Pierwszeństwo operatora `!` ma jeden wpływ, który może nie być oczywisty.</span><span class="sxs-lookup"><span data-stu-id="279a3-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="279a3-276">Jeśli funkcja lub operacja zwraca wartość, która staje się nieopakowana, wywołanie funkcji lub operacji musi być ujęte w nawiasy, tak aby krotka argumentu była powiązana z wywołaniem, a nie z odwinięciem.</span><span class="sxs-lookup"><span data-stu-id="279a3-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="279a3-277">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="279a3-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="279a3-278">Wyrażenia tablic</span><span class="sxs-lookup"><span data-stu-id="279a3-278">Array Expressions</span></span>

<span data-ttu-id="279a3-279">Literał tablicowy jest sekwencją co najmniej jednego wyrażenia elementu, oddzielone przecinkami, ujęte w `[` i `]`.</span><span class="sxs-lookup"><span data-stu-id="279a3-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="279a3-280">Wszystkie elementy muszą być zgodne z tym samym typem.</span><span class="sxs-lookup"><span data-stu-id="279a3-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="279a3-281">Jeśli wspólny typ elementu jest operacją lub typem funkcji, wszystkie elementy muszą mieć te same typy danych wejściowych i wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="279a3-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="279a3-282">Typ elementu tablicy będzie obsługiwał wszystkie funktory, które są obsługiwane przez wszystkie elementy.</span><span class="sxs-lookup"><span data-stu-id="279a3-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="279a3-283">Na przykład jeśli `Op1`, `Op2`i `Op3` wszystkie są `Qubit[] => Unit`, ale `Op1` obsługuje `Adjoint`, `Op2` obsługuje `Controlled`, a `Op3` obsługuje oba:</span><span class="sxs-lookup"><span data-stu-id="279a3-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="279a3-284">`[Op1, Op2]` jest tablicą operacji `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="279a3-285">`[Op1, Op3]` jest tablicą operacji `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="279a3-286">`[Op2, Op3]` jest tablicą operacji `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="279a3-287">Puste literały tablicowe, `[]`, są niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="279a3-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="279a3-288">Zamiast tego przy użyciu `new ★[0]`, gdzie `★` jest symbolem zastępczym dla odpowiedniego typu, umożliwia utworzenie odpowiedniej tablicy o długości zero.</span><span class="sxs-lookup"><span data-stu-id="279a3-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="279a3-289">Mając daną dwie tablice tego samego typu, operator `+` binarnych może służyć do tworzenia nowej tablicy, która jest połączeniem dwóch tablic.</span><span class="sxs-lookup"><span data-stu-id="279a3-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="279a3-290">Na przykład `[1,2,3] + [4,5,6]` jest `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="279a3-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="279a3-291">Tworzenie tablicy</span><span class="sxs-lookup"><span data-stu-id="279a3-291">Array Creation</span></span>

<span data-ttu-id="279a3-292">Uwzględniając typ i wyrażenie `Int`, operatora `new` można użyć do przydzielenia nowej tablicy o danym rozmiarze.</span><span class="sxs-lookup"><span data-stu-id="279a3-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="279a3-293">Na przykład `new Int[i+1]` przydzieli nową tablicę `Int` z elementami `i+1`.</span><span class="sxs-lookup"><span data-stu-id="279a3-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="279a3-294">Elementy nowej tablicy są inicjowane z wartością domyślną zależną od typu.</span><span class="sxs-lookup"><span data-stu-id="279a3-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="279a3-295">W większości przypadków jest to pewna odmiana zero.</span><span class="sxs-lookup"><span data-stu-id="279a3-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="279a3-296">W przypadku qubits i elementów, które są odwołaniami do jednostek, nie ma żadnej rozsądnej wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="279a3-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="279a3-297">W tym przypadku dla tych typów wartość domyślna to nieprawidłowe odwołanie, którego nie można użyć bez powodowania błędu czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="279a3-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="279a3-298">Jest to podobne do odwołania o wartości null w językach takich C# jak lub Java.</span><span class="sxs-lookup"><span data-stu-id="279a3-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="279a3-299">Tablice zawierające qubits lub elementy wywoływane muszą zostać prawidłowo zainicjowane przy użyciu wartości innych niż domyślne, zanim ich elementy mogą być bezpiecznie używane.</span><span class="sxs-lookup"><span data-stu-id="279a3-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="279a3-300">Odpowiednie procedury inicjowania można znaleźć w <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="279a3-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="279a3-301">Wartości domyślne dla każdego typu są następujące:</span><span class="sxs-lookup"><span data-stu-id="279a3-301">The default values for each type are:</span></span>

<span data-ttu-id="279a3-302">Typ</span><span class="sxs-lookup"><span data-stu-id="279a3-302">Type</span></span> | <span data-ttu-id="279a3-303">Domyślne</span><span class="sxs-lookup"><span data-stu-id="279a3-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="279a3-304">_Nieprawidłowy qubit_</span><span class="sxs-lookup"><span data-stu-id="279a3-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="279a3-305">Pusty zakres, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="279a3-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="279a3-306">_nieprawidłowe wywoływanie_</span><span class="sxs-lookup"><span data-stu-id="279a3-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="279a3-307">Typy krotek są inicjowane element po elemencie.</span><span class="sxs-lookup"><span data-stu-id="279a3-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="279a3-308">Tablice nieregularne</span><span class="sxs-lookup"><span data-stu-id="279a3-308">Jagged Arrays</span></span>

<span data-ttu-id="279a3-309">Tablica nieregularna, czasami nazywana "tablicą tablicową", jest tablicą, której elementy są tablicami.</span><span class="sxs-lookup"><span data-stu-id="279a3-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="279a3-310">Elementy tablicy nieregularnej mogą mieć różne rozmiary.</span><span class="sxs-lookup"><span data-stu-id="279a3-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="279a3-311">Poniższy przykład pokazuje, jak zadeklarować i zainicjować tablicę nieregularną reprezentującą tabelę mnożenia.</span><span class="sxs-lookup"><span data-stu-id="279a3-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {

    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```


### <a name="array-slices"></a><span data-ttu-id="279a3-312">Wycinki tablicy</span><span class="sxs-lookup"><span data-stu-id="279a3-312">Array Slices</span></span>

<span data-ttu-id="279a3-313">Korzystając z wyrażenia tablicy i wyrażenia `Range`, nowe wyrażenie może być utworzone przy użyciu operatora wycinka tablicy `[` i `]`.</span><span class="sxs-lookup"><span data-stu-id="279a3-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="279a3-314">Nowe wyrażenie będzie tego samego typu co tablica i będzie zawierać elementy tablicy indeksowane przez elementy `Range`w kolejności zdefiniowanej przez `Range`.</span><span class="sxs-lookup"><span data-stu-id="279a3-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="279a3-315">Na przykład jeśli `a` jest powiązany z tablicą `Double`s, `a[3..-1..0]` jest wyrażeniem `Double[]`, które zawiera pierwsze cztery elementy `a`, ale w kolejności odwrotnej, jak pojawiają się w `a`.</span><span class="sxs-lookup"><span data-stu-id="279a3-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="279a3-316">Jeśli `Range` jest puste, powstający wycink tablicy będzie zerem o zerowej długości.</span><span class="sxs-lookup"><span data-stu-id="279a3-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="279a3-317">Jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, musi być ujęte w nawiasy klamrowe w celu wycięcia.</span><span class="sxs-lookup"><span data-stu-id="279a3-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="279a3-318">Na przykład jeśli `a` i `b` są tablicami `Int`s, wycinek z złączki zostanie wyrażony jako:</span><span class="sxs-lookup"><span data-stu-id="279a3-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="279a3-319">Wszystkie tablice w Q # są oparte na zero.</span><span class="sxs-lookup"><span data-stu-id="279a3-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="279a3-320">Oznacza to, że pierwszy element tablicy `a` zawsze jest `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="279a3-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="279a3-321">Począwszy od naszego 0,8 wydania, obsługujemy kontekstowe wyrażenia dla dzielenia zakresów.</span><span class="sxs-lookup"><span data-stu-id="279a3-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="279a3-322">W szczególności wartości początkowe i końcowe zakresu mogą zostać pominięte w kontekście wyrażenia wycinka zakresu.</span><span class="sxs-lookup"><span data-stu-id="279a3-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="279a3-323">W takim przypadku kompilator zastosuje następujące reguły w celu wywnioskowania zamierzonych ograniczników dla zakresu.</span><span class="sxs-lookup"><span data-stu-id="279a3-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="279a3-324">Na przykład, jeśli wartość początkowa zakresu zostanie pominięta, wywnioskowana wartość początkowa</span><span class="sxs-lookup"><span data-stu-id="279a3-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="279a3-325">ma wartość zero, jeśli nie określono żadnego kroku lub określony krok jest dodatni i</span><span class="sxs-lookup"><span data-stu-id="279a3-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="279a3-326">jest długością tablicy z wycinkami minus jeden, jeśli określony krok jest ujemny.</span><span class="sxs-lookup"><span data-stu-id="279a3-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="279a3-327">W przypadku pominięcia wartości końcowej zakresu, wywnioskowana wartość końcowa</span><span class="sxs-lookup"><span data-stu-id="279a3-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="279a3-328">jest długością tablicy wycinka minus jeden, jeśli żaden krok nie jest określony lub określony krok jest dodatni i</span><span class="sxs-lookup"><span data-stu-id="279a3-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="279a3-329">ma wartość zero, jeśli określony krok jest ujemny.</span><span class="sxs-lookup"><span data-stu-id="279a3-329">is zero if the specified step is negative.</span></span> 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

## <a name="array-element-expressions"></a><span data-ttu-id="279a3-330">Wyrażenia elementu tablicy</span><span class="sxs-lookup"><span data-stu-id="279a3-330">Array Element Expressions</span></span>

<span data-ttu-id="279a3-331">Korzystając z wyrażenia tablicy i wyrażenia `Int`, nowe wyrażenie może być utworzone za pomocą operatora `[` i `]` elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="279a3-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="279a3-332">Nowe wyrażenie będzie tego samego typu co typ elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="279a3-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="279a3-333">Na przykład jeśli `a` jest powiązany z tablicą `Double`s, `a[4]` jest wyrażeniem `Double`.</span><span class="sxs-lookup"><span data-stu-id="279a3-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="279a3-334">Jeśli wyrażenie tablicy nie jest prostym identyfikatorem, musi być ujęte w nawiasy klamrowe, aby można było wybrać element.</span><span class="sxs-lookup"><span data-stu-id="279a3-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="279a3-335">Na przykład jeśli `a` i `b` są tablicami `Int`s, element z łączenia byłby wyrażony jako:</span><span class="sxs-lookup"><span data-stu-id="279a3-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="279a3-336">Wszystkie tablice w Q # są oparte na zero.</span><span class="sxs-lookup"><span data-stu-id="279a3-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="279a3-337">Oznacza to, że pierwszy element tablicy `a` zawsze jest `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="279a3-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="279a3-338">Wyrażenia kopiowania i aktualizowania</span><span class="sxs-lookup"><span data-stu-id="279a3-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="279a3-339">Nowe tablice można tworzyć z istniejących za pośrednictwem wyrażeń kopiowania i aktualizowania.</span><span class="sxs-lookup"><span data-stu-id="279a3-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="279a3-340">Wyrażenie Copy-and-Update jest wyrażeniem `expression1 w/ expression2 <- expression3`, gdzie `expression1` musi być typu `T[]` dla niektórych typów `T`.</span><span class="sxs-lookup"><span data-stu-id="279a3-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="279a3-341">Druga `expression2` definiuje indeksy elementów do zmodyfikowania w porównaniu do tablicy w `expression1` i musi być albo typu `Int` lub typu `Range`.</span><span class="sxs-lookup"><span data-stu-id="279a3-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="279a3-342">Jeśli `expression2` jest typu `Int`, `expression3` musi być typu `T`.</span><span class="sxs-lookup"><span data-stu-id="279a3-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="279a3-343">Jeśli `expression2` jest typu `Range`, `expression3` musi być typu `T[]`.</span><span class="sxs-lookup"><span data-stu-id="279a3-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="279a3-344">Wyrażenie Copy-and-Update `arr w/ idx <- value` konstruuje nową tablicę ze wszystkimi elementami ustawionymi na odpowiadający element w `arr`, z wyjątkiem elementów w `idx`, które są ustawione na jedną z nich w `value`.</span><span class="sxs-lookup"><span data-stu-id="279a3-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="279a3-345">Na przykład jeśli `arr` zawiera tablicę `[0,1,2,3]`, to</span><span class="sxs-lookup"><span data-stu-id="279a3-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="279a3-346">`arr w/ 0 <- 10` jest `[10,1,2,3]`tablicy.</span><span class="sxs-lookup"><span data-stu-id="279a3-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="279a3-347">`arr w/ 2 <- 10` jest `[0,1,10,3]`tablicy.</span><span class="sxs-lookup"><span data-stu-id="279a3-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="279a3-348">`arr w/ 0..2..3 <- [10,12]` jest `[10,1,12,3]`tablicy.</span><span class="sxs-lookup"><span data-stu-id="279a3-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="279a3-349">Podobne wyrażenia istnieją dla nazwanych elementów w typach zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="279a3-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="279a3-350">Rozważmy przykład typu</span><span class="sxs-lookup"><span data-stu-id="279a3-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="279a3-351">Jeśli `c` zawiera wartość typu `Complex(1.,-1.)`, `c w/ Re <- 0.` jest wyrażeniem typu `Complex`, które oblicza `Complex(0.,-1.)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="279a3-352">Wyrażenia warunkowe</span><span class="sxs-lookup"><span data-stu-id="279a3-352">Conditional Expressions</span></span>

<span data-ttu-id="279a3-353">W przypadku dwóch innych wyrażeń tego samego typu i wyrażenia logicznego wyrażenie warunkowe może być utworzone przy użyciu znaku zapytania `?` a pionowy pasek `|`.</span><span class="sxs-lookup"><span data-stu-id="279a3-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="279a3-354">Na przykład `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="279a3-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="279a3-355">W tym przykładzie wartość wyrażenia warunkowego zostanie `c`, jeśli `a==b` ma wartość true, a `d`, jeśli ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="279a3-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="279a3-356">Dwa wyrażenia mogą oszacować do operacji, które mają te same dane wejściowe i wyjściowe, ale obsługują różne funktory.</span><span class="sxs-lookup"><span data-stu-id="279a3-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="279a3-357">W tym przypadku typ wyrażenia warunkowego jest operacją z tymi danymi wejściowymi i wyjściowymi, które obsługują wszystkie funktory obsługiwane przez oba wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="279a3-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="279a3-358">Na przykład jeśli `Op1`, `Op2`i `Op3` wszystkie są `Qubit[]=>Unit`, ale `Op1` obsługuje `Adjoint`, `Op2` obsługuje `Controlled`, a `Op3` obsługuje oba:</span><span class="sxs-lookup"><span data-stu-id="279a3-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="279a3-359">`flag ? Op1 | Op2` jest operacją `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="279a3-360">`flag ? Op1 | Op3` jest operacją `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="279a3-361">`flag ? Op2 | Op3` jest operacją `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="279a3-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="279a3-362">Jeśli jedno z dwóch możliwych wyrażeń wynikowych zawiera wywołanie funkcji lub operacji, to wywołanie będzie odbywać się tylko wtedy, gdy ten wynik będzie wartością wywołania.</span><span class="sxs-lookup"><span data-stu-id="279a3-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="279a3-363">Na przykład w przypadku `a==b ? C(qs) | D(qs)`, jeśli `a==b` ma wartość true, operacja `C` zostanie wywołana, a jeśli ma wartość false, tylko `D` zostanie wywołana.</span><span class="sxs-lookup"><span data-stu-id="279a3-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="279a3-364">Jest to podobne do krótkich obwodów w innych językach.</span><span class="sxs-lookup"><span data-stu-id="279a3-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="279a3-365">Pierwszeństwo operatorów</span><span class="sxs-lookup"><span data-stu-id="279a3-365">Operator Precedence</span></span>

<span data-ttu-id="279a3-366">Wszystkie operatory binarne są z prawej strony skojarzenia, z wyjątkiem `^`.</span><span class="sxs-lookup"><span data-stu-id="279a3-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="279a3-367">Nawiasy klamrowe, `[` i `]`, na potrzeby dzielenia i indeksowania tablic.</span><span class="sxs-lookup"><span data-stu-id="279a3-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="279a3-368">Funktory `Adjoint` i `Controlled` powiązać po indeksowaniu tablicy, ale przed wszystkimi innymi operatorami.</span><span class="sxs-lookup"><span data-stu-id="279a3-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="279a3-369">Nawiasy dla wywołania operacji i funkcji są również powiązane przed dowolnym operatorem, ale po indeksowaniu tablicy i funktory.</span><span class="sxs-lookup"><span data-stu-id="279a3-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="279a3-370">Operatory według pierwszeństwa, od najwyższego do najniższego:</span><span class="sxs-lookup"><span data-stu-id="279a3-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="279a3-371">Operator</span><span class="sxs-lookup"><span data-stu-id="279a3-371">Operator</span></span> | <span data-ttu-id="279a3-372">Większa</span><span class="sxs-lookup"><span data-stu-id="279a3-372">Arity</span></span> | <span data-ttu-id="279a3-373">Opis</span><span class="sxs-lookup"><span data-stu-id="279a3-373">Description</span></span> | <span data-ttu-id="279a3-374">Typy operandów</span><span class="sxs-lookup"><span data-stu-id="279a3-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="279a3-375">`!` końcowy</span><span class="sxs-lookup"><span data-stu-id="279a3-375">trailing `!`</span></span> | <span data-ttu-id="279a3-376">Jednostk</span><span class="sxs-lookup"><span data-stu-id="279a3-376">Unary</span></span> | <span data-ttu-id="279a3-377">Unwrap</span><span class="sxs-lookup"><span data-stu-id="279a3-377">Unwrap</span></span> | <span data-ttu-id="279a3-378">Dowolny typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="279a3-378">Any user-defined type</span></span>
 <span data-ttu-id="279a3-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="279a3-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="279a3-380">Jednostk</span><span class="sxs-lookup"><span data-stu-id="279a3-380">Unary</span></span> | <span data-ttu-id="279a3-381">Cyfra ujemna, dopełnienie bitowe, Negacja logiczna</span><span class="sxs-lookup"><span data-stu-id="279a3-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="279a3-382">`Int`, `BigInt` lub `Double` dla `-`, `Int` lub `BigInt` w `~~~``Bool` `not`</span><span class="sxs-lookup"><span data-stu-id="279a3-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="279a3-383">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-383">Binary</span></span> | <span data-ttu-id="279a3-384">Moc całkowita</span><span class="sxs-lookup"><span data-stu-id="279a3-384">Integer power</span></span> | <span data-ttu-id="279a3-385">`Int` lub `BigInt` dla podstawy, `Int` dla wykładnika</span><span class="sxs-lookup"><span data-stu-id="279a3-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="279a3-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="279a3-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="279a3-387">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-387">Binary</span></span> | <span data-ttu-id="279a3-388">Dzielenie, mnożenie, moduł całkowity</span><span class="sxs-lookup"><span data-stu-id="279a3-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="279a3-389">`Int`, `BigInt` lub `Double` dla `/` i `*`, `Int` lub `BigInt` dla `%`</span><span class="sxs-lookup"><span data-stu-id="279a3-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="279a3-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="279a3-390">`+`, `-`</span></span> | <span data-ttu-id="279a3-391">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-391">Binary</span></span> | <span data-ttu-id="279a3-392">Dodawanie lub łączenie ciągów i tablic, odejmowanie</span><span class="sxs-lookup"><span data-stu-id="279a3-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="279a3-393">`Int`, `BigInt` lub `Double`, dodatkowo `String` lub dowolnego typu tablicy dla `+`</span><span class="sxs-lookup"><span data-stu-id="279a3-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="279a3-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="279a3-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="279a3-395">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-395">Binary</span></span> | <span data-ttu-id="279a3-396">Lewy Shift, prawy Shift</span><span class="sxs-lookup"><span data-stu-id="279a3-396">Left shift, right shift</span></span> | <span data-ttu-id="279a3-397">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="279a3-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="279a3-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="279a3-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="279a3-399">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-399">Binary</span></span> | <span data-ttu-id="279a3-400">Mniejsze niż, mniejsze niż lub równe, większe niż, większe niż lub równe</span><span class="sxs-lookup"><span data-stu-id="279a3-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="279a3-401">`Int`, `BigInt` lub `Double`</span><span class="sxs-lookup"><span data-stu-id="279a3-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="279a3-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="279a3-402">`==`, `!=`</span></span> | <span data-ttu-id="279a3-403">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-403">Binary</span></span> | <span data-ttu-id="279a3-404">porównania równe, nierówne</span><span class="sxs-lookup"><span data-stu-id="279a3-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="279a3-405">dowolny typ pierwotny</span><span class="sxs-lookup"><span data-stu-id="279a3-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="279a3-406">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-406">Binary</span></span> | <span data-ttu-id="279a3-407">Bitowe i</span><span class="sxs-lookup"><span data-stu-id="279a3-407">Bitwise AND</span></span> | <span data-ttu-id="279a3-408">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="279a3-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="279a3-409">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-409">Binary</span></span> | <span data-ttu-id="279a3-410">Bitowe XOR</span><span class="sxs-lookup"><span data-stu-id="279a3-410">Bitwise XOR</span></span> | <span data-ttu-id="279a3-411">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="279a3-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="279a3-412">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-412">Binary</span></span> | <span data-ttu-id="279a3-413">Bitowe LUB</span><span class="sxs-lookup"><span data-stu-id="279a3-413">Bitwise OR</span></span> | <span data-ttu-id="279a3-414">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="279a3-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="279a3-415">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-415">Binary</span></span> | <span data-ttu-id="279a3-416">Logicznego AND</span><span class="sxs-lookup"><span data-stu-id="279a3-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="279a3-417">Binarny</span><span class="sxs-lookup"><span data-stu-id="279a3-417">Binary</span></span> | <span data-ttu-id="279a3-418">Logicznego OR</span><span class="sxs-lookup"><span data-stu-id="279a3-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="279a3-419">Plik binarny/Trzyelementowy</span><span class="sxs-lookup"><span data-stu-id="279a3-419">Binary/Ternary</span></span> | <span data-ttu-id="279a3-420">Operator zakresu</span><span class="sxs-lookup"><span data-stu-id="279a3-420">Range operator</span></span> | `Int`
 <span data-ttu-id="279a3-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="279a3-421">`?` `|`</span></span> | <span data-ttu-id="279a3-422">Trójargumentowy</span><span class="sxs-lookup"><span data-stu-id="279a3-422">Ternary</span></span> | <span data-ttu-id="279a3-423">Warunkowe</span><span class="sxs-lookup"><span data-stu-id="279a3-423">Conditional</span></span> | <span data-ttu-id="279a3-424">`Bool` po lewej stronie</span><span class="sxs-lookup"><span data-stu-id="279a3-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="279a3-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="279a3-425">`w/` `<-`</span></span> | <span data-ttu-id="279a3-426">Trójargumentowy</span><span class="sxs-lookup"><span data-stu-id="279a3-426">Ternary</span></span> | <span data-ttu-id="279a3-427">Kopiuj i Aktualizuj</span><span class="sxs-lookup"><span data-stu-id="279a3-427">Copy-and-update</span></span> | <span data-ttu-id="279a3-428">Zobacz [wyrażenia kopiowania i aktualizowania](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="279a3-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

---
title: 'Wyrażenia Q #'
description: 'Dowiedz się, jak określać, odwoływać i łączyć stałe, zmienne, operatory, operacje i funkcje jako wyrażenia w Q #.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683925"
---
# <a name="expressions"></a><span data-ttu-id="b390a-103">Wyrażenia</span><span class="sxs-lookup"><span data-stu-id="b390a-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="b390a-104">Grupowanie</span><span class="sxs-lookup"><span data-stu-id="b390a-104">Grouping</span></span>

<span data-ttu-id="b390a-105">Uwzględniając dowolne wyrażenie, to samo wyrażenie ujęte w nawiasy jest wyrażeniem tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="b390a-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="b390a-106">Na przykład, `(7)` jest `Int` wyrażeniem, `([1,2,3])` jest wyrażeniem typu Array `Int`-s i `((1,2))` jest wyrażeniem typu. `(Int, Int)`</span><span class="sxs-lookup"><span data-stu-id="b390a-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="b390a-107">Równoważność między wartościami prostymi a krotkami jednoelementowymi opisanymi w [modelu typu](xref:microsoft.quantum.language.type-model#tuple-types) usuwa niejednoznaczność między `(6)` grupami i `(6)` jako spójną krotką.</span><span class="sxs-lookup"><span data-stu-id="b390a-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="b390a-108">Symbole</span><span class="sxs-lookup"><span data-stu-id="b390a-108">Symbols</span></span>

<span data-ttu-id="b390a-109">Nazwa symbolu powiązanego lub przypisana do wartości typu `'T` jest wyrażeniem typu. `'T`</span><span class="sxs-lookup"><span data-stu-id="b390a-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="b390a-110">Na przykład, jeśli symbol `count` jest powiązany z wartością `5`całkowitą, `count` jest wyrażeniem liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="b390a-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="b390a-111">Wyrażenia liczbowe</span><span class="sxs-lookup"><span data-stu-id="b390a-111">Numeric Expressions</span></span>

<span data-ttu-id="b390a-112">Wyrażenia liczbowe są wyrażeniami typu `Int`, `BigInt`, lub `Double`.</span><span class="sxs-lookup"><span data-stu-id="b390a-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="b390a-113">Oznacza to, że są to liczby całkowite lub zmiennoprzecinkowe.</span><span class="sxs-lookup"><span data-stu-id="b390a-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="b390a-114">`Int`literały w Q # są identyczne z literałami całkowitymi w języku C#, z tą różnicą, że nie są wymagane żadne końcowe litery "l" lub "L" (lub dozwolone).</span><span class="sxs-lookup"><span data-stu-id="b390a-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="b390a-115">Liczby całkowite szesnastkowe i binarne są obsługiwane odpowiednio prefiksem "0x" i "0b".</span><span class="sxs-lookup"><span data-stu-id="b390a-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="b390a-116">`BigInt`literały w Q # są identyczne z ciągami Big Integer w programie .NET, z końcowym "l" lub "L".</span><span class="sxs-lookup"><span data-stu-id="b390a-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="b390a-117">Szesnastkowe duże liczby całkowite są obsługiwane z prefiksem "0x".</span><span class="sxs-lookup"><span data-stu-id="b390a-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="b390a-118">W ten sposób wszystkie prawidłowe zastosowania `BigInt` literałów są następujące:</span><span class="sxs-lookup"><span data-stu-id="b390a-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="b390a-119">`Double`literały w Q # są takie same jak literały podwójne w języku C#, z tą różnicą, że nie jest wymagane końcowe "d" lub "D" (lub dozwolone).</span><span class="sxs-lookup"><span data-stu-id="b390a-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="b390a-120">Jeśli wyrażenie tablicy dowolnego `Int` typu elementu, wyrażenie może być utworzone przy użyciu `Length` wbudowanej funkcji, z wyrażeniem tablicy ujętym w nawiasy `(` i. `)`</span><span class="sxs-lookup"><span data-stu-id="b390a-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="b390a-121">Na przykład, jeśli `a` jest powiązany z tablicą, `Length(a)` jest wyrażeniem liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="b390a-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="b390a-122">Jeśli `b` jest tablicą tablic liczb całkowitych, `Int[][]`, a następnie `Length(b)` jest liczbą tablic `b`w, i `Length(b[1])` jest liczbą liczb całkowitych w drugiej tablicy podrzędnej w. `b`</span><span class="sxs-lookup"><span data-stu-id="b390a-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="b390a-123">Uwzględniając dwa `+`wyrażenia liczbowe tego samego typu, operatory binarne, `-` `*`, i `/` mogą być używane do tworzenia nowego wyrażenia liczbowego.</span><span class="sxs-lookup"><span data-stu-id="b390a-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="b390a-124">Typ nowego wyrażenia będzie taki sam jak typy wyrażeń składowych.</span><span class="sxs-lookup"><span data-stu-id="b390a-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="b390a-125">W przypadku dwóch wyrażeń całkowitych operator `^` binarny (potęga) może służyć do tworzenia nowego wyrażenia liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="b390a-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="b390a-126">Podobnie, `^` można użyć z dwoma wyrażeniami podwójnymi, aby utworzyć nowe wyrażenie podwójne.</span><span class="sxs-lookup"><span data-stu-id="b390a-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="b390a-127">Na koniec `^` , może być używany z dużą liczbą całkowitą z lewej strony i liczbą całkowitą z prawej strony, aby utworzyć nowe wyrażenie Big Integer.</span><span class="sxs-lookup"><span data-stu-id="b390a-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="b390a-128">W takim przypadku drugi parametr musi pasować do 32 bitów; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b390a-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="b390a-129">W przypadku dwóch wyrażeń całkowitych lub dużych liczb całkowitych można utworzyć nowe wyrażenie typu Integer lub Big Integer `%` przy użyciu operatorów ( `&&&` moduł), (bitowe `|||` and), (BITOWEGO or `^^^` ) lub (bitowe XOR).</span><span class="sxs-lookup"><span data-stu-id="b390a-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="b390a-130">W przypadku wyrażenia typu Integer lub Big Integer po lewej stronie i wyrażenia liczb całkowitych po prawej stronie operatory `<<<` (arytmetyczne przesunięcie w lewo) `>>>` lub (arytmetyczne przesunięcie w prawo) mogą być używane do tworzenia nowego wyrażenia z tym samym typem co lewe wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="b390a-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="b390a-131">Drugi parametr (wartość przesunięcia) dla operacji Shift musi być większy lub równy zero; zachowanie dla ujemnych kwot przesunięcia jest niezdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="b390a-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="b390a-132">Wartość przesunięcia dla operacji przesunięcia musi być również zgodna z 32 bitowymi; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b390a-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="b390a-133">Jeśli liczba, która ma zostać przesunięta jest liczbą całkowitą, jest interpretowana `mod 64`wartość przesunięcia. oznacza to, że przesunięcie 1 i przesunięcie 65 mają ten sam efekt.</span><span class="sxs-lookup"><span data-stu-id="b390a-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="b390a-134">W przypadku wartości liczb całkowitych i dużych liczb całkowitych przesunięcia są arytmetyczne.</span><span class="sxs-lookup"><span data-stu-id="b390a-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="b390a-135">Przesunięcie wartości ujemnej w lewo lub w prawo spowoduje powstanie liczby ujemnej.</span><span class="sxs-lookup"><span data-stu-id="b390a-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="b390a-136">Oznacza to, że przesunięcie jeden krok w lewo lub w prawo jest dokładnie takie samo jak mnożenie lub dzielenie odpowiednio przez 2.</span><span class="sxs-lookup"><span data-stu-id="b390a-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="b390a-137">Dzielenie liczb całkowitych i moduł całkowity są zgodne z tym samym zachowaniem dla liczb ujemnych w języku C#.</span><span class="sxs-lookup"><span data-stu-id="b390a-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="b390a-138">Oznacza to, `a % b` że będzie zawsze mieć ten sam znak `a`jako i `b * (a / b) + a % b` zawsze będzie równa `a`się.</span><span class="sxs-lookup"><span data-stu-id="b390a-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="b390a-139">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b390a-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="b390a-140">5</span><span class="sxs-lookup"><span data-stu-id="b390a-140">5</span></span> | <span data-ttu-id="b390a-141">2</span><span class="sxs-lookup"><span data-stu-id="b390a-141">2</span></span> | <span data-ttu-id="b390a-142">2</span><span class="sxs-lookup"><span data-stu-id="b390a-142">2</span></span> | <span data-ttu-id="b390a-143">1</span><span class="sxs-lookup"><span data-stu-id="b390a-143">1</span></span>
 <span data-ttu-id="b390a-144">5</span><span class="sxs-lookup"><span data-stu-id="b390a-144">5</span></span> | <span data-ttu-id="b390a-145">-2</span><span class="sxs-lookup"><span data-stu-id="b390a-145">-2</span></span> | <span data-ttu-id="b390a-146">-2</span><span class="sxs-lookup"><span data-stu-id="b390a-146">-2</span></span> | <span data-ttu-id="b390a-147">1</span><span class="sxs-lookup"><span data-stu-id="b390a-147">1</span></span>
 <span data-ttu-id="b390a-148">-5</span><span class="sxs-lookup"><span data-stu-id="b390a-148">-5</span></span> | <span data-ttu-id="b390a-149">2</span><span class="sxs-lookup"><span data-stu-id="b390a-149">2</span></span> | <span data-ttu-id="b390a-150">-2</span><span class="sxs-lookup"><span data-stu-id="b390a-150">-2</span></span> | <span data-ttu-id="b390a-151">-1</span><span class="sxs-lookup"><span data-stu-id="b390a-151">-1</span></span>
 <span data-ttu-id="b390a-152">-5</span><span class="sxs-lookup"><span data-stu-id="b390a-152">-5</span></span> | <span data-ttu-id="b390a-153">-2</span><span class="sxs-lookup"><span data-stu-id="b390a-153">-2</span></span> | <span data-ttu-id="b390a-154">2</span><span class="sxs-lookup"><span data-stu-id="b390a-154">2</span></span> | <span data-ttu-id="b390a-155">-1</span><span class="sxs-lookup"><span data-stu-id="b390a-155">-1</span></span>

<span data-ttu-id="b390a-156">Dzielenie z dużymi liczbami całkowitymi i moduł działa w taki sam sposób.</span><span class="sxs-lookup"><span data-stu-id="b390a-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="b390a-157">Mając każde wyrażenie liczbowe, nowe wyrażenie może być utworzone za pomocą operatora `-` jednoargumentowego.</span><span class="sxs-lookup"><span data-stu-id="b390a-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="b390a-158">Nowe wyrażenie będzie tego samego typu co wyrażenie elementu.</span><span class="sxs-lookup"><span data-stu-id="b390a-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="b390a-159">W przypadku dowolnego wyrażenia typu Integer lub Big Integer nowe wyrażenie tego samego typu może być sformułowane przy użyciu `~~~` operatora jednoargumentowego (dopełnienie bitowe).</span><span class="sxs-lookup"><span data-stu-id="b390a-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="b390a-160">Wyrażenia logiczne</span><span class="sxs-lookup"><span data-stu-id="b390a-160">Boolean Expressions</span></span>

<span data-ttu-id="b390a-161">Dwie `Bool` wartości literału są `true` i `false`.</span><span class="sxs-lookup"><span data-stu-id="b390a-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="b390a-162">Uwzględniając wszystkie dwa wyrażenia tego samego typu pierwotnego, operatory `==` i `!=` mogą być używane do konstruowania `Bool` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b390a-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="b390a-163">Wyrażenie będzie prawdziwe, jeśli dwa wyrażenia są równe, i wartość false, jeśli nie.</span><span class="sxs-lookup"><span data-stu-id="b390a-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="b390a-164">Wartości typów zdefiniowanych przez użytkownika mogą nie być porównywane. można porównać tylko ich nieopakowane wartości.</span><span class="sxs-lookup"><span data-stu-id="b390a-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="b390a-165">Na przykład przy użyciu operatora `!` "unotocz" (wyjaśnione na [stronie modelu typu Q #](xref:microsoft.quantum.language.type-model#user-defined-types)),</span><span class="sxs-lookup"><span data-stu-id="b390a-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="b390a-166">Porównywanie równości `Qubit` dla wartości jest równość tożsamości; oznacza to, czy dwa wyrażenia identyfikują ten sam qubit.</span><span class="sxs-lookup"><span data-stu-id="b390a-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="b390a-167">Stan dwóch qubits nie jest porównywany, dostępny, mierzony ani modyfikowany przez to porównanie.</span><span class="sxs-lookup"><span data-stu-id="b390a-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="b390a-168">Porównywanie równości `Double` dla wartości może być mylące ze względu na efekt zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="b390a-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="b390a-169">Na przykład `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="b390a-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="b390a-170">Uwzględniając wszystkie `>`dwa wyrażenia liczbowe, operatory binarne, `<` `>=`, i `<=` mogą być używane do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli pierwsze wyrażenie jest odpowiednio większe niż, mniejsze niż, większe niż lub równe lub mniejsze lub równe drugiemu wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="b390a-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="b390a-171">W przypadku wszystkich dwóch wyrażeń logicznych operatory `and` i `or` mogą być używane do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli oba wyrażenia (komp. or lub Both) mają wartość true.</span><span class="sxs-lookup"><span data-stu-id="b390a-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="b390a-172">Mając każde wyrażenie logiczne, operator `not` jednoargumentowy może służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli wyrażenie elementu składowego ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="b390a-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="b390a-173">Wyrażenia ciągów</span><span class="sxs-lookup"><span data-stu-id="b390a-173">String Expressions</span></span>

<span data-ttu-id="b390a-174">Funkcja Q # umożliwia używanie ciągów w `fail` instrukcji i funkcji `Log` standardowej.</span><span class="sxs-lookup"><span data-stu-id="b390a-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="b390a-175">Ciągi w Q # są literałami lub interpolowanymi ciągami.</span><span class="sxs-lookup"><span data-stu-id="b390a-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="b390a-176">Literały ciągu są podobne do prostych literałów ciągu w większości języków: sekwencji znaków Unicode ujętych w podwójne cudzysłowy `"`.</span><span class="sxs-lookup"><span data-stu-id="b390a-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="b390a-177">Wewnątrz `\` ciągu znak ukośnika odwrotnego może być używany do ucieczki podwójnego znaku cudzysłowu i do wstawiania nowej linii `\n`jako, powrotu karetki jako `\r`i karty jako. `\t`</span><span class="sxs-lookup"><span data-stu-id="b390a-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="b390a-178">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b390a-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="b390a-179">Składnia Q # dla interpolacji ciągów jest podzbiorem składni języka C# 7,0; Usługa Q # nie obsługuje ciągów interpolowanych Verbatim (wiele wierszy).</span><span class="sxs-lookup"><span data-stu-id="b390a-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="b390a-180">Zobacz [*interpolowane ciągi*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) dla składni języka C#.</span><span class="sxs-lookup"><span data-stu-id="b390a-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="b390a-181">Wyrażenia wewnątrz ciągu interpolowanego są zgodne z składnią Q #, a nie składnią języka C#.</span><span class="sxs-lookup"><span data-stu-id="b390a-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="b390a-182">Dowolne prawidłowe wyrażenie Q # może pojawić się w ciągu interpolowanym.</span><span class="sxs-lookup"><span data-stu-id="b390a-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="b390a-183">Wyrażenia qubit</span><span class="sxs-lookup"><span data-stu-id="b390a-183">Qubit Expressions</span></span>

<span data-ttu-id="b390a-184">Jedyne `Qubit` wyrażenia to symbole, które są powiązane `Qubit` z wartościami lub tablicami `Qubit` elementów tablic.</span><span class="sxs-lookup"><span data-stu-id="b390a-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="b390a-185">Brak `Qubit` literałów.</span><span class="sxs-lookup"><span data-stu-id="b390a-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="b390a-186">Wyrażenia Pauli</span><span class="sxs-lookup"><span data-stu-id="b390a-186">Pauli Expressions</span></span>

<span data-ttu-id="b390a-187">Cztery `Pauli` wartości `PauliI`,, `PauliX` `PauliY`, i `PauliZ`, są prawidłowymi `Pauli` wyrażeniami.</span><span class="sxs-lookup"><span data-stu-id="b390a-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="b390a-188">Inaczej niż to, jedyne `Pauli` wyrażenia to symbole, które są powiązane `Pauli` z wartościami lub tablicami `Pauli` elementów tablic.</span><span class="sxs-lookup"><span data-stu-id="b390a-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="b390a-189">Wyrażenia wynikowe</span><span class="sxs-lookup"><span data-stu-id="b390a-189">Result Expressions</span></span>

<span data-ttu-id="b390a-190">Dwie `Result` wartości `One` i `Zero`są prawidłowymi `Result` wyrażeniami.</span><span class="sxs-lookup"><span data-stu-id="b390a-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="b390a-191">Inaczej niż to, jedyne `Result` wyrażenia to symbole, które są powiązane `Result` z wartościami lub tablicami `Result` elementów tablic.</span><span class="sxs-lookup"><span data-stu-id="b390a-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="b390a-192">W szczególności należy zauważyć, `One` że nie jest taka sama jak liczba `1`całkowita i nie ma żadnej bezpośredniej konwersji między nimi.</span><span class="sxs-lookup"><span data-stu-id="b390a-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="b390a-193">Ta sama wartość dotyczy `Zero` i. `0`</span><span class="sxs-lookup"><span data-stu-id="b390a-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="b390a-194">Wyrażenia zakresu</span><span class="sxs-lookup"><span data-stu-id="b390a-194">Range Expressions</span></span>

<span data-ttu-id="b390a-195">Każde trzy `Int` `start`wyrażenie, `step`, i `stop`, `start .. step .. stop` jest wyrażeniem zakresu, którego pierwszy element jest `start`, drugi element jest `start+step`, trzeci element jest `start+step+step`itp., do do `stop` .</span><span class="sxs-lookup"><span data-stu-id="b390a-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="b390a-196">Zakres może być pusty, jeśli na przykład `step` jest wartością dodatnią i `stop < start`.</span><span class="sxs-lookup"><span data-stu-id="b390a-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="b390a-197">`stop` Ostatnim elementem zakresu będzie, jeśli różnica między `start` i `stop` jest całkowitą wielokrotnością; `step` oznacza to, że zakres jest włącznie na obu końcach.</span><span class="sxs-lookup"><span data-stu-id="b390a-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="b390a-198">Uwzględniając wszystkie dwa `Int` wyrażenia `start` i `stop`, `start .. stop` jest wyrażenie zakresu, które jest równe `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="b390a-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="b390a-199">Należy zauważyć, że implikowana `step` wartość to + 1 `stop` , nawet jeśli `start`jest mniejsza niż; w takim przypadku zakres jest pusty.</span><span class="sxs-lookup"><span data-stu-id="b390a-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="b390a-200">Oto kilka przykładowych zakresów:</span><span class="sxs-lookup"><span data-stu-id="b390a-200">Some example ranges are:</span></span>

- <span data-ttu-id="b390a-201">`1..3`jest zakresem 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="b390a-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="b390a-202">`2..2..5`jest zakresem od 2 do 4.</span><span class="sxs-lookup"><span data-stu-id="b390a-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="b390a-203">`2..2..6`jest zakresem 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="b390a-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="b390a-204">`6..-2..2`jest zakresem 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="b390a-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="b390a-205">`2..1`jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="b390a-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="b390a-206">`2..6..7`jest zakresem 2.</span><span class="sxs-lookup"><span data-stu-id="b390a-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="b390a-207">`2..2..1`jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="b390a-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="b390a-208">`1..-1..2`jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="b390a-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="b390a-209">Możliwe do przewyrażenia</span><span class="sxs-lookup"><span data-stu-id="b390a-209">Callable Expressions</span></span>

<span data-ttu-id="b390a-210">Możliwy do przeprowadzenia literał jest nazwą operacji lub funkcji zdefiniowanej w zakresie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="b390a-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="b390a-211">Na przykład, `X` to literał operacji odwołujący się do standardowej operacji `X` biblioteki i `Message` jest literalną funkcją, która odwołuje się do standardowej `Message` funkcji biblioteki.</span><span class="sxs-lookup"><span data-stu-id="b390a-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="b390a-212">Jeśli operacja obsługuje `Adjoint` Funktor, `Adjoint op` to wyrażenie operacji.</span><span class="sxs-lookup"><span data-stu-id="b390a-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="b390a-213">Podobnie, jeśli operacja obsługuje `Controlled` Funktor, a następnie `Controlled op` jest wyrażeniem operacji.</span><span class="sxs-lookup"><span data-stu-id="b390a-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="b390a-214">Typy tych wyrażeń są określone w [funktory](xref:microsoft.quantum.language.type-model#functors).</span><span class="sxs-lookup"><span data-stu-id="b390a-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="b390a-215">Funktory (`Adjoint` i `Controlled`) wiąże się bardziej ściśle niż wszystkie inne operatory, z wyjątkiem operatora `!` rozwinięcia i indeksowania tablicy `[]`przy użyciu.</span><span class="sxs-lookup"><span data-stu-id="b390a-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="b390a-216">W ten sposób obowiązują wszystkie kwestie prawne, przy założeniu, że operacje obsługują użycie funktory:</span><span class="sxs-lookup"><span data-stu-id="b390a-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="b390a-217">Możliwy do oddzielenia literału można użyć jako wartości, powiedzmy, aby przypisać do zmiennej lub przekazać do innego elementu.</span><span class="sxs-lookup"><span data-stu-id="b390a-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="b390a-218">W takim przypadku, jeśli wywoływany ma parametry typu, muszą one być podane jako część wartości możliwej do napisania.</span><span class="sxs-lookup"><span data-stu-id="b390a-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="b390a-219">Wartość możliwej do odwoływać nie może mieć żadnych nieokreślonych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="b390a-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="b390a-220">Na przykład jeśli `Fun` jest funkcją z podpisem `'T1->Unit`:</span><span class="sxs-lookup"><span data-stu-id="b390a-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="b390a-221">Wywoływanie wyrażeń wywołania</span><span class="sxs-lookup"><span data-stu-id="b390a-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="b390a-222">Dane wyrażenie możliwego do wywołania (operacji lub funkcji) i wyrażenie spójnej kolekcji typu wejściowego w podpisie, wyrażenie wywoływania może być sformułowane przez dołączenie wyrażenia krotki do możliwego do wywołania wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b390a-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="b390a-223">Typ wyrażenia wywołania jest typem wyjściowym podpisu, który ma zostać wywołany.</span><span class="sxs-lookup"><span data-stu-id="b390a-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="b390a-224">Na `Op` przykład jeśli jest operacją z podpisem `((Int, Qubit) => Double)`, `Op(3, qubit1)` jest wyrażeniem typu `Double`.</span><span class="sxs-lookup"><span data-stu-id="b390a-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="b390a-225">Podobnie, jeśli `Sin` jest funkcją z podpisem `(Double -> Double)`, `Sin(0.1)` jest wyrażeniem typu `Double`.</span><span class="sxs-lookup"><span data-stu-id="b390a-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="b390a-226">Na koniec, `Builder` jeśli jest funkcją z podpisem `(Int -> (Int -> Int))`, `Builder(3)` to funkcja od do int.</span><span class="sxs-lookup"><span data-stu-id="b390a-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="b390a-227">Wywołanie wyniku wyrażenia z wartościami możliwymi do wywołania wymaga dodatkowej pary nawiasów wokół wartościowego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b390a-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="b390a-228">W związku z tym, aby wywołać wynik `Builder` wywołania z poprzedniego akapitu, poprawna składnia to:</span><span class="sxs-lookup"><span data-stu-id="b390a-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="b390a-229">W przypadku wywołania sparametryzowanego typu, rzeczywiste parametry typu można określić w nawiasach `<` kątowych i `>` po wyrażeniu możliwym do wywołania.</span><span class="sxs-lookup"><span data-stu-id="b390a-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="b390a-230">Zwykle nie jest to konieczne, ponieważ kompilator Q # wykryje rzeczywiste typy.</span><span class="sxs-lookup"><span data-stu-id="b390a-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="b390a-231">Jest to wymagane w przypadku częściowej aplikacji (patrz poniżej), jeśli argument z parametrem sparametryzowanym nie został określony.</span><span class="sxs-lookup"><span data-stu-id="b390a-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="b390a-232">Jest to również czasami przydatne, gdy przekazywanie operacji z różnymi Funktor obsługuje do możliwego do odwoływać.</span><span class="sxs-lookup"><span data-stu-id="b390a-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="b390a-233">Na przykład, jeśli `Func` ma `('T1, 'T2, 'T1) -> 'T2`sygnaturę `Op1` i `Op2` `(Qubit[] => Unit is Adj)`ma sygnaturę i `Op3` ma sygnaturę `(Qubit[] => Unit)`, do `Func` wywołania `Op1` jako pierwszy argument, `Op2` jako drugi i `Op3` jako trzeci:</span><span class="sxs-lookup"><span data-stu-id="b390a-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="b390a-234">Specyfikacja typu jest wymagana, ponieważ `Op3` i `Op1` ma różne typy, więc kompilator będzie traktować ten sposób jako niejednoznaczny bez specyfikacji.</span><span class="sxs-lookup"><span data-stu-id="b390a-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="b390a-235">Aplikacja częściowa</span><span class="sxs-lookup"><span data-stu-id="b390a-235">Partial Application</span></span>

<span data-ttu-id="b390a-236">Po otrzymaniu możliwego do przetworzenia wyrażenia można utworzyć nowe wywoływanie, dostarczając podzestaw argumentów do obiektu.</span><span class="sxs-lookup"><span data-stu-id="b390a-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="b390a-237">Jest to nazywane _częściową aplikacją_.</span><span class="sxs-lookup"><span data-stu-id="b390a-237">This is called _partial application_.</span></span>

<span data-ttu-id="b390a-238">W Q #, częściowo zastosowane wywołanie jest wyrażane przez zapisanie wyrażenia zwykłego wywołania, ale przy użyciu znaku podkreślenia `_`, dla nieokreślonych argumentów.</span><span class="sxs-lookup"><span data-stu-id="b390a-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="b390a-239">Wynikowe wywoływanie ma ten sam typ wyniku co podstawowy możliwy do przetworzenie i te same specjalizacje dla operacji.</span><span class="sxs-lookup"><span data-stu-id="b390a-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="b390a-240">Typ danych wejściowych częściowej aplikacji jest po prostu oryginalnym typem z określonymi argumentami.</span><span class="sxs-lookup"><span data-stu-id="b390a-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="b390a-241">Jeśli zmienna modyfikowalna jest przenoszona jako określony argument podczas tworzenia częściowej aplikacji, używana jest bieżąca wartość zmiennej.</span><span class="sxs-lookup"><span data-stu-id="b390a-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="b390a-242">Późniejsze zmiany wartości zmiennej nie wpłyną na częściową aplikację.</span><span class="sxs-lookup"><span data-stu-id="b390a-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="b390a-243">Na przykład, jeśli `Op` ma typ `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="b390a-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="b390a-244">`Op(5,(_,_))`ma typ `(((Qubit,Qubit), Double) => Unit is Adj)`, a więc ma `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="b390a-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="b390a-245">`Op(_,(_,1.0))`ma typ `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="b390a-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="b390a-246">`Op(_,((q1,q2),_))`ma typ `((Int,Double) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="b390a-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="b390a-247">Należy zauważyć, że w tym miejscu zastosowano jednokrotną równoważność krotki.</span><span class="sxs-lookup"><span data-stu-id="b390a-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="b390a-248">Jeśli częściowo zastosowane wywołanie ma parametry typu, których nie można wywnioskować przez kompilator, muszą one być dostarczone w lokacji wywołania.</span><span class="sxs-lookup"><span data-stu-id="b390a-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="b390a-249">Częściowa aplikacja nie może mieć żadnych nieokreślonych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="b390a-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="b390a-250">Na przykład, jeśli `Op` ma typ `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="b390a-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="b390a-251">Rekursja</span><span class="sxs-lookup"><span data-stu-id="b390a-251">Recursion</span></span>

<span data-ttu-id="b390a-252">Liczba wywoływanych Q może być bezpośrednio lub pośrednio cykliczna.</span><span class="sxs-lookup"><span data-stu-id="b390a-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="b390a-253">Oznacza to, że operacja lub funkcja może wywołać się sama lub wywołać inne wywołanie, które bezpośrednio lub pośrednio wywołuje operację, którą można wywołać.</span><span class="sxs-lookup"><span data-stu-id="b390a-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="b390a-254">Istnieją jednak dwa ważne komentarze dotyczące korzystania z rekursji:</span><span class="sxs-lookup"><span data-stu-id="b390a-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="b390a-255">Użycie rekursji w operacjach może zakłócać pewne optymalizacje.</span><span class="sxs-lookup"><span data-stu-id="b390a-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="b390a-256">Może to mieć znaczny wpływ na czas wykonywania algorytmu.</span><span class="sxs-lookup"><span data-stu-id="b390a-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="b390a-257">W przypadku wykonywania na rzeczywistym urządzeniu Quantum przestrzeń stosu może być ograniczona, a więc Szczegółowa rekursja może prowadzić do błędu czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b390a-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="b390a-258">W szczególności kompilator Q # i środowisko wykonawcze nie identyfikują i nie optymalizują rekursji końcowego.</span><span class="sxs-lookup"><span data-stu-id="b390a-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="b390a-259">Wyrażenia krotki</span><span class="sxs-lookup"><span data-stu-id="b390a-259">Tuple Expressions</span></span>

<span data-ttu-id="b390a-260">Literał krotki to sekwencja wyrażeń elementu odpowiedniego typu, rozdzielona przecinkami, ujęta w `(` i. `)`</span><span class="sxs-lookup"><span data-stu-id="b390a-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="b390a-261">Na przykład `(1, One)` jest `(Int, Result)` wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="b390a-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="b390a-262">W przypadku innych niż literały jedynymi wyrażeniami krotek są symbole, które są powiązane z wartościami krotki, elementami tablicy tablic krotek i wywoływanie wywołań, które zwracają krotki.</span><span class="sxs-lookup"><span data-stu-id="b390a-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="b390a-263">Wyrażenia typu zdefiniowanego przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="b390a-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="b390a-264">Literał typu zdefiniowanego przez użytkownika składa się z nazwy typu, a następnie literału krotki typu krotki podstawowej typu.</span><span class="sxs-lookup"><span data-stu-id="b390a-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="b390a-265">Na przykład, jeśli `IntPair` jest typem zdefiniowanym przez użytkownika na `(Int, Int)`podstawie, `IntPair(2,3)` byłby on prawidłowym literałem tego typu.</span><span class="sxs-lookup"><span data-stu-id="b390a-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="b390a-266">Oprócz literałów jedynymi wyrażeniami typu zdefiniowanego przez użytkownika są symbole, które są powiązane z wartościami tego typu, elementy tablicy tablic tego typu i wywoływanie wywołań, które zwracają ten typ.</span><span class="sxs-lookup"><span data-stu-id="b390a-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="b390a-267">Odpakowywanie wyrażeń</span><span class="sxs-lookup"><span data-stu-id="b390a-267">Unwrap Expressions</span></span>

<span data-ttu-id="b390a-268">W Q # operator rozwinięcia jest końcowym wykrzyknikiem `!`.</span><span class="sxs-lookup"><span data-stu-id="b390a-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="b390a-269">Na przykład, jeśli `IntPair` jest typem zdefiniowanym przez użytkownika z typem `(Int, Int)`źródłowym i `s` była zmienną z wartością `IntPair(2,3)`, wówczas `s!` zostałby. `(2,3)`</span><span class="sxs-lookup"><span data-stu-id="b390a-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="b390a-270">Dla typów zdefiniowanych przez użytkownika, zdefiniowanych w warunkach innych typów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b390a-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="b390a-271">operatora rozwinięcia można powtórzyć; na przykład `s!!` wskazuje podwójnie nieopakowaną wartość `s`.</span><span class="sxs-lookup"><span data-stu-id="b390a-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="b390a-272">W takim przypadku `WrappedPair` , jeśli jest typem zdefiniowanym przez użytkownika z `IntPair`typem źródłowym `t` i jest zmienną z wartością `WrappedPair(IntPair(1,2))`, wówczas `t!!` zostałby `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="b390a-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="b390a-273">`!` Operator ma wyższy priorytet niż wszystkie inne operatory inne niż `[]` dla indeksowania tablicy i dzielenia.</span><span class="sxs-lookup"><span data-stu-id="b390a-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="b390a-274">`!`i `[]` Powiązywanie pozycyjne; oznacza to, `a[i]![3]` że powinna być odczytana `((a[i])!)[3]`jako `i`: Weź element " `a`th", Odpakuj go, a następnie Pobierz trzeci element nieopakowanej wartości (która musi być tablicą).</span><span class="sxs-lookup"><span data-stu-id="b390a-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="b390a-275">Pierwszeństwo `!` operatora ma jeden wpływ, który może nie być oczywisty.</span><span class="sxs-lookup"><span data-stu-id="b390a-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="b390a-276">Jeśli funkcja lub operacja zwraca wartość, która staje się nieopakowana, wywołanie funkcji lub operacji musi być ujęte w nawiasy, tak aby krotka argumentu była powiązana z wywołaniem, a nie z odwinięciem.</span><span class="sxs-lookup"><span data-stu-id="b390a-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="b390a-277">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b390a-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="b390a-278">Wyrażenia tablic</span><span class="sxs-lookup"><span data-stu-id="b390a-278">Array Expressions</span></span>

<span data-ttu-id="b390a-279">Literał tablicowy jest sekwencją co najmniej jednego wyrażenia elementu, rozdzielonych przecinkami, ujęty w `[` i `]`.</span><span class="sxs-lookup"><span data-stu-id="b390a-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="b390a-280">Wszystkie elementy muszą być zgodne z tym samym typem.</span><span class="sxs-lookup"><span data-stu-id="b390a-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="b390a-281">Jeśli wspólny typ elementu jest operacją lub typem funkcji, wszystkie elementy muszą mieć te same typy danych wejściowych i wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="b390a-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="b390a-282">Typ elementu tablicy będzie obsługiwał wszystkie funktory, które są obsługiwane przez wszystkie elementy.</span><span class="sxs-lookup"><span data-stu-id="b390a-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="b390a-283">Na przykład jeśli `Op1` `Op2`,, i `Op3` wszystkie są `Qubit[] => Unit`, ale `Op1` obsługuje `Adjoint`, `Op2` obsługuje `Controlled`i `Op3` obsługuje obie:</span><span class="sxs-lookup"><span data-stu-id="b390a-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="b390a-284">`[Op1, Op2]`jest tablicą `(Qubit[] => Unit)` operacji.</span><span class="sxs-lookup"><span data-stu-id="b390a-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="b390a-285">`[Op1, Op3]`jest tablicą `(Qubit[] => Unit is Adj)` operacji.</span><span class="sxs-lookup"><span data-stu-id="b390a-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="b390a-286">`[Op2, Op3]`jest tablicą `(Qubit[] => Unit is Ctl)` operacji.</span><span class="sxs-lookup"><span data-stu-id="b390a-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="b390a-287">Puste literały tablicowe `[]`,, są niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="b390a-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="b390a-288">Zamiast używać `new ★[0]`, gdzie `★` jest jako symbol zastępczy dla odpowiedniego typu, umożliwia utworzenie odpowiedniej tablicy o długości zero.</span><span class="sxs-lookup"><span data-stu-id="b390a-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="b390a-289">Mając daną dwie tablice tego samego typu, operator binarny `+` może służyć do tworzenia nowej tablicy, która jest połączeniem dwóch tablic.</span><span class="sxs-lookup"><span data-stu-id="b390a-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="b390a-290">Na przykład `[1,2,3] + [4,5,6]` ma `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="b390a-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="b390a-291">Tworzenie tablicy</span><span class="sxs-lookup"><span data-stu-id="b390a-291">Array Creation</span></span>

<span data-ttu-id="b390a-292">Uwzględniając typ i `Int` wyrażenie, `new` operator może służyć do przydzielenia nowej tablicy o danym rozmiarze.</span><span class="sxs-lookup"><span data-stu-id="b390a-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="b390a-293">Na przykład `new Int[i+1]` przydzieli nową `Int` tablicę z `i+1` elementami.</span><span class="sxs-lookup"><span data-stu-id="b390a-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="b390a-294">Elementy nowej tablicy są inicjowane z wartością domyślną zależną od typu.</span><span class="sxs-lookup"><span data-stu-id="b390a-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="b390a-295">W większości przypadków jest to pewna odmiana zero.</span><span class="sxs-lookup"><span data-stu-id="b390a-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="b390a-296">W przypadku qubits i elementów, które są odwołaniami do jednostek, nie ma żadnej rozsądnej wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="b390a-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="b390a-297">W tym przypadku dla tych typów wartość domyślna to nieprawidłowe odwołanie, którego nie można użyć bez powodowania błędu czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b390a-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="b390a-298">Jest to podobne do odwołania o wartości null w językach, takich jak C# lub Java.</span><span class="sxs-lookup"><span data-stu-id="b390a-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="b390a-299">Tablice zawierające qubits lub elementy wywoływane muszą zostać prawidłowo zainicjowane przy użyciu wartości innych niż domyślne, zanim ich elementy mogą być bezpiecznie używane.</span><span class="sxs-lookup"><span data-stu-id="b390a-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="b390a-300">Odpowiednie procedury inicjowania można znaleźć w <xref:microsoft.quantum.arrays>temacie.</span><span class="sxs-lookup"><span data-stu-id="b390a-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="b390a-301">Wartości domyślne dla każdego typu są następujące:</span><span class="sxs-lookup"><span data-stu-id="b390a-301">The default values for each type are:</span></span>

<span data-ttu-id="b390a-302">Typ</span><span class="sxs-lookup"><span data-stu-id="b390a-302">Type</span></span> | <span data-ttu-id="b390a-303">Domyślny</span><span class="sxs-lookup"><span data-stu-id="b390a-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="b390a-304">_Nieprawidłowy qubit_</span><span class="sxs-lookup"><span data-stu-id="b390a-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="b390a-305">Pusty zakres,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="b390a-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="b390a-306">_nieprawidłowe wywoływanie_</span><span class="sxs-lookup"><span data-stu-id="b390a-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="b390a-307">Typy krotek są inicjowane element po elemencie.</span><span class="sxs-lookup"><span data-stu-id="b390a-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="b390a-308">Tablice nieregularne</span><span class="sxs-lookup"><span data-stu-id="b390a-308">Jagged Arrays</span></span>

<span data-ttu-id="b390a-309">Tablica nieregularna, czasami nazywana "tablicą tablicową", jest tablicą, której elementy są tablicami.</span><span class="sxs-lookup"><span data-stu-id="b390a-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="b390a-310">Elementy tablicy nieregularnej mogą mieć różne rozmiary.</span><span class="sxs-lookup"><span data-stu-id="b390a-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="b390a-311">Poniższy przykład pokazuje, jak zadeklarować i zainicjować tablicę nieregularną reprezentującą tabelę mnożenia.</span><span class="sxs-lookup"><span data-stu-id="b390a-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="b390a-312">Wycinki tablicy</span><span class="sxs-lookup"><span data-stu-id="b390a-312">Array Slices</span></span>

<span data-ttu-id="b390a-313">Jeśli wyrażenie tablicowe i `Range` wyrażenie, nowe wyrażenie może być utworzone przy użyciu operatora wycinka Array `[` i. `]`</span><span class="sxs-lookup"><span data-stu-id="b390a-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="b390a-314">Nowe wyrażenie będzie tego samego typu co tablica i będzie zawierać elementy tablicy indeksowane przez elementy `Range`w kolejności zdefiniowanej przez. `Range`</span><span class="sxs-lookup"><span data-stu-id="b390a-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="b390a-315">Na przykład, jeśli `a` jest powiązany z tablicą `Double`s, a następnie `a[3..-1..0]` jest `Double[]` wyrażeniem zawierającym cztery pierwsze elementy z `a` , ale w odwrotnej kolejności, jak pojawiają `a`się w.</span><span class="sxs-lookup"><span data-stu-id="b390a-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="b390a-316">Jeśli wartość `Range` jest pusta, powstający wycink tablicy będzie zerem o zerowej długości.</span><span class="sxs-lookup"><span data-stu-id="b390a-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="b390a-317">Jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, musi być ujęte w nawiasy klamrowe w celu wycięcia.</span><span class="sxs-lookup"><span data-stu-id="b390a-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="b390a-318">Na przykład, jeśli `a` i `b` są obie tablice `Int`s, wycinek z łączenia będzie wyrażony jako:</span><span class="sxs-lookup"><span data-stu-id="b390a-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="b390a-319">Wszystkie tablice w Q # są oparte na zero.</span><span class="sxs-lookup"><span data-stu-id="b390a-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="b390a-320">Oznacza to, że pierwszy element tablicy `a` jest zawsze. `a[0]`</span><span class="sxs-lookup"><span data-stu-id="b390a-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="b390a-321">Począwszy od naszego 0,8 wydania, obsługujemy kontekstowe wyrażenia dla dzielenia zakresów.</span><span class="sxs-lookup"><span data-stu-id="b390a-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="b390a-322">W szczególności wartości początkowe i końcowe zakresu mogą zostać pominięte w kontekście wyrażenia wycinka zakresu.</span><span class="sxs-lookup"><span data-stu-id="b390a-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="b390a-323">W takim przypadku kompilator zastosuje następujące reguły w celu wywnioskowania zamierzonych ograniczników dla zakresu.</span><span class="sxs-lookup"><span data-stu-id="b390a-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="b390a-324">Na przykład, jeśli wartość początkowa zakresu zostanie pominięta, wywnioskowana wartość początkowa</span><span class="sxs-lookup"><span data-stu-id="b390a-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="b390a-325">ma wartość zero, jeśli nie określono żadnego kroku lub określony krok jest dodatni i</span><span class="sxs-lookup"><span data-stu-id="b390a-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="b390a-326">jest długością tablicy z wycinkami minus jeden, jeśli określony krok jest ujemny.</span><span class="sxs-lookup"><span data-stu-id="b390a-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="b390a-327">W przypadku pominięcia wartości końcowej zakresu, wywnioskowana wartość końcowa</span><span class="sxs-lookup"><span data-stu-id="b390a-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="b390a-328">jest długością tablicy wycinka minus jeden, jeśli żaden krok nie jest określony lub określony krok jest dodatni i</span><span class="sxs-lookup"><span data-stu-id="b390a-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="b390a-329">ma wartość zero, jeśli określony krok jest ujemny.</span><span class="sxs-lookup"><span data-stu-id="b390a-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="b390a-330">Wyrażenia elementu tablicy</span><span class="sxs-lookup"><span data-stu-id="b390a-330">Array Element Expressions</span></span>

<span data-ttu-id="b390a-331">Jeśli wyrażenie tablicowe i `Int` wyrażenie, nowe wyrażenie może być utworzone przy użyciu operatora elementu `[` Array `]` i.</span><span class="sxs-lookup"><span data-stu-id="b390a-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="b390a-332">Nowe wyrażenie będzie tego samego typu co typ elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="b390a-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="b390a-333">Na przykład, jeśli `a` jest powiązany z tablicą `Double`s, a następnie `a[4]` jest `Double` wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="b390a-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="b390a-334">Jeśli wyrażenie tablicy nie jest prostym identyfikatorem, musi być ujęte w nawiasy klamrowe, aby można było wybrać element.</span><span class="sxs-lookup"><span data-stu-id="b390a-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="b390a-335">Na przykład, jeśli `a` i `b` są obie tablice `Int`s, element z łączenia zostałby wyrażony jako:</span><span class="sxs-lookup"><span data-stu-id="b390a-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="b390a-336">Wszystkie tablice w Q # są oparte na zero.</span><span class="sxs-lookup"><span data-stu-id="b390a-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="b390a-337">Oznacza to, że pierwszy element tablicy `a` jest zawsze. `a[0]`</span><span class="sxs-lookup"><span data-stu-id="b390a-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="b390a-338">Wyrażenia kopiowania i aktualizowania</span><span class="sxs-lookup"><span data-stu-id="b390a-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="b390a-339">Nowe tablice można tworzyć z istniejących za pośrednictwem wyrażeń kopiowania i aktualizowania.</span><span class="sxs-lookup"><span data-stu-id="b390a-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="b390a-340">Wyrażenie copy `expression1 w/ expression2 <- expression3`-and-Update jest wyrażeniem formularza, gdzie `expression1` musi być typu `T[]` dla pewnego typu. `T`</span><span class="sxs-lookup"><span data-stu-id="b390a-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="b390a-341">Sekunda `expression2` definiuje indeksy elementów do zmodyfikowania w porównaniu do tablicy w `expression1` i musi być typu `Int` lub typu. `Range`</span><span class="sxs-lookup"><span data-stu-id="b390a-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="b390a-342">Jeśli `expression2` jest typu `Int`, `expression3` musi być typu. `T`</span><span class="sxs-lookup"><span data-stu-id="b390a-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="b390a-343">Jeśli `expression2` jest typu `Range`, `expression3` musi być typu. `T[]`</span><span class="sxs-lookup"><span data-stu-id="b390a-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="b390a-344">Wyrażenie `arr w/ idx <- value` Copy-and-Update konstruuje nową tablicę ze wszystkimi elementami ustawionymi na odpowiadający element `arr`w, z wyjątkiem elementów `idx`, które są ustawione na jeden z nich w. `value`</span><span class="sxs-lookup"><span data-stu-id="b390a-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="b390a-345">Na przykład, jeśli `arr` zawiera tablicę `[0,1,2,3]`,</span><span class="sxs-lookup"><span data-stu-id="b390a-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="b390a-346">`arr w/ 0 <- 10`jest tablicą `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="b390a-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="b390a-347">`arr w/ 2 <- 10`jest tablicą `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="b390a-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="b390a-348">`arr w/ 0..2..3 <- [10,12]`jest tablicą `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="b390a-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="b390a-349">Podobne wyrażenia istnieją dla nazwanych elementów w typach zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b390a-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="b390a-350">Rozważmy przykład typu</span><span class="sxs-lookup"><span data-stu-id="b390a-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="b390a-351">Jeśli `c` `Complex(1.,-1.)`zawiera wartość typu `c w/ Re <- 0.` , jest wyrażeniem typu `Complex` , który jest obliczany. `Complex(0.,-1.)`</span><span class="sxs-lookup"><span data-stu-id="b390a-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="b390a-352">Wyrażenia warunkowe</span><span class="sxs-lookup"><span data-stu-id="b390a-352">Conditional Expressions</span></span>

<span data-ttu-id="b390a-353">Uwzględniając dwa inne wyrażenia tego samego typu i wyrażenie logiczne, wyrażenie warunkowe może być utworzone przy użyciu znaku `?` zapytania i pionowego paska. `|`</span><span class="sxs-lookup"><span data-stu-id="b390a-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="b390a-354">Na przykład `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="b390a-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="b390a-355">W tym przykładzie wartość wyrażenia warunkowego będzie `c` `a==b` równa true, a `d` jeśli jest fałszywa.</span><span class="sxs-lookup"><span data-stu-id="b390a-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="b390a-356">Dwa wyrażenia mogą oszacować do operacji, które mają te same dane wejściowe i wyjściowe, ale obsługują różne funktory.</span><span class="sxs-lookup"><span data-stu-id="b390a-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="b390a-357">W tym przypadku typ wyrażenia warunkowego jest operacją z tymi danymi wejściowymi i wyjściowymi, które obsługują wszystkie funktory obsługiwane przez oba wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b390a-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="b390a-358">Na przykład jeśli `Op1` `Op2`,, i `Op3` wszystkie są `Qubit[]=>Unit`, ale `Op1` obsługuje `Adjoint`, `Op2` obsługuje `Controlled`i `Op3` obsługuje obie:</span><span class="sxs-lookup"><span data-stu-id="b390a-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="b390a-359">`flag ? Op1 | Op2`jest `(Qubit[] => Unit)` operacją.</span><span class="sxs-lookup"><span data-stu-id="b390a-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="b390a-360">`flag ? Op1 | Op3`jest `(Qubit[] => Unit is Adj)` operacją.</span><span class="sxs-lookup"><span data-stu-id="b390a-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="b390a-361">`flag ? Op2 | Op3`jest `(Qubit[] => Unit is Ctl)` operacją.</span><span class="sxs-lookup"><span data-stu-id="b390a-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="b390a-362">Jeśli jedno z dwóch możliwych wyrażeń wynikowych zawiera wywołanie funkcji lub operacji, to wywołanie będzie odbywać się tylko wtedy, gdy ten wynik będzie wartością wywołania.</span><span class="sxs-lookup"><span data-stu-id="b390a-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="b390a-363">Na przykład `a==b ? C(qs) | D(qs)`w przypadku, gdy `a==b` ma wartość true, `C` operacja zostanie wywołana, a jeśli ma wartość false, tylko `D` zostanie wywołana.</span><span class="sxs-lookup"><span data-stu-id="b390a-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="b390a-364">Jest to podobne do krótkich obwodów w innych językach.</span><span class="sxs-lookup"><span data-stu-id="b390a-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="b390a-365">Kolejność wykonywania działań</span><span class="sxs-lookup"><span data-stu-id="b390a-365">Operator Precedence</span></span>

<span data-ttu-id="b390a-366">Wszystkie operatory binarne są z prawej strony skojarzenia, z wyjątkiem `^`.</span><span class="sxs-lookup"><span data-stu-id="b390a-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="b390a-367">Nawiasy `[` klamrowe i `]`, w przypadku dzielenia i indeksowania tablicy, należy powiązać przed dowolnym operatorem.</span><span class="sxs-lookup"><span data-stu-id="b390a-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="b390a-368">Funktory `Adjoint` i `Controlled` Powiąż po indeksowaniu tablicy, ale przed wszystkimi innymi operatorami.</span><span class="sxs-lookup"><span data-stu-id="b390a-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="b390a-369">Nawiasy dla wywołania operacji i funkcji są również powiązane przed dowolnym operatorem, ale po indeksowaniu tablicy i funktory.</span><span class="sxs-lookup"><span data-stu-id="b390a-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="b390a-370">Operatory według pierwszeństwa, od najwyższego do najniższego:</span><span class="sxs-lookup"><span data-stu-id="b390a-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="b390a-371">Operator</span><span class="sxs-lookup"><span data-stu-id="b390a-371">Operator</span></span> | <span data-ttu-id="b390a-372">Większa</span><span class="sxs-lookup"><span data-stu-id="b390a-372">Arity</span></span> | <span data-ttu-id="b390a-373">Opis</span><span class="sxs-lookup"><span data-stu-id="b390a-373">Description</span></span> | <span data-ttu-id="b390a-374">Typy operandów</span><span class="sxs-lookup"><span data-stu-id="b390a-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="b390a-375">końcowe`!`</span><span class="sxs-lookup"><span data-stu-id="b390a-375">trailing `!`</span></span> | <span data-ttu-id="b390a-376">Jednoargumentowy</span><span class="sxs-lookup"><span data-stu-id="b390a-376">Unary</span></span> | <span data-ttu-id="b390a-377">Unwrap</span><span class="sxs-lookup"><span data-stu-id="b390a-377">Unwrap</span></span> | <span data-ttu-id="b390a-378">Dowolny typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="b390a-378">Any user-defined type</span></span>
 <span data-ttu-id="b390a-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="b390a-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="b390a-380">Jednoargumentowy</span><span class="sxs-lookup"><span data-stu-id="b390a-380">Unary</span></span> | <span data-ttu-id="b390a-381">Cyfra ujemna, dopełnienie bitowe, Negacja logiczna</span><span class="sxs-lookup"><span data-stu-id="b390a-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="b390a-382">`Int`, `BigInt` lub `Double` dla `-`, `Int` `BigInt` dla `~~~` `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="b390a-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="b390a-383">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-383">Binary</span></span> | <span data-ttu-id="b390a-384">Moc całkowita</span><span class="sxs-lookup"><span data-stu-id="b390a-384">Integer power</span></span> | <span data-ttu-id="b390a-385">`Int`lub `BigInt` dla podstawy `Int` dla wykładnika</span><span class="sxs-lookup"><span data-stu-id="b390a-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="b390a-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="b390a-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="b390a-387">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-387">Binary</span></span> | <span data-ttu-id="b390a-388">Dzielenie, mnożenie, moduł całkowity</span><span class="sxs-lookup"><span data-stu-id="b390a-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="b390a-389">`Int`, `BigInt` lub `Double` dla `/` i `*`, `Int` lub `BigInt` dla`%`</span><span class="sxs-lookup"><span data-stu-id="b390a-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="b390a-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="b390a-390">`+`, `-`</span></span> | <span data-ttu-id="b390a-391">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-391">Binary</span></span> | <span data-ttu-id="b390a-392">Dodawanie lub łączenie ciągów i tablic, odejmowanie</span><span class="sxs-lookup"><span data-stu-id="b390a-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="b390a-393">`Int`, `BigInt` or `Double`, dodatkowo `String` lub dowolnego typu tablicy dla`+`</span><span class="sxs-lookup"><span data-stu-id="b390a-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="b390a-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="b390a-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="b390a-395">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-395">Binary</span></span> | <span data-ttu-id="b390a-396">Lewy Shift, prawy Shift</span><span class="sxs-lookup"><span data-stu-id="b390a-396">Left shift, right shift</span></span> | <span data-ttu-id="b390a-397">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b390a-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="b390a-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="b390a-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="b390a-399">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-399">Binary</span></span> | <span data-ttu-id="b390a-400">Mniejsze niż, mniejsze niż lub równe, większe niż, większe niż lub równe</span><span class="sxs-lookup"><span data-stu-id="b390a-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="b390a-401">`Int``BigInt` lub`Double`</span><span class="sxs-lookup"><span data-stu-id="b390a-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="b390a-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="b390a-402">`==`, `!=`</span></span> | <span data-ttu-id="b390a-403">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-403">Binary</span></span> | <span data-ttu-id="b390a-404">porównania równe, nierówne</span><span class="sxs-lookup"><span data-stu-id="b390a-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="b390a-405">dowolny typ pierwotny</span><span class="sxs-lookup"><span data-stu-id="b390a-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="b390a-406">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-406">Binary</span></span> | <span data-ttu-id="b390a-407">Bitowe ORAZ</span><span class="sxs-lookup"><span data-stu-id="b390a-407">Bitwise AND</span></span> | <span data-ttu-id="b390a-408">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b390a-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="b390a-409">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-409">Binary</span></span> | <span data-ttu-id="b390a-410">Bitowe XOR</span><span class="sxs-lookup"><span data-stu-id="b390a-410">Bitwise XOR</span></span> | <span data-ttu-id="b390a-411">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b390a-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="b390a-412">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-412">Binary</span></span> | <span data-ttu-id="b390a-413">Bitowe OR</span><span class="sxs-lookup"><span data-stu-id="b390a-413">Bitwise OR</span></span> | <span data-ttu-id="b390a-414">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b390a-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="b390a-415">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-415">Binary</span></span> | <span data-ttu-id="b390a-416">AND logiczne</span><span class="sxs-lookup"><span data-stu-id="b390a-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="b390a-417">plików binarnych</span><span class="sxs-lookup"><span data-stu-id="b390a-417">Binary</span></span> | <span data-ttu-id="b390a-418">OR logiczne</span><span class="sxs-lookup"><span data-stu-id="b390a-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="b390a-419">Plik binarny/Trzyelementowy</span><span class="sxs-lookup"><span data-stu-id="b390a-419">Binary/Ternary</span></span> | <span data-ttu-id="b390a-420">Operator zakresu</span><span class="sxs-lookup"><span data-stu-id="b390a-420">Range operator</span></span> | `Int`
 <span data-ttu-id="b390a-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="b390a-421">`?` `|`</span></span> | <span data-ttu-id="b390a-422">Trójargumentowy</span><span class="sxs-lookup"><span data-stu-id="b390a-422">Ternary</span></span> | <span data-ttu-id="b390a-423">Warunkowe</span><span class="sxs-lookup"><span data-stu-id="b390a-423">Conditional</span></span> | <span data-ttu-id="b390a-424">`Bool`po lewej stronie</span><span class="sxs-lookup"><span data-stu-id="b390a-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="b390a-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="b390a-425">`w/` `<-`</span></span> | <span data-ttu-id="b390a-426">Trójargumentowy</span><span class="sxs-lookup"><span data-stu-id="b390a-426">Ternary</span></span> | <span data-ttu-id="b390a-427">Kopiuj i Aktualizuj</span><span class="sxs-lookup"><span data-stu-id="b390a-427">Copy-and-update</span></span> | <span data-ttu-id="b390a-428">Zobacz [wyrażenia kopiowania i aktualizowania](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="b390a-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

---
title: 'Wyrażenia typu w Q #'
description: 'Dowiedz się, jak określać, odwoływać i łączyć stałe, zmienne, operatory, operacje i funkcje jako wyrażenia w Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: b32644382bb88fb11da00d0d7d78bbd797a0eaaa
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84629996"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="9f81e-103">Wyrażenia typu w Q #</span><span class="sxs-lookup"><span data-stu-id="9f81e-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="9f81e-104">Wyrażenia liczbowe</span><span class="sxs-lookup"><span data-stu-id="9f81e-104">Numeric Expressions</span></span>

<span data-ttu-id="9f81e-105">Wyrażenia liczbowe są wyrażeniami typu `Int` , `BigInt` , lub `Double` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="9f81e-106">Oznacza to, że są to liczby całkowite lub zmiennoprzecinkowe.</span><span class="sxs-lookup"><span data-stu-id="9f81e-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="9f81e-107">`Int`literały w Q # są zapisywane po prostu jako sekwencja cyfr.</span><span class="sxs-lookup"><span data-stu-id="9f81e-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="9f81e-108">Liczby całkowite szesnastkowe i binarne są obsługiwane odpowiednio przy użyciu `0x` `0b` prefiksu i.</span><span class="sxs-lookup"><span data-stu-id="9f81e-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="9f81e-109">`BigInt`literały w Q # są zapisywane z końcowym `l` lub `L` sufiksem.</span><span class="sxs-lookup"><span data-stu-id="9f81e-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="9f81e-110">Szesnastkowe duże liczby całkowite są obsługiwane z prefiksem "0x".</span><span class="sxs-lookup"><span data-stu-id="9f81e-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="9f81e-111">W ten sposób wszystkie prawidłowe zastosowania `BigInt` literałów są następujące:</span><span class="sxs-lookup"><span data-stu-id="9f81e-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="9f81e-112">`Double`literały w Q # są liczbami zmiennoprzecinkowymi zapisanymi przy użyciu cyfr dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="9f81e-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="9f81e-113">Mogą być zapisywane z przecinkiem dziesiętnym, `.` , i/lub części wykładniczej wskazanej za pomocą znaku "e" lub "e" (po których dozwolone są tylko możliwe znaki minus i cyfry dziesiętne).</span><span class="sxs-lookup"><span data-stu-id="9f81e-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="9f81e-114">Poniżej podano prawidłowe `Double` literały: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="9f81e-115">Jeśli wyrażenie tablicy dowolnego typu elementu, `Int` wyrażenie może być utworzone przy użyciu [`Length`](xref:microsoft.quantum.core.length) wbudowanej funkcji, z wyrażeniem tablicy ujętym w nawiasy `(` i `)` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="9f81e-116">Na przykład, jeśli `a` jest powiązany z tablicą, `Length(a)` jest wyrażeniem liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="9f81e-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="9f81e-117">Jeśli `b` jest tablicą tablic liczb całkowitych, `Int[][]` , a następnie `Length(b)` jest liczbą tablic w `b` , i `Length(b[1])` jest liczbą liczb całkowitych w drugiej tablicy podrzędnej w `b` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="9f81e-118">Uwzględniając dwa wyrażenia liczbowe tego samego typu, operatory binarne,, `+` `-` `*` i `/` mogą być używane do tworzenia nowego wyrażenia liczbowego.</span><span class="sxs-lookup"><span data-stu-id="9f81e-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="9f81e-119">Typ nowego wyrażenia będzie taki sam jak typy wyrażeń składowych.</span><span class="sxs-lookup"><span data-stu-id="9f81e-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="9f81e-120">W przypadku dwóch wyrażeń całkowitych operator binarny `^` (potęga) może służyć do tworzenia nowego wyrażenia liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="9f81e-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="9f81e-121">Podobnie, można `^` użyć z dwoma wyrażeniami podwójnymi, aby utworzyć nowe wyrażenie podwójne.</span><span class="sxs-lookup"><span data-stu-id="9f81e-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="9f81e-122">Na koniec, `^` może być używany z dużą liczbą całkowitą z lewej strony i liczbą całkowitą z prawej strony, aby utworzyć nowe wyrażenie Big Integer.</span><span class="sxs-lookup"><span data-stu-id="9f81e-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="9f81e-123">W takim przypadku drugi parametr musi pasować do 32 bitów; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="9f81e-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="9f81e-124">W przypadku dwóch wyrażeń całkowitych lub dużych liczb całkowitych można utworzyć nowe wyrażenie typu Integer lub Big Integer przy użyciu `%` operatorów (moduł), `&&&` (bitowe and), `|||` (bitowego or) lub `^^^` (bitowe XOR).</span><span class="sxs-lookup"><span data-stu-id="9f81e-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="9f81e-125">W przypadku wyrażenia typu Integer lub Big Integer po lewej stronie i wyrażenia liczb całkowitych po prawej stronie `<<<` Operatory (arytmetyczne przesunięcie w lewo) lub `>>>` (arytmetyczne przesunięcie w prawo) mogą być używane do tworzenia nowego wyrażenia z tym samym typem co lewe wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="9f81e-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="9f81e-126">Drugi parametr (wartość przesunięcia) dla operacji Shift musi być większy lub równy zero; zachowanie dla ujemnych kwot przesunięcia jest niezdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="9f81e-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="9f81e-127">Wartość przesunięcia dla operacji przesunięcia musi być również zgodna z 32 bitowymi; Jeśli nie, zostanie zgłoszony błąd czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="9f81e-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="9f81e-128">Jeśli liczba, która ma zostać przesunięta jest liczbą całkowitą, jest interpretowana wartość przesunięcia, `mod 64` czyli przesunięcie 1 i przesunięcie 65 ma ten sam efekt.</span><span class="sxs-lookup"><span data-stu-id="9f81e-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="9f81e-129">W przypadku wartości liczb całkowitych i dużych liczb całkowitych przesunięcia są arytmetyczne.</span><span class="sxs-lookup"><span data-stu-id="9f81e-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="9f81e-130">Przesunięcie wartości ujemnej w lewo lub w prawo spowoduje powstanie liczby ujemnej.</span><span class="sxs-lookup"><span data-stu-id="9f81e-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="9f81e-131">Oznacza to, że przesunięcie jeden krok w lewo lub w prawo jest dokładnie takie samo jak mnożenie lub dzielenie odpowiednio przez 2.</span><span class="sxs-lookup"><span data-stu-id="9f81e-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="9f81e-132">Dzielenie liczb całkowitych i moduł całkowity są zgodne z tym samym zachowaniem dla liczb ujemnych w języku C#.</span><span class="sxs-lookup"><span data-stu-id="9f81e-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="9f81e-133">Oznacza to, że `a % b` będzie zawsze mieć ten sam znak jako `a` i `b * (a / b) + a % b` zawsze będzie równa się `a` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="9f81e-134">Przykład:</span><span class="sxs-lookup"><span data-stu-id="9f81e-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="9f81e-135">5</span><span class="sxs-lookup"><span data-stu-id="9f81e-135">5</span></span> | <span data-ttu-id="9f81e-136">2</span><span class="sxs-lookup"><span data-stu-id="9f81e-136">2</span></span> | <span data-ttu-id="9f81e-137">2</span><span class="sxs-lookup"><span data-stu-id="9f81e-137">2</span></span> | <span data-ttu-id="9f81e-138">1</span><span class="sxs-lookup"><span data-stu-id="9f81e-138">1</span></span>
 <span data-ttu-id="9f81e-139">5</span><span class="sxs-lookup"><span data-stu-id="9f81e-139">5</span></span> | <span data-ttu-id="9f81e-140">-2</span><span class="sxs-lookup"><span data-stu-id="9f81e-140">-2</span></span> | <span data-ttu-id="9f81e-141">-2</span><span class="sxs-lookup"><span data-stu-id="9f81e-141">-2</span></span> | <span data-ttu-id="9f81e-142">1</span><span class="sxs-lookup"><span data-stu-id="9f81e-142">1</span></span>
 <span data-ttu-id="9f81e-143">-5</span><span class="sxs-lookup"><span data-stu-id="9f81e-143">-5</span></span> | <span data-ttu-id="9f81e-144">2</span><span class="sxs-lookup"><span data-stu-id="9f81e-144">2</span></span> | <span data-ttu-id="9f81e-145">-2</span><span class="sxs-lookup"><span data-stu-id="9f81e-145">-2</span></span> | <span data-ttu-id="9f81e-146">-1</span><span class="sxs-lookup"><span data-stu-id="9f81e-146">-1</span></span>
 <span data-ttu-id="9f81e-147">-5</span><span class="sxs-lookup"><span data-stu-id="9f81e-147">-5</span></span> | <span data-ttu-id="9f81e-148">-2</span><span class="sxs-lookup"><span data-stu-id="9f81e-148">-2</span></span> | <span data-ttu-id="9f81e-149">2</span><span class="sxs-lookup"><span data-stu-id="9f81e-149">2</span></span> | <span data-ttu-id="9f81e-150">-1</span><span class="sxs-lookup"><span data-stu-id="9f81e-150">-1</span></span>

<span data-ttu-id="9f81e-151">Dzielenie z dużymi liczbami całkowitymi i moduł działa w taki sam sposób.</span><span class="sxs-lookup"><span data-stu-id="9f81e-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="9f81e-152">Mając każde wyrażenie liczbowe, nowe wyrażenie może być utworzone za pomocą `-` operatora jednoargumentowego.</span><span class="sxs-lookup"><span data-stu-id="9f81e-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="9f81e-153">Nowe wyrażenie będzie tego samego typu co wyrażenie elementu.</span><span class="sxs-lookup"><span data-stu-id="9f81e-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="9f81e-154">W przypadku dowolnego wyrażenia typu Integer lub Big Integer nowe wyrażenie tego samego typu może być sformułowane przy użyciu `~~~` operatora jednoargumentowego (dopełnienie bitowe).</span><span class="sxs-lookup"><span data-stu-id="9f81e-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="9f81e-155">Wyrażenia logiczne</span><span class="sxs-lookup"><span data-stu-id="9f81e-155">Boolean Expressions</span></span>

<span data-ttu-id="9f81e-156">Dwie `Bool` wartości literału są `true` i `false` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="9f81e-157">Uwzględniając wszystkie dwa wyrażenia tego samego typu pierwotnego, `==` Operatory i `!=` mogą być używane do konstruowania `Bool` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="9f81e-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="9f81e-158">Wyrażenie będzie prawdziwe, jeśli dwa wyrażenia są równe, i wartość false, jeśli nie.</span><span class="sxs-lookup"><span data-stu-id="9f81e-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="9f81e-159">Wartości typów zdefiniowanych przez użytkownika mogą nie być porównywane. można porównać tylko ich nieopakowane wartości.</span><span class="sxs-lookup"><span data-stu-id="9f81e-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="9f81e-160">Na przykład przy użyciu operatora "unotoka" `!` (szczegółowo wyjaśniono w [typach w Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="9f81e-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="9f81e-161">Porównywanie równości dla `Qubit` wartości jest równość tożsamości; oznacza to, czy dwa wyrażenia identyfikują ten sam qubit.</span><span class="sxs-lookup"><span data-stu-id="9f81e-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="9f81e-162">Stan dwóch qubits nie jest porównywany, dostępny, mierzony ani modyfikowany przez to porównanie.</span><span class="sxs-lookup"><span data-stu-id="9f81e-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="9f81e-163">Porównywanie równości dla `Double` wartości może być mylące ze względu na efekt zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="9f81e-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="9f81e-164">Na przykład `49.0 * (1.0/49.0) != 1.0` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="9f81e-165">Uwzględniając wszystkie dwa wyrażenia liczbowe, operatory binarne `>` ,, `<` `>=` i `<=` mogą być używane do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli pierwsze wyrażenie jest odpowiednio większe niż, mniejsze niż, większe niż lub równe lub mniejsze lub równe drugiemu wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="9f81e-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="9f81e-166">W przypadku wszystkich dwóch wyrażeń logicznych `and` Operatory i `or` mogą być używane do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli oba wyrażenia (komp. or lub Both) mają wartość true.</span><span class="sxs-lookup"><span data-stu-id="9f81e-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="9f81e-167">Mając każde wyrażenie logiczne, `not` operator jednoargumentowy może służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli wyrażenie elementu składowego ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="9f81e-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="9f81e-168">Wyrażenia ciągów</span><span class="sxs-lookup"><span data-stu-id="9f81e-168">String Expressions</span></span>

<span data-ttu-id="9f81e-169">Funkcja Q # umożliwia używanie ciągów w `fail` instrukcji (wyjaśniono w [przepływie sterowania](xref:microsoft.quantum.guide.controlflow#fail-statement)) i w [`Message`](xref:microsoft.quantum.intrinsic.message) funkcji standardowej.</span><span class="sxs-lookup"><span data-stu-id="9f81e-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="9f81e-170">Określone zachowanie tego elementu jest zależne od używanego symulatora, ale zazwyczaj zapisuje komunikat do konsoli hosta po wywołaniu w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="9f81e-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="9f81e-171">Ciągi w Q # są literałami lub interpolowanymi ciągami.</span><span class="sxs-lookup"><span data-stu-id="9f81e-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="9f81e-172">Literały ciągu są podobne do prostych literałów ciągu w większości języków: sekwencji znaków Unicode ujętych w podwójne cudzysłowy `"` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="9f81e-173">Wewnątrz ciągu znak ukośnika odwrotnego `\` może być używany do ucieczki podwójnego znaku cudzysłowu i do wstawiania nowej linii jako `\n` , powrotu karetki jako `\r` i karty jako `\t` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="9f81e-174">Przykład:</span><span class="sxs-lookup"><span data-stu-id="9f81e-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="9f81e-175">Ciągi interpolowane</span><span class="sxs-lookup"><span data-stu-id="9f81e-175">Interpolated strings</span></span>

<span data-ttu-id="9f81e-176">Składnia Q # dla interpolacji ciągów jest podzbiorem składni języka C#, ale w tym miejscu podsumowano najważniejsze punkty, które odnoszą się do Q #.</span><span class="sxs-lookup"><span data-stu-id="9f81e-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="9f81e-177">Główne rozróżnienia zostały omówione poniżej.</span><span class="sxs-lookup"><span data-stu-id="9f81e-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="9f81e-178">Aby zidentyfikować literał ciągu jako ciąg interpolowany, poprzedź go `$` symbolem.</span><span class="sxs-lookup"><span data-stu-id="9f81e-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="9f81e-179">Między `$` i `"` , które zaczyna się literałem ciągu znaków, nie może zawierać żadnego odstępu.</span><span class="sxs-lookup"><span data-stu-id="9f81e-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="9f81e-180">Poniżej znajduje się podstawowy przykład, za pomocą którego [`Message`](xref:microsoft.quantum.intrinsic.message) można napisać wynik pomiaru do konsoli wraz z innymi wyrażeniami Q #.</span><span class="sxs-lookup"><span data-stu-id="9f81e-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="9f81e-181">Dowolne prawidłowe wyrażenie Q # może pojawić się w ciągu interpolowanym.</span><span class="sxs-lookup"><span data-stu-id="9f81e-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="9f81e-182">Więcej szczegółowych informacji na temat składni języka C# można znaleźć w [*ciągach interpolowanych*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="9f81e-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="9f81e-183">Najbardziej istotną różnicą jest to, że Q # nie obsługuje ciągów interpolowanych Verbatim (wiele wierszy).</span><span class="sxs-lookup"><span data-stu-id="9f81e-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="9f81e-184">Wyrażenia wewnątrz ciągu interpolowanego są zgodne z składnią Q #, a nie składnią języka C#.</span><span class="sxs-lookup"><span data-stu-id="9f81e-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="9f81e-185">Wyrażenia zakresu</span><span class="sxs-lookup"><span data-stu-id="9f81e-185">Range Expressions</span></span>

<span data-ttu-id="9f81e-186">Każde trzy `Int` wyrażenie `start` , `step` , i `stop` , `start .. step .. stop` jest wyrażeniem zakresu, którego pierwszy element jest `start` , drugi element jest `start+step` , trzeci element jest `start+step+step` itp., do do `stop` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="9f81e-187">Zakres może być pusty, jeśli na przykład `step` jest wartością dodatnią i `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="9f81e-188">Ostatnim elementem zakresu będzie `stop` , jeśli różnica między `start` i `stop` jest całkowitą wielokrotnością `step` ; oznacza to, że zakres jest włącznie na obu końcach.</span><span class="sxs-lookup"><span data-stu-id="9f81e-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="9f81e-189">Uwzględniając wszystkie dwa `Int` wyrażenia `start` i `stop` , `start .. stop` jest wyrażenie zakresu, które jest równe `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="9f81e-190">Należy zauważyć, że implikowana `step` wartość to + 1 `stop` , nawet jeśli jest mniejsza niż `start` ; w takim przypadku zakres jest pusty.</span><span class="sxs-lookup"><span data-stu-id="9f81e-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="9f81e-191">Oto kilka przykładowych zakresów:</span><span class="sxs-lookup"><span data-stu-id="9f81e-191">Some example ranges are:</span></span>

- <span data-ttu-id="9f81e-192">`1..3`jest zakresem 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="9f81e-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="9f81e-193">`2..2..5`jest zakresem od 2 do 4.</span><span class="sxs-lookup"><span data-stu-id="9f81e-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="9f81e-194">`2..2..6`jest zakresem 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="9f81e-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="9f81e-195">`6..-2..2`jest zakresem 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="9f81e-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="9f81e-196">`2..1`jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="9f81e-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="9f81e-197">`2..6..7`jest zakresem 2.</span><span class="sxs-lookup"><span data-stu-id="9f81e-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="9f81e-198">`2..2..1`jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="9f81e-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="9f81e-199">`1..-1..2`jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="9f81e-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="9f81e-200">Wyrażenia qubit</span><span class="sxs-lookup"><span data-stu-id="9f81e-200">Qubit Expressions</span></span>

<span data-ttu-id="9f81e-201">Jedyne `Qubit` wyrażenia to symbole, które są powiązane z `Qubit` wartościami lub tablicami elementów tablic `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="9f81e-202">Brak `Qubit` literałów.</span><span class="sxs-lookup"><span data-stu-id="9f81e-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="9f81e-203">Wyrażenia Pauli</span><span class="sxs-lookup"><span data-stu-id="9f81e-203">Pauli Expressions</span></span>

<span data-ttu-id="9f81e-204">Cztery `Pauli` wartości, `PauliI` ,, `PauliX` `PauliY` i `PauliZ` , są prawidłowymi `Pauli` wyrażeniami.</span><span class="sxs-lookup"><span data-stu-id="9f81e-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="9f81e-205">Inaczej niż to, jedyne `Pauli` wyrażenia to symbole, które są powiązane z `Pauli` wartościami lub tablicami elementów tablic `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="9f81e-206">Wyrażenia wynikowe</span><span class="sxs-lookup"><span data-stu-id="9f81e-206">Result Expressions</span></span>

<span data-ttu-id="9f81e-207">Dwie `Result` wartości `One` i `Zero` są prawidłowymi `Result` wyrażeniami.</span><span class="sxs-lookup"><span data-stu-id="9f81e-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="9f81e-208">Inaczej niż to, jedyne `Result` wyrażenia to symbole, które są powiązane z `Result` wartościami lub tablicami elementów tablic `Result` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="9f81e-209">W szczególności należy zauważyć, że `One` nie jest taka sama jak liczba całkowita `1` i nie ma żadnej bezpośredniej konwersji między nimi.</span><span class="sxs-lookup"><span data-stu-id="9f81e-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="9f81e-210">Ta sama wartość dotyczy `Zero` i `0` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="9f81e-211">Wyrażenia krotki</span><span class="sxs-lookup"><span data-stu-id="9f81e-211">Tuple Expressions</span></span>

<span data-ttu-id="9f81e-212">Literał krotki to sekwencja wyrażeń elementu odpowiedniego typu, rozdzielona przecinkami, ujęta w `(` i `)` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="9f81e-213">Na przykład `(1, One)` jest `(Int, Result)` wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="9f81e-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="9f81e-214">W przypadku innych niż literały jedynymi wyrażeniami krotek są symbole, które są powiązane z wartościami krotki, elementami tablicy tablic krotek i wywoływanie wywołań, które zwracają krotki.</span><span class="sxs-lookup"><span data-stu-id="9f81e-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="9f81e-215">Wyrażenia typu zdefiniowanego przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="9f81e-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="9f81e-216">Literał typu zdefiniowanego przez użytkownika składa się z nazwy typu, a następnie literału krotki typu krotki podstawowej typu.</span><span class="sxs-lookup"><span data-stu-id="9f81e-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="9f81e-217">Na przykład, jeśli `IntPair` jest typem zdefiniowanym przez użytkownika na podstawie `(Int, Int)` , `IntPair(2, 3)` byłby on prawidłowym literałem tego typu.</span><span class="sxs-lookup"><span data-stu-id="9f81e-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="9f81e-218">Oprócz literałów jedynymi wyrażeniami typu zdefiniowanego przez użytkownika są symbole, które są powiązane z wartościami tego typu, elementy tablicy tablic tego typu i wywoływanie wywołań, które zwracają ten typ.</span><span class="sxs-lookup"><span data-stu-id="9f81e-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="9f81e-219">Odpakowywanie wyrażeń</span><span class="sxs-lookup"><span data-stu-id="9f81e-219">Unwrap Expressions</span></span>

<span data-ttu-id="9f81e-220">W Q # operator rozwinięcia jest końcowym wykrzyknikiem `!` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="9f81e-221">Na przykład, jeśli `IntPair` jest typem zdefiniowanym przez użytkownika z typem źródłowym `(Int, Int)` i `s` była zmienną z wartością `IntPair(2, 3)` , wówczas `s!` zostałby `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="9f81e-222">Dla typów zdefiniowanych przez użytkownika, zdefiniowanych w warunkach innych typów zdefiniowanych przez użytkownika, można powtórzyć operator rozwinięcia. na przykład `s!!` wskazuje podwójnie nieopakowaną wartość `s` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-222">For user-defined types defined in terms of other user-defined types, the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="9f81e-223">W takim przypadku, jeśli `WrappedPair` jest typem zdefiniowanym przez użytkownika z typem źródłowym `IntPair` i `t` jest zmienną z wartością `WrappedPair(IntPair(1,2))` , wówczas `t!!` zostałby `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-223">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="9f81e-224">`!`Operator ma wyższy priorytet niż wszystkie inne operatory inne niż `[]` dla indeksowania tablicy i dzielenia.</span><span class="sxs-lookup"><span data-stu-id="9f81e-224">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="9f81e-225">`!`i `[]` powiąże się z pozycją, czyli `a[i]![3]` należy ją przeczytać jako `((a[i])!)[3]` : Take `i` "ty" elementu `a` , Odpakuj go, a następnie Pobierz trzeci element nieopakowanej wartości (która musi być tablicą).</span><span class="sxs-lookup"><span data-stu-id="9f81e-225">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="9f81e-226">Pierwszeństwo `!` operatora ma jeden wpływ, który może nie być oczywisty.</span><span class="sxs-lookup"><span data-stu-id="9f81e-226">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="9f81e-227">Jeśli funkcja lub operacja zwraca wartość, która staje się nieopakowana, wywołanie funkcji lub operacji musi być ujęte w nawiasy, tak aby krotka argumentu była powiązana z wywołaniem, a nie z odwinięciem.</span><span class="sxs-lookup"><span data-stu-id="9f81e-227">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="9f81e-228">Przykład:</span><span class="sxs-lookup"><span data-stu-id="9f81e-228">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="9f81e-229">Wyrażenia tablic</span><span class="sxs-lookup"><span data-stu-id="9f81e-229">Array Expressions</span></span>

<span data-ttu-id="9f81e-230">Literał tablicowy jest sekwencją co najmniej jednego wyrażenia elementu, rozdzielonych przecinkami, ujęty w `[` i `]` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-230">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="9f81e-231">Wszystkie elementy muszą być zgodne z tym samym typem.</span><span class="sxs-lookup"><span data-stu-id="9f81e-231">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="9f81e-232">Mając daną dwie tablice tego samego typu, operator binarny `+` może służyć do tworzenia nowej tablicy, która jest połączeniem dwóch tablic.</span><span class="sxs-lookup"><span data-stu-id="9f81e-232">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="9f81e-233">Na przykład `[1,2,3] + [4,5,6]` ma `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-233">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="9f81e-234">Tworzenie tablicy</span><span class="sxs-lookup"><span data-stu-id="9f81e-234">Array Creation</span></span>

<span data-ttu-id="9f81e-235">Uwzględniając typ i `Int` wyrażenie, `new` operator może służyć do przydzielenia nowej tablicy o danym rozmiarze.</span><span class="sxs-lookup"><span data-stu-id="9f81e-235">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="9f81e-236">Na przykład `new Int[i + 1]` przydzieli nową `Int` tablicę z `i + 1` elementami.</span><span class="sxs-lookup"><span data-stu-id="9f81e-236">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="9f81e-237">Puste literały tablicowe, `[]` , są niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="9f81e-237">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="9f81e-238">Zamiast używać `new ★[0]` , gdzie `★` jest jako symbol zastępczy dla odpowiedniego typu, umożliwia utworzenie odpowiedniej tablicy o długości zero.</span><span class="sxs-lookup"><span data-stu-id="9f81e-238">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="9f81e-239">Elementy nowej tablicy są inicjowane z wartością domyślną zależną od typu.</span><span class="sxs-lookup"><span data-stu-id="9f81e-239">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="9f81e-240">W większości przypadków jest to pewna odmiana zero.</span><span class="sxs-lookup"><span data-stu-id="9f81e-240">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="9f81e-241">W przypadku qubits i elementów, które są odwołaniami do jednostek, nie ma żadnej rozsądnej wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="9f81e-241">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="9f81e-242">W tym przypadku dla tych typów wartość domyślna to nieprawidłowe odwołanie, którego nie można użyć bez powodowania błędu czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="9f81e-242">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="9f81e-243">Jest to podobne do odwołania o wartości null w językach, takich jak C# lub Java.</span><span class="sxs-lookup"><span data-stu-id="9f81e-243">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="9f81e-244">Tablice zawierające qubits lub elementy wywoływane muszą zostać prawidłowo zainicjowane przy użyciu wartości innych niż domyślne, zanim ich elementy mogą być bezpiecznie używane.</span><span class="sxs-lookup"><span data-stu-id="9f81e-244">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="9f81e-245">Odpowiednie procedury inicjowania można znaleźć w temacie <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="9f81e-245">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="9f81e-246">Wartości domyślne dla każdego typu są następujące:</span><span class="sxs-lookup"><span data-stu-id="9f81e-246">The default values for each type are:</span></span>

<span data-ttu-id="9f81e-247">Typ</span><span class="sxs-lookup"><span data-stu-id="9f81e-247">Type</span></span> | <span data-ttu-id="9f81e-248">Domyślne</span><span class="sxs-lookup"><span data-stu-id="9f81e-248">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="9f81e-249">_Nieprawidłowy qubit_</span><span class="sxs-lookup"><span data-stu-id="9f81e-249">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="9f81e-250">Pusty zakres,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="9f81e-250">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="9f81e-251">_nieprawidłowe wywoływanie_</span><span class="sxs-lookup"><span data-stu-id="9f81e-251">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="9f81e-252">Typy krotek są inicjowane element po elemencie.</span><span class="sxs-lookup"><span data-stu-id="9f81e-252">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="9f81e-253">Elementy tablicy</span><span class="sxs-lookup"><span data-stu-id="9f81e-253">Array Elements</span></span>

<span data-ttu-id="9f81e-254">Jeśli wyrażenie tablicowe i `Int` wyrażenie, nowe wyrażenie może być utworzone przy użyciu `[` `]` operatora elementu Array i.</span><span class="sxs-lookup"><span data-stu-id="9f81e-254">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="9f81e-255">Nowe wyrażenie będzie tego samego typu co typ elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="9f81e-255">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="9f81e-256">Na przykład, jeśli `a` jest powiązany z tablicą `Double` s, a następnie `a[4]` jest `Double` wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="9f81e-256">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="9f81e-257">Jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, musi być ujęte w nawiasy, aby można było wybrać element.</span><span class="sxs-lookup"><span data-stu-id="9f81e-257">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="9f81e-258">Na przykład, jeśli `a` i `b` są obie tablice `Int` s, element z łączenia zostałby wyrażony jako:</span><span class="sxs-lookup"><span data-stu-id="9f81e-258">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="9f81e-259">Wszystkie tablice w Q # są oparte na zero.</span><span class="sxs-lookup"><span data-stu-id="9f81e-259">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="9f81e-260">Oznacza to, że pierwszy element tablicy `a` jest zawsze `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-260">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="9f81e-261">Wycinki tablicy</span><span class="sxs-lookup"><span data-stu-id="9f81e-261">Array Slices</span></span>

<span data-ttu-id="9f81e-262">Jeśli wyrażenie tablicowe i `Range` wyrażenie, nowe wyrażenie może być utworzone przy użyciu `[` `]` operatora wycinka Array i.</span><span class="sxs-lookup"><span data-stu-id="9f81e-262">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="9f81e-263">Nowe wyrażenie będzie tego samego typu co tablica i będzie zawierać elementy tablicy indeksowane przez elementy `Range` w kolejności zdefiniowanej przez `Range` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-263">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="9f81e-264">Na przykład, jeśli `a` jest powiązany z tablicą `Double` s, a następnie `a[3..-1..0]` jest `Double[]` wyrażeniem zawierającym cztery pierwsze elementy z, `a` ale w odwrotnej kolejności, jak pojawiają się w `a` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-264">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="9f81e-265">Jeśli wartość `Range` jest pusta, powstający wycink tablicy będzie zerem o zerowej długości.</span><span class="sxs-lookup"><span data-stu-id="9f81e-265">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="9f81e-266">Podobnie jak w przypadku elementów tablicy odwołujących się, jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, musi być ujęte w nawiasy klamrowe w celu wycięcia.</span><span class="sxs-lookup"><span data-stu-id="9f81e-266">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="9f81e-267">Jeśli `a` i `b` są obydwa tablice `Int` s, wycinek z łączenia będzie wyrażony jako:</span><span class="sxs-lookup"><span data-stu-id="9f81e-267">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="9f81e-268">Wywnioskowane wartości początkowe/końcowe</span><span class="sxs-lookup"><span data-stu-id="9f81e-268">Inferred start/end values</span></span>

<span data-ttu-id="9f81e-269">Począwszy od naszego 0,8 wydania, obsługujemy kontekstowe wyrażenia dla dzielenia zakresów.</span><span class="sxs-lookup"><span data-stu-id="9f81e-269">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="9f81e-270">W szczególności wartości początkowe i końcowe zakresu mogą zostać pominięte w kontekście wyrażenia wycinka zakresu.</span><span class="sxs-lookup"><span data-stu-id="9f81e-270">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="9f81e-271">W takim przypadku kompilator zastosuje następujące reguły w celu wywnioskowania zamierzonych ograniczników dla zakresu.</span><span class="sxs-lookup"><span data-stu-id="9f81e-271">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="9f81e-272">Na przykład, jeśli wartość początkowa zakresu zostanie pominięta, wywnioskowana wartość początkowa</span><span class="sxs-lookup"><span data-stu-id="9f81e-272">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="9f81e-273">ma wartość zero, jeśli nie określono żadnego kroku lub określony krok jest dodatni i</span><span class="sxs-lookup"><span data-stu-id="9f81e-273">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="9f81e-274">jest długością tablicy z wycinkami minus jeden, jeśli określony krok jest ujemny.</span><span class="sxs-lookup"><span data-stu-id="9f81e-274">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="9f81e-275">W przypadku pominięcia wartości końcowej zakresu, wywnioskowana wartość końcowa</span><span class="sxs-lookup"><span data-stu-id="9f81e-275">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="9f81e-276">jest długością tablicy wycinka minus jeden, jeśli żaden krok nie jest określony lub określony krok jest dodatni i</span><span class="sxs-lookup"><span data-stu-id="9f81e-276">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="9f81e-277">ma wartość zero, jeśli określony krok jest ujemny.</span><span class="sxs-lookup"><span data-stu-id="9f81e-277">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="9f81e-278">Wyrażenia kopiowania i aktualizowania</span><span class="sxs-lookup"><span data-stu-id="9f81e-278">Copy-and-Update Expressions</span></span>

<span data-ttu-id="9f81e-279">Ponieważ wszystkie typy Q # są typami wartości — w przypadku qubits z bardzo specjalną rolą — "kopia" jest tworzona, gdy wartość jest powiązana z symbolem lub gdy jest on powiązany.</span><span class="sxs-lookup"><span data-stu-id="9f81e-279">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="9f81e-280">Oznacza to, że zachowanie Q # jest takie samo, jak w przypadku tworzenia kopii podczas przypisywania.</span><span class="sxs-lookup"><span data-stu-id="9f81e-280">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="9f81e-281">Oczywiście w praktyce tylko odpowiednie fragmenty są w rzeczywistości odtworzone w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="9f81e-281">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="9f81e-282">Dotyczy to również tablic.</span><span class="sxs-lookup"><span data-stu-id="9f81e-282">This in particular also includes arrays.</span></span>
<span data-ttu-id="9f81e-283">W szczególności nie jest możliwe aktualizowanie elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="9f81e-283">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="9f81e-284">Aby zmodyfikować istniejącą tablicę, należy wykorzystać mechanizm *kopiowania i aktualizowania* .</span><span class="sxs-lookup"><span data-stu-id="9f81e-284">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="9f81e-285">Nowe tablice można tworzyć z istniejących za pośrednictwem wyrażeń *kopiowania i aktualizowania* .</span><span class="sxs-lookup"><span data-stu-id="9f81e-285">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="9f81e-286">Wyrażenie Copy-and-Update jest wyrażeniem formularza `expression1 w/ expression2 <- expression3` , gdzie `expression1` musi być typu `T[]` dla pewnego typu `T` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-286">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="9f81e-287">Sekunda `expression2` definiuje indeksy elementów do zmodyfikowania w porównaniu do tablicy w `expression1` i musi być typu `Int` lub typu `Range` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-287">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="9f81e-288">Jeśli `expression2` jest typu `Int` , `expression3` musi być typu `T` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-288">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="9f81e-289">Jeśli `expression2` jest typu `Range` , `expression3` musi być typu `T[]` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-289">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="9f81e-290">Wyrażenie Copy-and-Update `arr w/ idx <- value` konstruuje nową tablicę ze wszystkimi elementami ustawionymi na odpowiadający element w `arr` , z wyjątkiem elementów `idx` , które są ustawione na jeden z nich w `value` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-290">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="9f81e-291">Na przykład, jeśli `arr` zawiera tablicę `[0,1,2,3]` ,</span><span class="sxs-lookup"><span data-stu-id="9f81e-291">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="9f81e-292">`arr w/ 0 <- 10`jest tablicą `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-292">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="9f81e-293">`arr w/ 2 <- 10`jest tablicą `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-293">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="9f81e-294">`arr w/ 0..2..3 <- [10,12]`jest tablicą `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-294">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="9f81e-295">Wyrażenia Copy-and-Update dla nazwanych elementów</span><span class="sxs-lookup"><span data-stu-id="9f81e-295">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="9f81e-296">Podobne wyrażenia istnieją dla nazwanych elementów w typach zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9f81e-296">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="9f81e-297">Rozważmy przykład typu</span><span class="sxs-lookup"><span data-stu-id="9f81e-297">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="9f81e-298">Jeśli `c` zawiera wartość typu `Complex(1., -1.)` , `c w/ Re <- 0.` jest wyrażeniem typu, `Complex` który jest obliczany `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-298">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="9f81e-299">Tablice nieregularne</span><span class="sxs-lookup"><span data-stu-id="9f81e-299">Jagged Arrays</span></span>

<span data-ttu-id="9f81e-300">Tablica nieregularna, czasami nazywana "tablicą tablic," jest tablicą, której elementy są tablicami.</span><span class="sxs-lookup"><span data-stu-id="9f81e-300">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="9f81e-301">Elementy tablicy nieregularnej mogą mieć różne rozmiary.</span><span class="sxs-lookup"><span data-stu-id="9f81e-301">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="9f81e-302">Poniższy przykład pokazuje, jak zadeklarować i zainicjować tablicę nieregularną reprezentującą tabelę mnożenia.</span><span class="sxs-lookup"><span data-stu-id="9f81e-302">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="9f81e-303">Tablice wywoływanych</span><span class="sxs-lookup"><span data-stu-id="9f81e-303">Arrays of callables</span></span> 

<span data-ttu-id="9f81e-304">Należy zauważyć, że więcej informacji na temat żądanych typów można znaleźć poniżej, a także na następnej stronie, [operacji i funkcji w Q #](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="9f81e-304">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="9f81e-305">Jeśli wspólny typ elementu jest operacją lub typem funkcji, wszystkie elementy muszą mieć te same typy danych wejściowych i wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="9f81e-305">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="9f81e-306">Typ elementu tablicy będzie obsługiwał wszystkie funktory, które są obsługiwane przez wszystkie elementy.</span><span class="sxs-lookup"><span data-stu-id="9f81e-306">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="9f81e-307">Na przykład jeśli `Op1` , `Op2` , i `Op3` wszystkie są `Qubit[] => Unit` , ale obsługuje, `Op1` `Adjoint` `Op2` obsługuje `Controlled` i `Op3` obsługuje obie:</span><span class="sxs-lookup"><span data-stu-id="9f81e-307">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="9f81e-308">`[Op1, Op2]`jest tablicą `(Qubit[] => Unit)` operacji.</span><span class="sxs-lookup"><span data-stu-id="9f81e-308">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="9f81e-309">`[Op1, Op3]`jest tablicą `(Qubit[] => Unit is Adj)` operacji.</span><span class="sxs-lookup"><span data-stu-id="9f81e-309">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="9f81e-310">`[Op2, Op3]`jest tablicą `(Qubit[] => Unit is Ctl)` operacji.</span><span class="sxs-lookup"><span data-stu-id="9f81e-310">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="9f81e-311">Jednak chociaż `(Qubit[] => Unit is Adj)` `(Qubit[] => Unit is Ctl)` operacje mają wspólny typ podstawowy `(Qubit[] => Unit)` , należy pamiętać, że tablice tych operatorów *of* nie mają wspólnego typu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="9f81e-311">However, while `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` operations have the common base type of `(Qubit[] => Unit)`, note that arrays *of* these operators do not share a common base type.</span></span> <span data-ttu-id="9f81e-312">Na przykład `[[Op1], [Op2]]` obecnie zgłaszany jest błąd, ponieważ próbuje on utworzyć tablicę niezgodnych typów tablicy `(Qubit[] => Unit is Adj)[]` i `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-312">For example, `[[Op1], [Op2]]` would currently raise an error because it is attempting to create an array of the incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="9f81e-313">Wyrażenia warunkowe</span><span class="sxs-lookup"><span data-stu-id="9f81e-313">Conditional Expressions</span></span>

<span data-ttu-id="9f81e-314">Uwzględniając dwa inne wyrażenia tego samego typu i wyrażenie logiczne, wyrażenie warunkowe może być utworzone przy użyciu znaku zapytania `?` i pionowego paska `|` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-314">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="9f81e-315">Na przykład `a==b ? c | d` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-315">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="9f81e-316">W tym przykładzie wartość wyrażenia warunkowego będzie równa true, `c` `a==b` a `d` Jeśli jest fałszywa.</span><span class="sxs-lookup"><span data-stu-id="9f81e-316">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="9f81e-317">Wyrażenia warunkowe z możliwymi do odwoływać</span><span class="sxs-lookup"><span data-stu-id="9f81e-317">Conditional expressions with callables</span></span>

<span data-ttu-id="9f81e-318">Dwa wyrażenia mogą oszacować do operacji, które mają te same dane wejściowe i wyjściowe, ale obsługują różne funktory.</span><span class="sxs-lookup"><span data-stu-id="9f81e-318">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="9f81e-319">W tym przypadku typ wyrażenia warunkowego jest operacją z tymi danymi wejściowymi i wyjściowymi, które obsługują wszystkie funktory obsługiwane przez oba wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="9f81e-319">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="9f81e-320">Na przykład jeśli `Op1` , `Op2` , i `Op3` wszystkie są `Qubit[]=>Unit` , ale obsługuje, `Op1` `Adjoint` `Op2` obsługuje `Controlled` i `Op3` obsługuje obie:</span><span class="sxs-lookup"><span data-stu-id="9f81e-320">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="9f81e-321">`flag ? Op1 | Op2`jest `(Qubit[] => Unit)` operacją.</span><span class="sxs-lookup"><span data-stu-id="9f81e-321">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="9f81e-322">`flag ? Op1 | Op3`jest `(Qubit[] => Unit is Adj)` operacją.</span><span class="sxs-lookup"><span data-stu-id="9f81e-322">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="9f81e-323">`flag ? Op2 | Op3`jest `(Qubit[] => Unit is Ctl)` operacją.</span><span class="sxs-lookup"><span data-stu-id="9f81e-323">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="9f81e-324">Jeśli jedno z dwóch możliwych wyrażeń wynikowych zawiera wywołanie funkcji lub operacji, to wywołanie będzie odbywać się tylko wtedy, gdy ten wynik będzie wartością wywołania.</span><span class="sxs-lookup"><span data-stu-id="9f81e-324">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="9f81e-325">Na przykład w przypadku `a==b ? C(qs) | D(qs)` , gdy `a==b` ma wartość true, `C` operacja zostanie wywołana, a jeśli ma wartość false, tylko `D` zostanie wywołana.</span><span class="sxs-lookup"><span data-stu-id="9f81e-325">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="9f81e-326">Jest to podobne do krótkich obwodów w innych językach.</span><span class="sxs-lookup"><span data-stu-id="9f81e-326">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="9f81e-327">Możliwe do przewyrażenia</span><span class="sxs-lookup"><span data-stu-id="9f81e-327">Callable Expressions</span></span>

<span data-ttu-id="9f81e-328">Możliwy do przeprowadzenia literał jest nazwą operacji lub funkcji zdefiniowanej w zakresie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="9f81e-328">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="9f81e-329">Na przykład, `X` to literał operacji odwołujący się do standardowej `X` operacji biblioteki i `Message` jest literalną funkcją, która odwołuje się do standardowej `Message` funkcji biblioteki.</span><span class="sxs-lookup"><span data-stu-id="9f81e-329">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="9f81e-330">Jeśli operacja obsługuje `Adjoint` Funktor, `Adjoint op` to wyrażenie operacji.</span><span class="sxs-lookup"><span data-stu-id="9f81e-330">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="9f81e-331">Podobnie, jeśli operacja obsługuje `Controlled` Funktor, a następnie `Controlled op` jest wyrażeniem operacji.</span><span class="sxs-lookup"><span data-stu-id="9f81e-331">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="9f81e-332">Typy tych wyrażeń są określane podczas [wywoływania specjalizacji operacji](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="9f81e-332">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="9f81e-333">Funktory ( `Adjoint` i `Controlled` ) wiąże się bardziej ściśle niż wszystkie inne operatory, z wyjątkiem operatora rozwinięcia `!` i indeksowania tablicy z [] ".</span><span class="sxs-lookup"><span data-stu-id="9f81e-333">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="9f81e-334">W ten sposób obowiązują wszystkie kwestie prawne, przy założeniu, że operacje obsługują użycie funktory:</span><span class="sxs-lookup"><span data-stu-id="9f81e-334">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="9f81e-335">Wyrażenia, które możliwe do napisania</span><span class="sxs-lookup"><span data-stu-id="9f81e-335">Type-parameterized callable expressions</span></span>

<span data-ttu-id="9f81e-336">Możliwy do oddzielenia literału można użyć jako wartości, powiedzmy, aby przypisać do zmiennej lub przekazać do innego elementu.</span><span class="sxs-lookup"><span data-stu-id="9f81e-336">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="9f81e-337">W takim przypadku, jeśli wywoływany ma [parametry typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), muszą one być podane jako część wartości możliwej do napisania.</span><span class="sxs-lookup"><span data-stu-id="9f81e-337">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="9f81e-338">Wartość możliwej do odwoływać nie może mieć żadnych nieokreślonych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="9f81e-338">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="9f81e-339">Na przykład jeśli `Fun` jest funkcją z podpisem `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="9f81e-339">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="9f81e-340">Wywoływanie wyrażeń wywołania</span><span class="sxs-lookup"><span data-stu-id="9f81e-340">Callable Invocation Expressions</span></span>

<span data-ttu-id="9f81e-341">Dane wyrażenie możliwego do wywołania (operacji lub funkcji) i wyrażenie spójnej kolekcji typu wejściowego w podpisie, wyrażenie wywoływania może być sformułowane przez dołączenie wyrażenia krotki do możliwego do wywołania wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="9f81e-341">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="9f81e-342">Typ wyrażenia wywołania jest typem wyjściowym podpisu, który ma zostać wywołany.</span><span class="sxs-lookup"><span data-stu-id="9f81e-342">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="9f81e-343">Na przykład jeśli `Op` jest operacją z podpisem `((Int, Qubit) => Double)` , `Op(3, qubit1)` jest wyrażeniem typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-343">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="9f81e-344">Podobnie, jeśli `Sin` jest funkcją z podpisem `(Double -> Double)` , `Sin(0.1)` jest wyrażeniem typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-344">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="9f81e-345">Na koniec, jeśli `Builder` jest funkcją z podpisem `(Int -> (Int -> Int))` , `Builder(3)` to funkcja od do int.</span><span class="sxs-lookup"><span data-stu-id="9f81e-345">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="9f81e-346">Wywołanie wyniku wyrażenia z wartościami możliwymi do wywołania wymaga dodatkowej pary nawiasów wokół wartościowego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="9f81e-346">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="9f81e-347">W związku z tym, aby wywołać wynik wywołania `Builder` z poprzedniego akapitu, poprawna składnia to:</span><span class="sxs-lookup"><span data-stu-id="9f81e-347">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="9f81e-348">W przypadku wywołania [sparametryzowanego typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , rzeczywiste parametry typu można określić w nawiasach kątowych `<` i `>` po wyrażeniu możliwym do wywołania.</span><span class="sxs-lookup"><span data-stu-id="9f81e-348">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="9f81e-349">Zwykle nie jest to konieczne, ponieważ kompilator Q # wykryje rzeczywiste typy.</span><span class="sxs-lookup"><span data-stu-id="9f81e-349">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="9f81e-350">Jednak *jest to* wymagane w przypadku [częściowej aplikacji](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , jeśli argument typu sparametryzowanego nie został określony.</span><span class="sxs-lookup"><span data-stu-id="9f81e-350">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="9f81e-351">Jest to również czasami przydatne, gdy przekazywanie operacji z różnymi Funktor obsługuje do możliwego do odwoływać.</span><span class="sxs-lookup"><span data-stu-id="9f81e-351">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="9f81e-352">Na przykład, jeśli `Func` ma sygnaturę i ma sygnaturę `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` i `Op3` ma sygnaturę `(Qubit[] => Unit)` , do `Func` wywołania `Op1` jako pierwszy argument, `Op2` jako drugi i `Op3` jako trzeci:</span><span class="sxs-lookup"><span data-stu-id="9f81e-352">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="9f81e-353">Specyfikacja typu jest wymagana, ponieważ `Op3` i `Op1` ma różne typy, więc kompilator będzie traktować ten sposób jako niejednoznaczny bez specyfikacji.</span><span class="sxs-lookup"><span data-stu-id="9f81e-353">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="9f81e-354">Kolejność wykonywania działań</span><span class="sxs-lookup"><span data-stu-id="9f81e-354">Operator Precedence</span></span>

<span data-ttu-id="9f81e-355">Wszystkie operatory binarne są z prawej strony skojarzenia, z wyjątkiem `^` .</span><span class="sxs-lookup"><span data-stu-id="9f81e-355">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="9f81e-356">Nawiasy klamrowe `[` i `]` , w przypadku dzielenia i indeksowania tablicy, należy powiązać przed dowolnym operatorem.</span><span class="sxs-lookup"><span data-stu-id="9f81e-356">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="9f81e-357">Funktory `Adjoint` i `Controlled` Powiąż po indeksowaniu tablicy, ale przed wszystkimi innymi operatorami.</span><span class="sxs-lookup"><span data-stu-id="9f81e-357">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="9f81e-358">Nawiasy dla wywołania operacji i funkcji są również powiązane przed dowolnym operatorem, ale po indeksowaniu tablicy i funktory.</span><span class="sxs-lookup"><span data-stu-id="9f81e-358">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="9f81e-359">Operatory według pierwszeństwa, od najwyższego do najniższego:</span><span class="sxs-lookup"><span data-stu-id="9f81e-359">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="9f81e-360">Operator</span><span class="sxs-lookup"><span data-stu-id="9f81e-360">Operator</span></span> | <span data-ttu-id="9f81e-361">Większa</span><span class="sxs-lookup"><span data-stu-id="9f81e-361">Arity</span></span> | <span data-ttu-id="9f81e-362">Opis</span><span class="sxs-lookup"><span data-stu-id="9f81e-362">Description</span></span> | <span data-ttu-id="9f81e-363">Typy operandów</span><span class="sxs-lookup"><span data-stu-id="9f81e-363">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="9f81e-364">końcowe`!`</span><span class="sxs-lookup"><span data-stu-id="9f81e-364">trailing `!`</span></span> | <span data-ttu-id="9f81e-365">Jednoargumentowy</span><span class="sxs-lookup"><span data-stu-id="9f81e-365">Unary</span></span> | <span data-ttu-id="9f81e-366">Unwrap</span><span class="sxs-lookup"><span data-stu-id="9f81e-366">Unwrap</span></span> | <span data-ttu-id="9f81e-367">Dowolny typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="9f81e-367">Any user-defined type</span></span>
 <span data-ttu-id="9f81e-368">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="9f81e-368">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="9f81e-369">Jednoargumentowy</span><span class="sxs-lookup"><span data-stu-id="9f81e-369">Unary</span></span> | <span data-ttu-id="9f81e-370">Cyfra ujemna, dopełnienie bitowe, Negacja logiczna</span><span class="sxs-lookup"><span data-stu-id="9f81e-370">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="9f81e-371">`Int`, `BigInt` lub `Double` dla `-` , `Int` dla `BigInt` `~~~` `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="9f81e-371">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="9f81e-372">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-372">Binary</span></span> | <span data-ttu-id="9f81e-373">Moc całkowita</span><span class="sxs-lookup"><span data-stu-id="9f81e-373">Integer power</span></span> | <span data-ttu-id="9f81e-374">`Int`lub `BigInt` dla podstawy `Int` dla wykładnika</span><span class="sxs-lookup"><span data-stu-id="9f81e-374">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="9f81e-375">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="9f81e-375">`/`, `*`, `%`</span></span> | <span data-ttu-id="9f81e-376">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-376">Binary</span></span> | <span data-ttu-id="9f81e-377">Dzielenie, mnożenie, moduł całkowity</span><span class="sxs-lookup"><span data-stu-id="9f81e-377">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="9f81e-378">`Int`, `BigInt` lub `Double` dla `/` i `*` , `Int` lub `BigInt` dla`%`</span><span class="sxs-lookup"><span data-stu-id="9f81e-378">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="9f81e-379">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="9f81e-379">`+`, `-`</span></span> | <span data-ttu-id="9f81e-380">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-380">Binary</span></span> | <span data-ttu-id="9f81e-381">Dodawanie lub łączenie ciągów i tablic, odejmowanie</span><span class="sxs-lookup"><span data-stu-id="9f81e-381">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="9f81e-382">`Int`, `BigInt` or `Double` , dodatkowo `String` lub dowolnego typu tablicy dla`+`</span><span class="sxs-lookup"><span data-stu-id="9f81e-382">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="9f81e-383">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="9f81e-383">`<<<`, `>>>`</span></span> | <span data-ttu-id="9f81e-384">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-384">Binary</span></span> | <span data-ttu-id="9f81e-385">Lewy Shift, prawy Shift</span><span class="sxs-lookup"><span data-stu-id="9f81e-385">Left shift, right shift</span></span> | <span data-ttu-id="9f81e-386">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9f81e-386">`Int` or `BigInt`</span></span>
 <span data-ttu-id="9f81e-387">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="9f81e-387">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="9f81e-388">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-388">Binary</span></span> | <span data-ttu-id="9f81e-389">Mniejsze niż, mniejsze niż lub równe, większe niż, większe niż lub równe</span><span class="sxs-lookup"><span data-stu-id="9f81e-389">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="9f81e-390">`Int``BigInt`lub`Double`</span><span class="sxs-lookup"><span data-stu-id="9f81e-390">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="9f81e-391">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="9f81e-391">`==`, `!=`</span></span> | <span data-ttu-id="9f81e-392">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-392">Binary</span></span> | <span data-ttu-id="9f81e-393">porównania równe, nierówne</span><span class="sxs-lookup"><span data-stu-id="9f81e-393">equal, not-equal comparisons</span></span> | <span data-ttu-id="9f81e-394">dowolny typ pierwotny</span><span class="sxs-lookup"><span data-stu-id="9f81e-394">any primitive type</span></span>
 `&&&` | <span data-ttu-id="9f81e-395">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-395">Binary</span></span> | <span data-ttu-id="9f81e-396">Bitowe ORAZ</span><span class="sxs-lookup"><span data-stu-id="9f81e-396">Bitwise AND</span></span> | <span data-ttu-id="9f81e-397">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9f81e-397">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="9f81e-398">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-398">Binary</span></span> | <span data-ttu-id="9f81e-399">Bitowe XOR</span><span class="sxs-lookup"><span data-stu-id="9f81e-399">Bitwise XOR</span></span> | <span data-ttu-id="9f81e-400">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9f81e-400">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="9f81e-401">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-401">Binary</span></span> | <span data-ttu-id="9f81e-402">Bitowe OR</span><span class="sxs-lookup"><span data-stu-id="9f81e-402">Bitwise OR</span></span> | <span data-ttu-id="9f81e-403">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9f81e-403">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="9f81e-404">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-404">Binary</span></span> | <span data-ttu-id="9f81e-405">Logiczne AND</span><span class="sxs-lookup"><span data-stu-id="9f81e-405">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="9f81e-406">Binarne</span><span class="sxs-lookup"><span data-stu-id="9f81e-406">Binary</span></span> | <span data-ttu-id="9f81e-407">Logiczne OR</span><span class="sxs-lookup"><span data-stu-id="9f81e-407">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="9f81e-408">Plik binarny/Trzyelementowy</span><span class="sxs-lookup"><span data-stu-id="9f81e-408">Binary/Ternary</span></span> | <span data-ttu-id="9f81e-409">Operator zakresu</span><span class="sxs-lookup"><span data-stu-id="9f81e-409">Range operator</span></span> | `Int`
 <span data-ttu-id="9f81e-410">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="9f81e-410">`?` `|`</span></span> | <span data-ttu-id="9f81e-411">Trójargumentowy</span><span class="sxs-lookup"><span data-stu-id="9f81e-411">Ternary</span></span> | <span data-ttu-id="9f81e-412">Warunkowe</span><span class="sxs-lookup"><span data-stu-id="9f81e-412">Conditional</span></span> | <span data-ttu-id="9f81e-413">`Bool`po lewej stronie</span><span class="sxs-lookup"><span data-stu-id="9f81e-413">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="9f81e-414">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="9f81e-414">`w/` `<-`</span></span> | <span data-ttu-id="9f81e-415">Trójargumentowy</span><span class="sxs-lookup"><span data-stu-id="9f81e-415">Ternary</span></span> | <span data-ttu-id="9f81e-416">Kopiuj i Aktualizuj</span><span class="sxs-lookup"><span data-stu-id="9f81e-416">Copy-and-update</span></span> | <span data-ttu-id="9f81e-417">Zobacz [wyrażenia kopiowania i aktualizowania](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="9f81e-417">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f81e-418">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="9f81e-418">Next steps</span></span>

<span data-ttu-id="9f81e-419">Teraz, gdy można korzystać z wyrażeń w Q #, można [odstawić do operacji i funkcji w q #](xref:microsoft.quantum.guide.operationsfunctions) , aby dowiedzieć się, jak definiować i wywoływać operacje i funkcje.</span><span class="sxs-lookup"><span data-stu-id="9f81e-419">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>

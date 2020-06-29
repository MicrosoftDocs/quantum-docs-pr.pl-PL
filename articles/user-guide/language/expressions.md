---
title: 'Wyrażenia typu w Q #'
description: 'Dowiedz się, jak określać, odwoływać i łączyć stałe, zmienne, operatory, operacje i funkcje jako wyrażenia w Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 1821df6a3a51a62b44f3ccd96b127577c5db990a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415392"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="b9728-103">Wyrażenia typu w Q #</span><span class="sxs-lookup"><span data-stu-id="b9728-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="b9728-104">Wyrażenia liczbowe</span><span class="sxs-lookup"><span data-stu-id="b9728-104">Numeric Expressions</span></span>

<span data-ttu-id="b9728-105">Wyrażenia liczbowe są wyrażeniami typu `Int` , `BigInt` , lub `Double` .</span><span class="sxs-lookup"><span data-stu-id="b9728-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="b9728-106">Oznacza to, że są to liczby całkowite lub zmiennoprzecinkowe.</span><span class="sxs-lookup"><span data-stu-id="b9728-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="b9728-107">`Int`literały w Q # są zapisywane jako sekwencja cyfr.</span><span class="sxs-lookup"><span data-stu-id="b9728-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="b9728-108">Szesnastkowe i binarne liczby całkowite są obsługiwane i zapisywane odpowiednio przy użyciu `0x` `0b` prefiksu i.</span><span class="sxs-lookup"><span data-stu-id="b9728-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="b9728-109">`BigInt`literały w Q # mają kończyć się `l` `L` sufiksem lub.</span><span class="sxs-lookup"><span data-stu-id="b9728-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="b9728-110">Szesnastkowe duże liczby całkowite są obsługiwane i zapisywane z prefiksem "0x".</span><span class="sxs-lookup"><span data-stu-id="b9728-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="b9728-111">W ten sposób wszystkie prawidłowe zastosowania `BigInt` literałów są następujące:</span><span class="sxs-lookup"><span data-stu-id="b9728-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="b9728-112">`Double`literały w Q # są liczbami zmiennoprzecinkowymi zapisanymi przy użyciu cyfr dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="b9728-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="b9728-113">Mogą być napisywane z lub bez separatora dziesiętnego, `.` lub części wykładniczej wskazanej za pomocą znaku "e" lub "e" (po których dozwolone są tylko możliwe znaki minus i cyfry dziesiętne).</span><span class="sxs-lookup"><span data-stu-id="b9728-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="b9728-114">Poniżej podano prawidłowe `Double` literały: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="b9728-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="b9728-115">Uwzględniając wyrażenie tablicy dowolnego typu elementu, można utworzyć `Int` wyrażenie przy użyciu [`Length`](xref:microsoft.quantum.core.length) wbudowanej funkcji, z wyrażeniem tablicy ujętym w nawiasy.</span><span class="sxs-lookup"><span data-stu-id="b9728-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="b9728-116">Na przykład, jeśli `a` jest powiązany z tablicą, `Length(a)` jest wyrażeniem liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="b9728-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="b9728-117">Jeśli `b` jest tablicą tablic liczb całkowitych, `Int[][]` , a następnie `Length(b)` jest liczbą tablic w `b` , i `Length(b[1])` jest liczbą liczb całkowitych w drugiej tablicy podrzędnej w `b` .</span><span class="sxs-lookup"><span data-stu-id="b9728-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="b9728-118">Uwzględniając dwa wyrażenia liczbowe tego samego typu, operatory binarne,, `+` `-` `*` i `/` mogą być używane do tworzenia nowego wyrażenia liczbowego.</span><span class="sxs-lookup"><span data-stu-id="b9728-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="b9728-119">Typ nowego wyrażenia jest taki sam jak typy wyrażeń składowych.</span><span class="sxs-lookup"><span data-stu-id="b9728-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="b9728-120">Podane dwa wyrażenia całkowite, użyj operatora binarnego `^` (potęgi), aby utworzyć nowe wyrażenie liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="b9728-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="b9728-121">Analogicznie, można również użyć `^` z dwoma wyrażeniami podwójnymi, aby utworzyć nowe wyrażenie podwójne.</span><span class="sxs-lookup"><span data-stu-id="b9728-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="b9728-122">Na koniec możesz użyć `^` z dużą liczbą całkowitą z lewej strony i liczbą całkowitą z prawej strony, aby utworzyć nowe wyrażenie Big Integer.</span><span class="sxs-lookup"><span data-stu-id="b9728-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="b9728-123">W takim przypadku drugi parametr musi pasować do 32 bitów; w przeciwnym razie zgłasza błąd czasu wykonania.</span><span class="sxs-lookup"><span data-stu-id="b9728-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="b9728-124">W przypadku dwóch liczb całkowitych lub dużych liczb całkowitych należy utworzyć nowe wyrażenie typu Integer lub Big Integer przy użyciu `%` operatorów (moduł), `&&&` (bitowego i), `|||` (bitowego lub bitowego) `^^^` .</span><span class="sxs-lookup"><span data-stu-id="b9728-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="b9728-125">W przypadku wyrażenia typu Integer lub Big Integer po lewej stronie i wyrażenia liczb całkowitych po prawej stronie `<<<` można użyć operatorów (arytmetyczne przesunięcie w lewo) lub `>>>` (arytmetyczne przesunięcie w prawo), aby utworzyć nowe wyrażenie z tym samym typem co lewe wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="b9728-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="b9728-126">Drugi parametr (wartość przesunięcia) dla operacji Shift musi być większy lub równy zero; zachowanie dla ujemnych kwot przesunięcia jest niezdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="b9728-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="b9728-127">Wartość przesunięcia dla operacji przesunięcia musi być również zgodna z 32 bitowymi; w przeciwnym razie zgłasza błąd czasu wykonania.</span><span class="sxs-lookup"><span data-stu-id="b9728-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="b9728-128">Jeśli liczba przesunięta jest liczbą całkowitą, wówczas wartość przesunięcia jest interpretowana, `mod 64` czyli przesunięcie 1 i przesunięcie 65 ma ten sam efekt.</span><span class="sxs-lookup"><span data-stu-id="b9728-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="b9728-129">W przypadku wartości liczb całkowitych i dużych liczb całkowitych przesunięcia są arytmetyczne.</span><span class="sxs-lookup"><span data-stu-id="b9728-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="b9728-130">Przesunięcie wartości ujemnej w lewo lub w prawo powoduje ujemną liczbę.</span><span class="sxs-lookup"><span data-stu-id="b9728-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="b9728-131">Oznacza to, że przesunięcie jednego kroku w lewo lub w prawo jest takie samo jak mnożenie lub dzielenie odpowiednio przez 2.</span><span class="sxs-lookup"><span data-stu-id="b9728-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="b9728-132">Dzielenie liczb całkowitych i moduł całkowity są zgodne z tym samym zachowaniem dla liczb ujemnych w języku C#.</span><span class="sxs-lookup"><span data-stu-id="b9728-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="b9728-133">Oznacza to, że `a % b` zawsze ma ten sam znak jako `a` i `b * (a / b) + a % b` zawsze równa się `a` .</span><span class="sxs-lookup"><span data-stu-id="b9728-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span>
<span data-ttu-id="b9728-134">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="b9728-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="b9728-135">5</span><span class="sxs-lookup"><span data-stu-id="b9728-135">5</span></span> | <span data-ttu-id="b9728-136">2</span><span class="sxs-lookup"><span data-stu-id="b9728-136">2</span></span> | <span data-ttu-id="b9728-137">2</span><span class="sxs-lookup"><span data-stu-id="b9728-137">2</span></span> | <span data-ttu-id="b9728-138">1</span><span class="sxs-lookup"><span data-stu-id="b9728-138">1</span></span>
 <span data-ttu-id="b9728-139">5</span><span class="sxs-lookup"><span data-stu-id="b9728-139">5</span></span> | <span data-ttu-id="b9728-140">-2</span><span class="sxs-lookup"><span data-stu-id="b9728-140">-2</span></span> | <span data-ttu-id="b9728-141">-2</span><span class="sxs-lookup"><span data-stu-id="b9728-141">-2</span></span> | <span data-ttu-id="b9728-142">1</span><span class="sxs-lookup"><span data-stu-id="b9728-142">1</span></span>
 <span data-ttu-id="b9728-143">-5</span><span class="sxs-lookup"><span data-stu-id="b9728-143">-5</span></span> | <span data-ttu-id="b9728-144">2</span><span class="sxs-lookup"><span data-stu-id="b9728-144">2</span></span> | <span data-ttu-id="b9728-145">-2</span><span class="sxs-lookup"><span data-stu-id="b9728-145">-2</span></span> | <span data-ttu-id="b9728-146">-1</span><span class="sxs-lookup"><span data-stu-id="b9728-146">-1</span></span>
 <span data-ttu-id="b9728-147">-5</span><span class="sxs-lookup"><span data-stu-id="b9728-147">-5</span></span> | <span data-ttu-id="b9728-148">-2</span><span class="sxs-lookup"><span data-stu-id="b9728-148">-2</span></span> | <span data-ttu-id="b9728-149">2</span><span class="sxs-lookup"><span data-stu-id="b9728-149">2</span></span> | <span data-ttu-id="b9728-150">-1</span><span class="sxs-lookup"><span data-stu-id="b9728-150">-1</span></span>

<span data-ttu-id="b9728-151">Operacje dzielenia w dużej liczbie całkowitej i modułu działają w ten sam sposób.</span><span class="sxs-lookup"><span data-stu-id="b9728-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="b9728-152">Mając każde wyrażenie liczbowe, można utworzyć nowe wyrażenie przy użyciu `-` operatora jednoargumentowego.</span><span class="sxs-lookup"><span data-stu-id="b9728-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="b9728-153">Nowe wyrażenie jest tego samego typu co wyrażenie elementu.</span><span class="sxs-lookup"><span data-stu-id="b9728-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="b9728-154">Podanym wyrażeniem liczb całkowitych lub Big Integer można utworzyć nowe wyrażenie tego samego typu przy użyciu `~~~` operatora jednoargumentowego (dopełnienie bitowe).</span><span class="sxs-lookup"><span data-stu-id="b9728-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="b9728-155">Wyrażenia logiczne</span><span class="sxs-lookup"><span data-stu-id="b9728-155">Boolean Expressions</span></span>

<span data-ttu-id="b9728-156">Dwie `Bool` wartości literału są `true` i `false` .</span><span class="sxs-lookup"><span data-stu-id="b9728-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="b9728-157">Uwzględniając wszystkie dwa wyrażenia tego samego typu pierwotnego, `==` Operatory i `!=` mogą być używane do konstruowania `Bool` wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b9728-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="b9728-158">Wyrażenie ma wartość true, jeśli dwa wyrażenia są równe i FAŁSZ, jeśli nie.</span><span class="sxs-lookup"><span data-stu-id="b9728-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="b9728-159">Wartości typów zdefiniowanych przez użytkownika mogą nie być porównywane. można porównać tylko ich nieopakowane wartości.</span><span class="sxs-lookup"><span data-stu-id="b9728-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="b9728-160">Na przykład przy użyciu operatora "unotoka" `!` (szczegółowo wyjaśniono w [typach w Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="b9728-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="b9728-161">Porównywanie równości dla `Qubit` wartości jest równość tożsamości; oznacza to, czy dwa wyrażenia identyfikują ten sam qubit.</span><span class="sxs-lookup"><span data-stu-id="b9728-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="b9728-162">Nie są one porównywane, dostępne, mierzone ani modyfikowane przez to porównanie.</span><span class="sxs-lookup"><span data-stu-id="b9728-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="b9728-163">Porównywanie równości dla `Double` wartości może być mylące ze względu na efekt zaokrąglenia.</span><span class="sxs-lookup"><span data-stu-id="b9728-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="b9728-164">Na przykład `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="b9728-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="b9728-165">Uwzględniając wszystkie dwa wyrażenia liczbowe, operatory binarne `>` ,, `<` `>=` i `<=` mogą być używane do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli pierwsze wyrażenie jest odpowiednio większe niż, mniejsze niż, większe niż lub równe lub mniejsze lub równe drugiemu wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="b9728-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="b9728-166">Uwzględniając wszystkie dwa wyrażenia logiczne, użyj `and` operatora binarnego, aby utworzyć nowe wyrażenie logiczne, które ma wartość true, jeśli oba te dwa wyrażenia mają wartość true.</span><span class="sxs-lookup"><span data-stu-id="b9728-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="b9728-167">Podobnie przy użyciu `or` operatora tworzy wyrażenie, które ma wartość true, jeśli jedno z dwóch wyrażeń ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="b9728-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="b9728-168">Mając każde wyrażenie logiczne, `not` operator jednoargumentowy może służyć do konstruowania nowego wyrażenia logicznego, które ma wartość true, jeśli wyrażenie elementu składowego ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="b9728-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="b9728-169">Wyrażenia ciągu</span><span class="sxs-lookup"><span data-stu-id="b9728-169">String expressions</span></span>

<span data-ttu-id="b9728-170">Funkcja Q # umożliwia używanie ciągów w `fail` instrukcji (objaśnienie w [przepływie sterowania](xref:microsoft.quantum.guide.controlflow#fail-statement)) i w [`Message`](xref:microsoft.quantum.intrinsic.message) funkcji standardowej.</span><span class="sxs-lookup"><span data-stu-id="b9728-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span> <span data-ttu-id="b9728-171">Takie zachowanie jest zależne od używanego symulatora, ale zazwyczaj zapisuje komunikat do konsoli hosta po wywołaniu w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="b9728-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="b9728-172">Ciągi w Q # są literałami lub interpolowanymi ciągami.</span><span class="sxs-lookup"><span data-stu-id="b9728-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="b9728-173">Literały ciągu są podobne do prostych literałów ciągu w większości języków: sekwencji znaków Unicode ujętych w podwójne cudzysłowy `" "` .</span><span class="sxs-lookup"><span data-stu-id="b9728-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="b9728-174">Wewnątrz ciągu Użyj znaku ukośnika odwrotnego, `\` Aby wypróbować znak podwójnego cudzysłowu ( `\"` ) lub wstawić nowy wiersz ( `\n` ), powrót karetki ( `\r` ) lub kartę ( `\t` ).</span><span class="sxs-lookup"><span data-stu-id="b9728-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="b9728-175">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="b9728-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="b9728-176">Ciągi interpolowane</span><span class="sxs-lookup"><span data-stu-id="b9728-176">Interpolated strings</span></span>

<span data-ttu-id="b9728-177">Składnia Q # dla interpolacji ciągów jest podzbiorem składni języka C#.</span><span class="sxs-lookup"><span data-stu-id="b9728-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="b9728-178">Poniżej przedstawiono kluczowe punkty, które odnoszą się do Q #:</span><span class="sxs-lookup"><span data-stu-id="b9728-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="b9728-179">Aby zidentyfikować literał ciągu jako ciąg interpolowany, poprzedź go `$` symbolem.</span><span class="sxs-lookup"><span data-stu-id="b9728-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="b9728-180">Między `$` i `"` , które zaczyna się literałem ciągu znaków, nie może być odstępu.</span><span class="sxs-lookup"><span data-stu-id="b9728-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="b9728-181">Poniżej znajduje się podstawowy przykład, za pomocą którego [`Message`](xref:microsoft.quantum.intrinsic.message) można napisać wynik pomiaru do konsoli wraz z innymi wyrażeniami Q #.</span><span class="sxs-lookup"><span data-stu-id="b9728-181">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="b9728-182">Dowolne prawidłowe wyrażenie Q # może pojawić się w ciągu interpolowanym.</span><span class="sxs-lookup"><span data-stu-id="b9728-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="b9728-183">Wyrażenia wewnątrz ciągu interpolowanego są zgodne z składnią Q #, a nie składnią języka C#.</span><span class="sxs-lookup"><span data-stu-id="b9728-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="b9728-184">Najbardziej istotną różnicą jest to, że Q # nie obsługuje ciągów interpolowanych Verbatim (wiele wierszy).</span><span class="sxs-lookup"><span data-stu-id="b9728-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="b9728-185">Aby uzyskać więcej informacji na temat składni języka C#, zobacz [*interpolowane ciągi*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="b9728-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="b9728-186">Wyrażenia zakresu</span><span class="sxs-lookup"><span data-stu-id="b9728-186">Range Expressions</span></span>

<span data-ttu-id="b9728-187">Uwzględniając wszystkie trzy `Int` wyrażenia `start` , `step` i `stop` wyrażenie `start .. step .. stop` jest wyrażeniem zakresu, którego pierwszy element jest `start` , drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do momentu przekazania `stop` .</span><span class="sxs-lookup"><span data-stu-id="b9728-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="b9728-188">Zakres może być pusty, jeśli na przykład `step` jest wartością dodatnią i `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="b9728-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="b9728-189">Zakres jest włącznie na obu końcach.</span><span class="sxs-lookup"><span data-stu-id="b9728-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="b9728-190">Oznacza to, że jeśli różnica między `start` i `stop` jest wielokrotnością wielokrotności `step` , ostatni element zakresu będzie `stop` .</span><span class="sxs-lookup"><span data-stu-id="b9728-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="b9728-191">Uwzględniając wszystkie dwa `Int` wyrażenia `start` i `stop` wyrażenie `start .. stop` jest wyrażeniem zakresu, które jest równe `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="b9728-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="b9728-192">Należy zauważyć, że implikowana `step` wartość to + 1 `stop` , nawet jeśli jest mniejsza niż `start` ; w takim przypadku zakres jest pusty.</span><span class="sxs-lookup"><span data-stu-id="b9728-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="b9728-193">Oto kilka przykładowych zakresów:</span><span class="sxs-lookup"><span data-stu-id="b9728-193">Some example ranges are:</span></span>

- <span data-ttu-id="b9728-194">`1..3`jest zakresem 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="b9728-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="b9728-195">`2..2..5`jest zakresem od 2 do 4.</span><span class="sxs-lookup"><span data-stu-id="b9728-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="b9728-196">`2..2..6`jest zakresem 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="b9728-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="b9728-197">`6..-2..2`jest zakresem 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="b9728-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="b9728-198">`2..1`jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="b9728-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="b9728-199">`2..6..7`jest zakresem 2.</span><span class="sxs-lookup"><span data-stu-id="b9728-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="b9728-200">`2..2..1`jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="b9728-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="b9728-201">`1..-1..2`jest pustym zakresem.</span><span class="sxs-lookup"><span data-stu-id="b9728-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="b9728-202">Wyrażenia qubit</span><span class="sxs-lookup"><span data-stu-id="b9728-202">Qubit Expressions</span></span>

<span data-ttu-id="b9728-203">Jedyne `Qubit` wyrażenia to symbole, które są powiązane z `Qubit` wartościami lub tablicami elementów tablic `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="b9728-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="b9728-204">Brak `Qubit` literałów.</span><span class="sxs-lookup"><span data-stu-id="b9728-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="b9728-205">Wyrażenia Pauli</span><span class="sxs-lookup"><span data-stu-id="b9728-205">Pauli Expressions</span></span>

<span data-ttu-id="b9728-206">Cztery `Pauli` wartości, `PauliI` ,, `PauliX` `PauliY` i `PauliZ` , są prawidłowymi `Pauli` wyrażeniami.</span><span class="sxs-lookup"><span data-stu-id="b9728-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="b9728-207">Inaczej niż to, jedyne `Pauli` wyrażenia to symbole, które są powiązane z `Pauli` wartościami lub tablicami elementów tablic `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="b9728-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="b9728-208">Wyrażenia wynikowe</span><span class="sxs-lookup"><span data-stu-id="b9728-208">Result Expressions</span></span>

<span data-ttu-id="b9728-209">Dwie `Result` wartości `One` i `Zero` są prawidłowymi `Result` wyrażeniami.</span><span class="sxs-lookup"><span data-stu-id="b9728-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="b9728-210">Inaczej niż to, jedyne `Result` wyrażenia to symbole, które są powiązane z `Result` wartościami lub tablicami elementów tablic `Result` .</span><span class="sxs-lookup"><span data-stu-id="b9728-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="b9728-211">W szczególności należy zauważyć, że `One` nie jest taka sama jak liczba całkowita `1` i nie ma żadnej bezpośredniej konwersji między nimi.</span><span class="sxs-lookup"><span data-stu-id="b9728-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="b9728-212">Ta sama wartość dotyczy `Zero` i `0` .</span><span class="sxs-lookup"><span data-stu-id="b9728-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="b9728-213">Wyrażenia krotki</span><span class="sxs-lookup"><span data-stu-id="b9728-213">Tuple Expressions</span></span>

<span data-ttu-id="b9728-214">Literał krotki to sekwencja wyrażeń elementu odpowiedniego typu, rozdzielona przecinkami, ujęta w nawiasy.</span><span class="sxs-lookup"><span data-stu-id="b9728-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="b9728-215">Na przykład `(1, One)` jest `(Int, Result)` wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="b9728-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="b9728-216">W przypadku innych niż literały jedynymi wyrażeniami krotek są symbole, które są powiązane z wartościami krotki, elementami tablicy tablic krotek i wywoływanie wywołań, które zwracają krotki.</span><span class="sxs-lookup"><span data-stu-id="b9728-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="b9728-217">Wyrażenia typu zdefiniowanego przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="b9728-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="b9728-218">Literał typu zdefiniowanego przez użytkownika składa się z nazwy typu, a następnie literału krotki typu krotki podstawowej typu.</span><span class="sxs-lookup"><span data-stu-id="b9728-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="b9728-219">Na przykład jeśli `IntPair` jest typem zdefiniowanym przez użytkownika `(Int, Int)` , a następnie `IntPair(2, 3)` jest prawidłowym literałem tego typu.</span><span class="sxs-lookup"><span data-stu-id="b9728-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="b9728-220">Oprócz literałów jedynymi wyrażeniami typu zdefiniowanego przez użytkownika są symbole, które są powiązane z wartościami tego typu, elementy tablicy tablic tego typu i wywoływanie wywołań, które zwracają ten typ.</span><span class="sxs-lookup"><span data-stu-id="b9728-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="b9728-221">Odpakowywanie wyrażeń</span><span class="sxs-lookup"><span data-stu-id="b9728-221">Unwrap Expressions</span></span>

<span data-ttu-id="b9728-222">W Q # operator rozwinięcia jest końcowym wykrzyknikiem `!` .</span><span class="sxs-lookup"><span data-stu-id="b9728-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="b9728-223">Na przykład jeśli `IntPair` jest typem zdefiniowanym przez użytkownika z typem źródłowym `(Int, Int)` i `s` jest zmienną o wartości `IntPair(2, 3)` , `s!` to `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="b9728-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="b9728-224">Dla typów zdefiniowanych przez użytkownika, zdefiniowanych w warunkach innych typów zdefiniowanych przez użytkownika, można powtórzyć operator rozwinięcia.</span><span class="sxs-lookup"><span data-stu-id="b9728-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="b9728-225">Na przykład `s!!` wskazuje podwójnie nieopakowaną wartość `s` .</span><span class="sxs-lookup"><span data-stu-id="b9728-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="b9728-226">W takim przypadku, jeśli `WrappedPair` jest typem zdefiniowanym przez użytkownika z typem źródłowym `IntPair` i `t` jest zmienną z wartością `WrappedPair(IntPair(1,2))` , `t!!` to jest `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="b9728-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="b9728-227">`!`Operator ma wyższy priorytet niż wszystkie inne operatory inne niż `[]` dla indeksowania tablicy i dzielenia.</span><span class="sxs-lookup"><span data-stu-id="b9728-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="b9728-228">`!`i `[]` Powiąż, to jest `a[i]![3]` odczytywane jako `((a[i])!)[3]` : Zrób `i` ty element `a` , Odpakuj go, a następnie Pobierz trzeci element nieopakowanej wartości (która musi być tablicą).</span><span class="sxs-lookup"><span data-stu-id="b9728-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="b9728-229">Pierwszeństwo `!` operatora ma jeden wpływ, który może nie być oczywisty.</span><span class="sxs-lookup"><span data-stu-id="b9728-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="b9728-230">Jeśli funkcja lub operacja zwraca wartość, która staje się nieopakowana, wywołanie funkcji lub operacji musi być ujęte w nawiasy, tak aby krotka argumentu była powiązana z wywołaniem, a nie z odwinięciem.</span><span class="sxs-lookup"><span data-stu-id="b9728-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="b9728-231">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="b9728-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="b9728-232">Wyrażenia tablic</span><span class="sxs-lookup"><span data-stu-id="b9728-232">Array Expressions</span></span>

<span data-ttu-id="b9728-233">Literał tablicowy jest sekwencją co najmniej jednego wyrażenia elementu, oddzielone przecinkami, ujęte w nawiasy kwadratowe `[]` .</span><span class="sxs-lookup"><span data-stu-id="b9728-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="b9728-234">Wszystkie elementy muszą być zgodne z tym samym typem.</span><span class="sxs-lookup"><span data-stu-id="b9728-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="b9728-235">Mając dwie tablice tego samego typu, użyj operatora Binary, `+` Aby utworzyć nową tablicę, która jest połączeniem dwóch tablic.</span><span class="sxs-lookup"><span data-stu-id="b9728-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="b9728-236">Na przykład `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="b9728-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="b9728-237">Tworzenie tablicy</span><span class="sxs-lookup"><span data-stu-id="b9728-237">Array Creation</span></span>

<span data-ttu-id="b9728-238">Uwzględniając typ i `Int` wyrażenie, użyj `new` operatora, aby przydzielić nową tablicę o danym rozmiarze.</span><span class="sxs-lookup"><span data-stu-id="b9728-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="b9728-239">Na przykład `new Int[i + 1]` przypisuje nową `Int` tablicę z `i + 1` elementami.</span><span class="sxs-lookup"><span data-stu-id="b9728-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="b9728-240">Puste literały tablicowe, takie jak `[]` , są niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="b9728-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="b9728-241">Zamiast tego można utworzyć tablicę o długości zero przy użyciu `new T[0]` , gdzie `T` jest symbolem zastępczym dla odpowiedniego typu.</span><span class="sxs-lookup"><span data-stu-id="b9728-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="b9728-242">Elementy nowej tablicy są inicjowane do wartości domyślnej zależnej od typu.</span><span class="sxs-lookup"><span data-stu-id="b9728-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="b9728-243">W większości przypadków jest to pewna odmiana zero.</span><span class="sxs-lookup"><span data-stu-id="b9728-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="b9728-244">W przypadku qubits i elementów, które są odwołaniami do jednostek, nie ma żadnej rozsądnej wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="b9728-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="b9728-245">W związku z tym, wartością domyślną jest nieprawidłowe odwołanie, którego nie można użyć bez powodowania błędu czasu wykonywania, podobnie jak w przypadku odwołań o wartości null w językach, takich jak C# lub Java.</span><span class="sxs-lookup"><span data-stu-id="b9728-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="b9728-246">Tablice zawierające qubits lub elementy wywoływane muszą zostać zainicjowane przy użyciu wartości innych niż domyślne, aby można było bezpiecznie używać ich elementów.</span><span class="sxs-lookup"><span data-stu-id="b9728-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="b9728-247">Odpowiednie procedury inicjowania można znaleźć w temacie <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="b9728-247">For suitable initialization routines, see <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="b9728-248">Wartości domyślne dla każdego typu są następujące:</span><span class="sxs-lookup"><span data-stu-id="b9728-248">The default values for each type are:</span></span>

<span data-ttu-id="b9728-249">Typ</span><span class="sxs-lookup"><span data-stu-id="b9728-249">Type</span></span> | <span data-ttu-id="b9728-250">Domyślne</span><span class="sxs-lookup"><span data-stu-id="b9728-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="b9728-251">_Nieprawidłowy qubit_</span><span class="sxs-lookup"><span data-stu-id="b9728-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="b9728-252">Pusty zakres,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="b9728-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="b9728-253">_nieprawidłowe wywoływanie_</span><span class="sxs-lookup"><span data-stu-id="b9728-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="b9728-254">Typy krotek inicjują element po elemencie.</span><span class="sxs-lookup"><span data-stu-id="b9728-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="b9728-255">Elementy tablicy</span><span class="sxs-lookup"><span data-stu-id="b9728-255">Array Elements</span></span>

<span data-ttu-id="b9728-256">Podaną wyrażeniem tablicowym i `Int` wyrażeniem, należy utworzyć nowe wyrażenie przy użyciu operatora elementu tablicy `[]` .</span><span class="sxs-lookup"><span data-stu-id="b9728-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="b9728-257">Nowe wyrażenie jest tego samego typu co typ elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="b9728-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="b9728-258">Na przykład jeśli `a` jest powiązany z tablicą typu `Double` , wówczas `a[4]` jest `Double` wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="b9728-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="b9728-259">Jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, należy umieścić je w nawiasach, aby wybrać element.</span><span class="sxs-lookup"><span data-stu-id="b9728-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="b9728-260">Na przykład jeśli `a` i `b` są obie tablice typu `Int` , element z łączenia jest wyrażony jako:</span><span class="sxs-lookup"><span data-stu-id="b9728-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="b9728-261">Wszystkie tablice w Q # są oparte na zero.</span><span class="sxs-lookup"><span data-stu-id="b9728-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="b9728-262">Oznacza to, że pierwszy element tablicy `a` jest zawsze `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="b9728-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="b9728-263">Wycinki tablicy</span><span class="sxs-lookup"><span data-stu-id="b9728-263">Array Slices</span></span>

<span data-ttu-id="b9728-264">Podaną wyrażeniem tablicowym i `Range` wyrażeniem, należy utworzyć nowe wyrażenie przy użyciu operatora wycinka tablicy `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="b9728-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="b9728-265">Nowe wyrażenie jest tego samego typu co tablica i zawiera elementy tablicy indeksowane przez elementy w `Range` kolejności zdefiniowanej przez `Range` .</span><span class="sxs-lookup"><span data-stu-id="b9728-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="b9728-266">Na przykład, jeśli `a` jest powiązany z tablicą typu `Double` , `a[3..-1..0]` to `Double[]` wyrażenie, które zawiera pierwsze cztery elementy, `a` ale w odwrotnej kolejności, jak pojawiają się w `a` .</span><span class="sxs-lookup"><span data-stu-id="b9728-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="b9728-267">Jeśli wartość `Range` jest pusta, powstaje wycinek tablicy o zerowej długości.</span><span class="sxs-lookup"><span data-stu-id="b9728-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="b9728-268">Podobnie jak w przypadku elementów tablicy odwołujących się, jeśli wyrażenie tablicowe nie jest prostym identyfikatorem, należy umieścić je w nawiasach, aby je podzielić.</span><span class="sxs-lookup"><span data-stu-id="b9728-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="b9728-269">Na przykład jeśli `a` i `b` są obie tablice typu `Int` , wycinek z łączenia jest wyrażony jako:</span><span class="sxs-lookup"><span data-stu-id="b9728-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="b9728-270">Wywnioskowane wartości początkowe/końcowe</span><span class="sxs-lookup"><span data-stu-id="b9728-270">Inferred start/end values</span></span>

<span data-ttu-id="b9728-271">Począwszy od naszego [0,8 wydania](xref:microsoft.quantum.relnotes), obsługujemy kontekstowe wyrażenia dla dzielenia zakresów.</span><span class="sxs-lookup"><span data-stu-id="b9728-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="b9728-272">W szczególności można pominąć zakres wartości początkowych i końcowych w kontekście wyrażenia wycinka zakresu.</span><span class="sxs-lookup"><span data-stu-id="b9728-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="b9728-273">W takim przypadku kompilator stosuje następujące reguły w celu wywnioskowania zamierzonych ograniczników dla zakresu:</span><span class="sxs-lookup"><span data-stu-id="b9728-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="b9728-274">Jeśli wartość *początkowa* zakresu zostanie pominięta, wywnioskowana wartość początkowa</span><span class="sxs-lookup"><span data-stu-id="b9728-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="b9728-275">ma wartość zero, jeśli nie określono żadnego kroku lub określony krok jest dodatni.</span><span class="sxs-lookup"><span data-stu-id="b9728-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="b9728-276">jest długością tablicy wycinka minus jeden, jeśli określony krok jest ujemny.</span><span class="sxs-lookup"><span data-stu-id="b9728-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="b9728-277">W przypadku pominięcia wartości *końcowej* zakresu, wywnioskowana wartość końcowa</span><span class="sxs-lookup"><span data-stu-id="b9728-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="b9728-278">jest długością tablicy wycinka minus jeden, jeśli żaden krok nie jest określony lub określony krok jest dodatni.</span><span class="sxs-lookup"><span data-stu-id="b9728-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="b9728-279">ma wartość zero, jeśli określony krok jest ujemny.</span><span class="sxs-lookup"><span data-stu-id="b9728-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="b9728-280">Przykłady to:</span><span class="sxs-lookup"><span data-stu-id="b9728-280">Some examples are:</span></span>

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="b9728-281">Wyrażenia kopiowania i aktualizowania</span><span class="sxs-lookup"><span data-stu-id="b9728-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="b9728-282">Ponieważ wszystkie typy pytań i odpowiedzi są typami wartości (z qubitsą z pewnymi szczególnymi rolami), formularz "Copy" jest tworzony, gdy wartość jest powiązana z symbolem lub gdy jest on powiązany.</span><span class="sxs-lookup"><span data-stu-id="b9728-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="b9728-283">Oznacza to, że zachowanie Q # jest takie samo, jak w przypadku utworzenia kopii przy użyciu operatora przypisania.</span><span class="sxs-lookup"><span data-stu-id="b9728-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="b9728-284">Oczywiście tylko odpowiednie fragmenty są ponownie tworzone w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="b9728-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="b9728-285">Ma to wpływ na sposób kopiowania tablic, ponieważ nie jest możliwe aktualizowanie elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="b9728-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="b9728-286">Aby zmodyfikować istniejącą tablicę, należy wykorzystać mechanizm *kopiowania i aktualizowania* .</span><span class="sxs-lookup"><span data-stu-id="b9728-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="b9728-287">Można utworzyć nową tablicę z istniejącej tablicy za pośrednictwem wyrażeń *kopiowania i aktualizowania* , które używają operatorów `w/` i `<-` .</span><span class="sxs-lookup"><span data-stu-id="b9728-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="b9728-288">Wyrażenie Copy-and-Update jest wyrażeniem formularza `expression1 w/ expression2 <- expression3` , gdzie</span><span class="sxs-lookup"><span data-stu-id="b9728-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="b9728-289">`expression1`Typ musi być typem `T[]` `T` .</span><span class="sxs-lookup"><span data-stu-id="b9728-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="b9728-290">`expression2`definiuje, które indeksy w tablicy określone w `expression1` do zmodyfikowania.</span><span class="sxs-lookup"><span data-stu-id="b9728-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="b9728-291">`expression2`musi to być typ `Int` lub typ `Range` .</span><span class="sxs-lookup"><span data-stu-id="b9728-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="b9728-292">`expression3`to wartości używane do aktualizowania elementów w programie `expression1` , na podstawie indeksów określonych w `expression2` .</span><span class="sxs-lookup"><span data-stu-id="b9728-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="b9728-293">Jeśli `expression2` jest typu `Int` , `expression3` musi być typu `T` .</span><span class="sxs-lookup"><span data-stu-id="b9728-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="b9728-294">Jeśli `expression2` jest typu `Range` , `expression3` musi być typu `T[]` .</span><span class="sxs-lookup"><span data-stu-id="b9728-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="b9728-295">Na przykład wyrażenie Copy-and-Update `arr w/ idx <- value` konstruuje nową tablicę ze wszystkimi elementami ustawionymi na odpowiadające im elementy w `arr` , z wyjątkiem elementów określonych przez `idx` , które są ustawione na wartości w `value` .</span><span class="sxs-lookup"><span data-stu-id="b9728-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="b9728-296">Dostarczone `arr` zawiera tablicę `[0,1,2,3]` , a następnie</span><span class="sxs-lookup"><span data-stu-id="b9728-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="b9728-297">`arr w/ 0 <- 10`jest tablicą `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="b9728-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="b9728-298">`arr w/ 2 <- 10`jest tablicą `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="b9728-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="b9728-299">`arr w/ 0..2..3 <- [10,12]`jest tablicą `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="b9728-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="b9728-300">Wyrażenia Copy-and-Update dla nazwanych elementów</span><span class="sxs-lookup"><span data-stu-id="b9728-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="b9728-301">Podobne wyrażenia istnieją dla nazwanych elementów w typach zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b9728-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="b9728-302">Rozważmy na przykład typ</span><span class="sxs-lookup"><span data-stu-id="b9728-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="b9728-303">Jeśli `c` zawiera wartość typu `Complex(1., -1.)` , `c w/ Re <- 0.` jest wyrażeniem typu, `Complex` który jest obliczany `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="b9728-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="b9728-304">Tablice nieregularne</span><span class="sxs-lookup"><span data-stu-id="b9728-304">Jagged Arrays</span></span>

<span data-ttu-id="b9728-305">Tablica nieregularna, czasami nazywana "tablicą tablic," jest tablicą, której elementy są tablicami.</span><span class="sxs-lookup"><span data-stu-id="b9728-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="b9728-306">Elementy tablicy nieregularnej mogą mieć różne rozmiary.</span><span class="sxs-lookup"><span data-stu-id="b9728-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="b9728-307">Poniższy przykład pokazuje, jak zadeklarować i zainicjować tablicę nieregularną reprezentującą tabelę mnożenia.</span><span class="sxs-lookup"><span data-stu-id="b9728-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="b9728-308">Tablice wywoływanych</span><span class="sxs-lookup"><span data-stu-id="b9728-308">Arrays of callables</span></span> 

<span data-ttu-id="b9728-309">Można również utworzyć tablicę z możliwymi do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="b9728-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="b9728-310">Jeśli wspólny typ elementu jest operacją lub typem funkcji, wszystkie elementy muszą mieć te same typy danych wejściowych i wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="b9728-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="b9728-311">Typ elementu tablicy obsługuje wszystkie [funktory](xref:microsoft.quantum.guide.operationsfunctions) , które są obsługiwane przez wszystkie elementy.</span><span class="sxs-lookup"><span data-stu-id="b9728-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="b9728-312">Na przykład jeśli `Op1` , `Op2` , i `Op3` wszystkie są `Qubit[] => Unit` operacjami, ale `Op1` obsługuje `Adjoint` , `Op2` obsługuje `Controlled` i `Op3` obsługuje obie:</span><span class="sxs-lookup"><span data-stu-id="b9728-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="b9728-313">`[Op1, Op2]`jest tablicą `(Qubit[] => Unit)` operacji.</span><span class="sxs-lookup"><span data-stu-id="b9728-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="b9728-314">`[Op1, Op3]`jest tablicą `(Qubit[] => Unit is Adj)` operacji.</span><span class="sxs-lookup"><span data-stu-id="b9728-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="b9728-315">`[Op2, Op3]`jest tablicą `(Qubit[] => Unit is Ctl)` operacji.</span><span class="sxs-lookup"><span data-stu-id="b9728-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="b9728-316">Jednak chociaż operacje `(Qubit[] => Unit is Adj)` i `(Qubit[] => Unit is Ctl)` mają wspólny typ podstawowy `(Qubit[] => Unit)` , *tablice* tych operacji nie mają wspólnego typu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="b9728-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="b9728-317">Na przykład `[[Op1], [Op2]]` obecnie zgłaszany jest błąd, ponieważ próbuje utworzyć tablicę dwóch niezgodnych typów tablicy `(Qubit[] => Unit is Adj)[]` i `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="b9728-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="b9728-318">Aby uzyskać więcej informacji o wywoływaniu, zobacz temat wywoływane [wyrażenia](#callable-expressions) na tej stronie lub [operacjach i funkcjach w Q #](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="b9728-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="b9728-319">Wyrażenia warunkowe</span><span class="sxs-lookup"><span data-stu-id="b9728-319">Conditional Expressions</span></span>

<span data-ttu-id="b9728-320">W przypadku dwóch wyrażeń tego samego typu i wyrażenia logicznego należy utworzyć wyrażenie warunkowe przy użyciu znaku zapytania, `?` i paska pionowego `|` .</span><span class="sxs-lookup"><span data-stu-id="b9728-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="b9728-321">W `a==b ? c | d` przypadku wartości wyrażenia warunkowego występuje wartość `c` true, `a==b` a jeśli wartość `d` to false.</span><span class="sxs-lookup"><span data-stu-id="b9728-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="b9728-322">Wyrażenia warunkowe z możliwymi do odwoływać</span><span class="sxs-lookup"><span data-stu-id="b9728-322">Conditional expressions with callables</span></span>

<span data-ttu-id="b9728-323">Wyrażenia warunkowe mogą oszacować operacje, które mają te same dane wejściowe i wyjściowe, ale obsługują różne funktory.</span><span class="sxs-lookup"><span data-stu-id="b9728-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="b9728-324">W tym przypadku typ wyrażenia warunkowego jest operacją z danymi wejściowymi i wyjściowymi, które obsługują wszystkie funktory obsługiwane przez oba wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b9728-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="b9728-325">Na przykład jeśli `Op1` , `Op2` , i `Op3` wszystkie są `Qubit[]=>Unit` , ale obsługuje, `Op1` `Adjoint` `Op2` obsługuje `Controlled` i `Op3` obsługuje obie:</span><span class="sxs-lookup"><span data-stu-id="b9728-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="b9728-326">`flag ? Op1 | Op2`jest `(Qubit[] => Unit)` operacją.</span><span class="sxs-lookup"><span data-stu-id="b9728-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="b9728-327">`flag ? Op1 | Op3`jest `(Qubit[] => Unit is Adj)` operacją.</span><span class="sxs-lookup"><span data-stu-id="b9728-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="b9728-328">`flag ? Op2 | Op3`jest `(Qubit[] => Unit is Ctl)` operacją.</span><span class="sxs-lookup"><span data-stu-id="b9728-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="b9728-329">Jeśli jedno z dwóch możliwych wyrażeń wynikowych zawiera wywołanie funkcji lub operacji, to wywołanie odbywa się tylko wtedy, gdy ten wynik jest wartością wywołania.</span><span class="sxs-lookup"><span data-stu-id="b9728-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="b9728-330">Na przykład w przypadku `a==b ? C(qs) | D(qs)` , gdy `a==b` ma wartość true, `C` operacja jest wywoływana, a jeśli ma wartość false, `D` wywoływana jest tylko operacja.</span><span class="sxs-lookup"><span data-stu-id="b9728-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="b9728-331">Takie podejście jest podobne do *krótkich obwodów* w innych językach.</span><span class="sxs-lookup"><span data-stu-id="b9728-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="b9728-332">Możliwe do przewyrażenia</span><span class="sxs-lookup"><span data-stu-id="b9728-332">Callable Expressions</span></span>

<span data-ttu-id="b9728-333">Możliwy do przeprowadzenia literał jest nazwą operacji lub funkcji zdefiniowanej w zakresie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="b9728-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="b9728-334">Na przykład, `X` to literał operacji odwołujący się do standardowej `X` operacji biblioteki i `Message` jest literałem funkcji, która odwołuje się do standardowej `Message` funkcji biblioteki.</span><span class="sxs-lookup"><span data-stu-id="b9728-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="b9728-335">Jeśli operacja obsługuje `Adjoint` Funktor, `Adjoint op` to wyrażenie operacji.</span><span class="sxs-lookup"><span data-stu-id="b9728-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="b9728-336">Podobnie, jeśli operacja obsługuje `Controlled` Funktor, a następnie `Controlled op` jest wyrażeniem operacji.</span><span class="sxs-lookup"><span data-stu-id="b9728-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="b9728-337">Aby uzyskać więcej informacji na temat typów tych wyrażeń, zobacz temat [wywoływanie specjalizacji operacji](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="b9728-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="b9728-338">Funktory ( `Adjoint` i `Controlled` ) wiąże się bardziej ściśle niż wszystkie inne operatory, z wyjątkiem operatora rozwinięcia `!` i indeksowania tablicy przy użyciu `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="b9728-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="b9728-339">W ten sposób wszystkie są prawidłowe, przy założeniu, że operacje obsługują używany funktory:</span><span class="sxs-lookup"><span data-stu-id="b9728-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="b9728-340">Wyrażenia, które możliwe do napisania</span><span class="sxs-lookup"><span data-stu-id="b9728-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="b9728-341">Można użyć możliwego do oddzielenia literału jako wartości, na przykład w celu przypisania jej do zmiennej lub przekazania jej do innego elementu, który można wywołać.</span><span class="sxs-lookup"><span data-stu-id="b9728-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="b9728-342">W tym przypadku, jeśli wywołano [parametry typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), należy podać parametry jako część wartości możliwej do nadania.</span><span class="sxs-lookup"><span data-stu-id="b9728-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="b9728-343">Wartość możliwej do odwoływać nie może mieć żadnych nieokreślonych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="b9728-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="b9728-344">Na przykład jeśli `Fun` jest funkcją z podpisem `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="b9728-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="b9728-345">Wywoływanie wyrażeń wywołania</span><span class="sxs-lookup"><span data-stu-id="b9728-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="b9728-346">W wyniku możliwego do wywołania wyrażenia (operacji lub funkcji) i wyrażenia spójnej kolekcji typu wejściowego można utworzyć *wyrażenie wywoływania* , dołączając wyrażenie krotki do możliwego do wywołania wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b9728-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="b9728-347">Typ wyrażenia wywołania jest typem wyjściowym podpisu, który ma zostać wywołany.</span><span class="sxs-lookup"><span data-stu-id="b9728-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="b9728-348">Na przykład jeśli `Op` jest operacją z podpisem `((Int, Qubit) => Double)` , `Op(3, qubit1)` jest wyrażeniem typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="b9728-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="b9728-349">Podobnie, jeśli `Sin` jest funkcją z podpisem `(Double -> Double)` , `Sin(0.1)` jest wyrażeniem typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="b9728-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="b9728-350">Na koniec, jeśli `Builder` jest funkcją z podpisem `(Int -> (Int -> Int))` , `Builder(3)` to funkcja z `Int` do `Int` .</span><span class="sxs-lookup"><span data-stu-id="b9728-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="b9728-351">Wywołanie wyniku wyrażenia z wartościami możliwymi do wywołania wymaga dodatkowej pary nawiasów wokół wartościowego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b9728-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="b9728-352">W związku z tym, aby wywołać wynik wywołania `Builder` z poprzedniego akapitu, poprawna składnia to:</span><span class="sxs-lookup"><span data-stu-id="b9728-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="b9728-353">Podczas wywoływania [sparametryzowanego typu](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , można określić rzeczywiste parametry typu w nawiasach kątowych `< >` po dodaniu wartości wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="b9728-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="b9728-354">Ta akcja jest zwykle zbędna, ponieważ kompilator Q # wnioskuje o rzeczywiste typy.</span><span class="sxs-lookup"><span data-stu-id="b9728-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="b9728-355">Jednak *jest to* wymagane w przypadku [częściowej aplikacji](xref:microsoft.quantum.guide.operationsfunctions#partial-application) , jeśli argument typu sparametryzowanego nie został określony.</span><span class="sxs-lookup"><span data-stu-id="b9728-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="b9728-356">Jest on również przydatny, gdy przekazywanie operacji przy użyciu różnych Funktor obsługuje wywoływany.</span><span class="sxs-lookup"><span data-stu-id="b9728-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="b9728-357">Na przykład, jeśli `Func` ma sygnaturę i ma sygnaturę `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` i `Op3` ma sygnaturę `(Qubit[] => Unit)` , do `Func` wywołania `Op1` jako pierwszy argument, `Op2` jako drugi, a `Op3` jako trzeci:</span><span class="sxs-lookup"><span data-stu-id="b9728-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="b9728-358">Specyfikacja typu jest wymagana, ponieważ `Op3` i `Op1` ma różne typy, więc kompilator będzie traktować ten sposób jako niejednoznaczny bez specyfikacji.</span><span class="sxs-lookup"><span data-stu-id="b9728-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="b9728-359">Kolejność wykonywania działań</span><span class="sxs-lookup"><span data-stu-id="b9728-359">Operator Precedence</span></span>

* <span data-ttu-id="b9728-360">Wszystkie operatory binarne są z prawej strony skojarzenia, z wyjątkiem `^` .</span><span class="sxs-lookup"><span data-stu-id="b9728-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="b9728-361">Nawiasy kwadratowe, `[ ]` , w przypadku dzielenia i indeksowania tablicy, są powiązane przed dowolnym operatorem.</span><span class="sxs-lookup"><span data-stu-id="b9728-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="b9728-362">Funktory `Adjoint` i `Controlled` Powiąż po indeksowaniu tablicy, ale przed wszystkimi innymi operatorami.</span><span class="sxs-lookup"><span data-stu-id="b9728-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="b9728-363">Nawiasy dla wywołania operacji i funkcji są również powiązane przed dowolnym operatorem, ale po indeksowaniu tablicy i funktory.</span><span class="sxs-lookup"><span data-stu-id="b9728-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="b9728-364">Operatory Q # według pierwszeństwa, od najwyższego do najniższego:</span><span class="sxs-lookup"><span data-stu-id="b9728-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="b9728-365">Operator</span><span class="sxs-lookup"><span data-stu-id="b9728-365">Operator</span></span> | <span data-ttu-id="b9728-366">Większa</span><span class="sxs-lookup"><span data-stu-id="b9728-366">Arity</span></span> | <span data-ttu-id="b9728-367">Opis</span><span class="sxs-lookup"><span data-stu-id="b9728-367">Description</span></span> | <span data-ttu-id="b9728-368">Typy operandów</span><span class="sxs-lookup"><span data-stu-id="b9728-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="b9728-369">końcowe`!`</span><span class="sxs-lookup"><span data-stu-id="b9728-369">trailing `!`</span></span> | <span data-ttu-id="b9728-370">Jednoargumentowy</span><span class="sxs-lookup"><span data-stu-id="b9728-370">Unary</span></span> | <span data-ttu-id="b9728-371">Unwrap</span><span class="sxs-lookup"><span data-stu-id="b9728-371">Unwrap</span></span> | <span data-ttu-id="b9728-372">Dowolny typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="b9728-372">Any user-defined type</span></span>
 <span data-ttu-id="b9728-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="b9728-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="b9728-374">Jednoargumentowy</span><span class="sxs-lookup"><span data-stu-id="b9728-374">Unary</span></span> | <span data-ttu-id="b9728-375">Cyfra ujemna, dopełnienie bitowe, Negacja logiczna</span><span class="sxs-lookup"><span data-stu-id="b9728-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="b9728-376">`Int`, `BigInt` lub `Double` dla `-` , `Int` dla `BigInt` `~~~` `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="b9728-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="b9728-377">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-377">Binary</span></span> | <span data-ttu-id="b9728-378">Moc całkowita</span><span class="sxs-lookup"><span data-stu-id="b9728-378">Integer power</span></span> | <span data-ttu-id="b9728-379">`Int`lub `BigInt` dla podstawy `Int` dla wykładnika</span><span class="sxs-lookup"><span data-stu-id="b9728-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="b9728-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="b9728-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="b9728-381">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-381">Binary</span></span> | <span data-ttu-id="b9728-382">Dzielenie, mnożenie, moduł całkowity</span><span class="sxs-lookup"><span data-stu-id="b9728-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="b9728-383">`Int`, `BigInt` lub `Double` dla `/` i `*` , `Int` lub `BigInt` dla`%`</span><span class="sxs-lookup"><span data-stu-id="b9728-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="b9728-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="b9728-384">`+`, `-`</span></span> | <span data-ttu-id="b9728-385">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-385">Binary</span></span> | <span data-ttu-id="b9728-386">Dodawanie lub łączenie ciągów i tablic, odejmowanie</span><span class="sxs-lookup"><span data-stu-id="b9728-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="b9728-387">`Int`, `BigInt` or `Double` , dodatkowo `String` lub dowolnego typu tablicy dla`+`</span><span class="sxs-lookup"><span data-stu-id="b9728-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="b9728-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="b9728-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="b9728-389">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-389">Binary</span></span> | <span data-ttu-id="b9728-390">Lewy Shift, prawy Shift</span><span class="sxs-lookup"><span data-stu-id="b9728-390">Left shift, right shift</span></span> | <span data-ttu-id="b9728-391">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b9728-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="b9728-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="b9728-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="b9728-393">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-393">Binary</span></span> | <span data-ttu-id="b9728-394">Mniejsze niż, mniejsze niż lub równe, większe niż, większe niż lub równe</span><span class="sxs-lookup"><span data-stu-id="b9728-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="b9728-395">`Int``BigInt`lub`Double`</span><span class="sxs-lookup"><span data-stu-id="b9728-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="b9728-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="b9728-396">`==`, `!=`</span></span> | <span data-ttu-id="b9728-397">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-397">Binary</span></span> | <span data-ttu-id="b9728-398">porównania równe, nierówne</span><span class="sxs-lookup"><span data-stu-id="b9728-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="b9728-399">dowolny typ pierwotny</span><span class="sxs-lookup"><span data-stu-id="b9728-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="b9728-400">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-400">Binary</span></span> | <span data-ttu-id="b9728-401">Bitowe ORAZ</span><span class="sxs-lookup"><span data-stu-id="b9728-401">Bitwise AND</span></span> | <span data-ttu-id="b9728-402">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b9728-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="b9728-403">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-403">Binary</span></span> | <span data-ttu-id="b9728-404">Bitowe XOR</span><span class="sxs-lookup"><span data-stu-id="b9728-404">Bitwise XOR</span></span> | <span data-ttu-id="b9728-405">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b9728-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="b9728-406">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-406">Binary</span></span> | <span data-ttu-id="b9728-407">Bitowe OR</span><span class="sxs-lookup"><span data-stu-id="b9728-407">Bitwise OR</span></span> | <span data-ttu-id="b9728-408">`Int` lub `BigInt`</span><span class="sxs-lookup"><span data-stu-id="b9728-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="b9728-409">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-409">Binary</span></span> | <span data-ttu-id="b9728-410">Logiczne AND</span><span class="sxs-lookup"><span data-stu-id="b9728-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="b9728-411">Binarne</span><span class="sxs-lookup"><span data-stu-id="b9728-411">Binary</span></span> | <span data-ttu-id="b9728-412">Logiczne OR</span><span class="sxs-lookup"><span data-stu-id="b9728-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="b9728-413">Plik binarny/Trzyelementowy</span><span class="sxs-lookup"><span data-stu-id="b9728-413">Binary/Ternary</span></span> | <span data-ttu-id="b9728-414">Operator zakresu</span><span class="sxs-lookup"><span data-stu-id="b9728-414">Range operator</span></span> | `Int`
 <span data-ttu-id="b9728-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="b9728-415">`?` `|`</span></span> | <span data-ttu-id="b9728-416">Trójargumentowy</span><span class="sxs-lookup"><span data-stu-id="b9728-416">Ternary</span></span> | <span data-ttu-id="b9728-417">Warunkowe</span><span class="sxs-lookup"><span data-stu-id="b9728-417">Conditional</span></span> | <span data-ttu-id="b9728-418">`Bool`po lewej stronie</span><span class="sxs-lookup"><span data-stu-id="b9728-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="b9728-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="b9728-419">`w/` `<-`</span></span> | <span data-ttu-id="b9728-420">Trójargumentowy</span><span class="sxs-lookup"><span data-stu-id="b9728-420">Ternary</span></span> | <span data-ttu-id="b9728-421">Kopiuj i Aktualizuj</span><span class="sxs-lookup"><span data-stu-id="b9728-421">Copy-and-update</span></span> | <span data-ttu-id="b9728-422">Zobacz [wyrażenia kopiowania i aktualizowania](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="b9728-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9728-423">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="b9728-423">Next steps</span></span>

<span data-ttu-id="b9728-424">Teraz, gdy możesz korzystać z wyrażeń w Q #, przejdź do [operacji i funkcji w q #](xref:microsoft.quantum.guide.operationsfunctions) , aby dowiedzieć się, jak definiować i wywoływać operacje i funkcje.</span><span class="sxs-lookup"><span data-stu-id="b9728-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>

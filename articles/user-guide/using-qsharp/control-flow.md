---
title: 'Przepływ sterowania w p #'
description: Pętle, warunkowe itd.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: c534e016fcb8b50e66c11ca29c253ba0512acc6e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430955"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="4664d-103">Przepływ sterowania w p #</span><span class="sxs-lookup"><span data-stu-id="4664d-103">Control Flow in Q#</span></span>

<span data-ttu-id="4664d-104">W ramach operacji lub funkcji każda instrukcja jest wykonywana w kolejności, podobnie jak w przypadku najczęściej używanych języków klasycznych.</span><span class="sxs-lookup"><span data-stu-id="4664d-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="4664d-105">Ten przepływ sterowania można jednak zmodyfikować na trzy różne sposoby:</span><span class="sxs-lookup"><span data-stu-id="4664d-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="4664d-106">`if`zatwierdzeni</span><span class="sxs-lookup"><span data-stu-id="4664d-106">`if` statements</span></span>
- <span data-ttu-id="4664d-107">`for`pętli</span><span class="sxs-lookup"><span data-stu-id="4664d-107">`for` loops</span></span>
- <span data-ttu-id="4664d-108">`repeat`-`until`pętli</span><span class="sxs-lookup"><span data-stu-id="4664d-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="4664d-109">W dalszej części [znajdziesz poniższe](#repeat-until-success-loop)Omówienie.</span><span class="sxs-lookup"><span data-stu-id="4664d-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="4664d-110">`if` `for` Konstrukcje przepływu sterowania i są jednak bardziej zrozumiałe dla większości klasycznych języków programowania.</span><span class="sxs-lookup"><span data-stu-id="4664d-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="4664d-111">Należy pamiętać, że `for` pętle i `if` instrukcje mogą być nawet używane w operacjach, dla których specjalizacje są generowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4664d-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="4664d-112">W takim przypadku sąsiadująca `for` Pętla odwraca kierunek i przyjmuje sąsiadujące poszczególne iteracje.</span><span class="sxs-lookup"><span data-stu-id="4664d-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="4664d-113">Ta zasada jest zgodna z zasadą "buty i-SOCKS": Jeśli chcesz cofnąć umieszczanie w ramach SOCKS, a następnie odbuty, musisz cofnąć umieszczanie na butów, a następnie cofnąć umieszczenie w usłudze SOCKS.</span><span class="sxs-lookup"><span data-stu-id="4664d-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="4664d-114">Decidedly mniej dobrze, aby wypróbować i podjąć Twoje SOCKS, gdy będziesz nadal korzystać z swoich oddziałów.</span><span class="sxs-lookup"><span data-stu-id="4664d-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="4664d-115">If, Else-IF, else</span><span class="sxs-lookup"><span data-stu-id="4664d-115">If, Else-if, Else</span></span>

<span data-ttu-id="4664d-116">`if`Instrukcja obsługuje wykonywanie warunkowe.</span><span class="sxs-lookup"><span data-stu-id="4664d-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="4664d-117">Składa się ze słowa kluczowego `if` , otwartego nawiasu, `(` wyrażenia logicznego, nawiasu zamykającego `)` i bloku instrukcji (bloku _then_ ).</span><span class="sxs-lookup"><span data-stu-id="4664d-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="4664d-118">Może to być dowolna liczba klauzul innych niż, z których każda składa się ze słowa kluczowego `elif` , otwierającego nawiasu `(` , wyrażenia logicznego, zamykającego nawiasu `)` i bloku instrukcji (bloku _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="4664d-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="4664d-119">Na koniec instrukcja może opcjonalnie zakończyć z klauzulą else, która składa się ze słowa kluczowego, `else` po którym następuje inny blok instrukcji (blok _else_ ).</span><span class="sxs-lookup"><span data-stu-id="4664d-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="4664d-120">`if`Warunek jest obliczany, a jeśli ma wartość true, zostaje wykonany blok then.</span><span class="sxs-lookup"><span data-stu-id="4664d-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="4664d-121">Jeśli warunek ma wartość false, zostanie obliczony pierwszy warunek else-if; Jeśli wartość jest równa true, ten blok else-IF jest wykonywany.</span><span class="sxs-lookup"><span data-stu-id="4664d-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="4664d-122">W przeciwnym razie drugi blok else-if zostanie przetestowany, a następnie trzeci i tak dalej, dopóki nie zostanie napotkana klauzula z prawdziwym warunkiem lub nie ma żadnych klauzul else-IF.</span><span class="sxs-lookup"><span data-stu-id="4664d-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="4664d-123">Jeśli oryginalny warunek if i wszystkie klauzule else-if mają wartość false, blok else jest wykonywany, jeśli został podany.</span><span class="sxs-lookup"><span data-stu-id="4664d-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="4664d-124">Należy zauważyć, że każdy blok jest wykonywany we własnym zakresie.</span><span class="sxs-lookup"><span data-stu-id="4664d-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="4664d-125">Powiązania wykonane wewnątrz elementu `if` , `elif` lub `else` bloku nie są widoczne po jego zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="4664d-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="4664d-126">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="4664d-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="4664d-127">lub</span><span class="sxs-lookup"><span data-stu-id="4664d-127">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="4664d-128">Pętla for</span><span class="sxs-lookup"><span data-stu-id="4664d-128">For Loop</span></span>

<span data-ttu-id="4664d-129">`for`Instrukcja obsługuje iterację w zakresie liczb całkowitych lub za pośrednictwem tablicy.</span><span class="sxs-lookup"><span data-stu-id="4664d-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="4664d-130">Instrukcja składa się ze słowa kluczowego `for` , otwartego nawiasu `(` , po którym występuje krotka symbol lub symbol, słowo kluczowe `in` , wyrażenie typu `Range` lub tablicy, nawias zamykający `)` i blok instrukcji.</span><span class="sxs-lookup"><span data-stu-id="4664d-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="4664d-131">Blok instrukcji (treść pętli) jest wykonywany wielokrotnie ze zdefiniowanymi symbolami (zmienne pętli) powiązane z każdą wartością w zakresie lub tablicy.</span><span class="sxs-lookup"><span data-stu-id="4664d-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="4664d-132">Należy pamiętać, że jeśli wyrażenie zakresu szacuje pusty zakres lub tablicę, treść nie zostanie wykonana.</span><span class="sxs-lookup"><span data-stu-id="4664d-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="4664d-133">Wyrażenie jest w pełni oceniane przed wprowadzeniem pętli i nie zmienia się podczas wykonywania pętli.</span><span class="sxs-lookup"><span data-stu-id="4664d-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="4664d-134">Zmienna pętla jest powiązana z każdym wejściem do treści pętli i niezależna na końcu treści.</span><span class="sxs-lookup"><span data-stu-id="4664d-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="4664d-135">W szczególności zmienna Loop nie jest powiązana po zakończeniu pętli for.</span><span class="sxs-lookup"><span data-stu-id="4664d-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="4664d-136">Powiązanie zadeklarowanych symboli jest niezmienne i zgodne z tymi samymi regułami, co inne powiązania zmiennych.</span><span class="sxs-lookup"><span data-stu-id="4664d-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="4664d-137">W przypadku niektórych przykładów Załóżmy, że `qubits` jest to rejestr qubits (tj. typu `Qubit[]` ),</span><span class="sxs-lookup"><span data-stu-id="4664d-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
<span data-ttu-id="4664d-138">Należy pamiętać, że na końcu wykorzystujemy operator binarny z przesunięciem w lewo, `<<<` szczegóły, które można znaleźć w [wyrażeniach liczbowych](xref:microsoft.quantum.guide.expressions#numeric-expressions) .</span><span class="sxs-lookup"><span data-stu-id="4664d-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="4664d-139">Pętla REPEAT-until-Success</span><span class="sxs-lookup"><span data-stu-id="4664d-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="4664d-140">Język Q # zezwala, aby klasyczny przepływ sterowania był zależny od wyników pomiaru qubits.</span><span class="sxs-lookup"><span data-stu-id="4664d-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="4664d-141">Ta funkcja z kolei umożliwia wdrażanie zaawansowanych probabilistyczneych gadżetów, które mogą zmniejszyć koszt obliczeniowy wdrożenia unitaries.</span><span class="sxs-lookup"><span data-stu-id="4664d-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="4664d-142">Przykładowo można łatwo zaimplementować wzorce " *REPEAT-until-Success* " (jednostek ru) w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="4664d-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="4664d-143">Te wzorce jednostek ru są programami probabilistyczne, które mają *przewidywane* niskie koszty w zakresie bram elementarnych, ale dla których rzeczywisty koszt zależy od rzeczywistego przebiegu i rzeczywiste odchodzenie między różnymi możliwymi gałęziami.</span><span class="sxs-lookup"><span data-stu-id="4664d-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="4664d-144">Aby ułatwić wzorce powtarzania do sukcesu (jednostek ru), Q # obsługuje konstrukcje</span><span class="sxs-lookup"><span data-stu-id="4664d-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="4664d-145">gdzie `expression` jest dowolnym prawidłowym wyrażeniem, którego wynikiem jest wartość typu `Bool` .</span><span class="sxs-lookup"><span data-stu-id="4664d-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="4664d-146">Zostanie wykonana treść pętli, a następnie warunek jest obliczany.</span><span class="sxs-lookup"><span data-stu-id="4664d-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="4664d-147">Jeśli warunek ma wartość true, instrukcja zostanie zakończona; w przeciwnym razie nastąpi wykonanie naprawy, a instrukcja jest wykonywana ponownym uruchomieniem, rozpoczynając od treści pętli.</span><span class="sxs-lookup"><span data-stu-id="4664d-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="4664d-148">Wszystkie trzy części pętli REPEAT/until (treść, test i naprawa) są traktowane jako pojedynczy zakres *dla każdego powtórzenia*, dlatego symbole, które są powiązane z treścią, są dostępne w teście i w naprawie.</span><span class="sxs-lookup"><span data-stu-id="4664d-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="4664d-149">Jednak Kończenie wykonywania naprawy kończy zakres instrukcji, tak aby powiązania symboli wykonane podczas treści lub naprawy nie były dostępne w kolejnych powtórzeniach.</span><span class="sxs-lookup"><span data-stu-id="4664d-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="4664d-150">Ponadto `fixup` instrukcja jest często przydatna, ale nie zawsze jest konieczna.</span><span class="sxs-lookup"><span data-stu-id="4664d-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="4664d-151">W przypadkach, gdy nie jest to konieczne, konstrukcja</span><span class="sxs-lookup"><span data-stu-id="4664d-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="4664d-152">jest również prawidłowym wzorcem jednostek ru.</span><span class="sxs-lookup"><span data-stu-id="4664d-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="4664d-153">W dolnej części tej strony przedstawiamy kilka [przykładów pętli jednostek ru](#repeat-until-success-examples).</span><span class="sxs-lookup"><span data-stu-id="4664d-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="4664d-154">Unikaj używania pętli REPEAT-until-Success wewnątrz funkcji.</span><span class="sxs-lookup"><span data-stu-id="4664d-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="4664d-155">Odpowiednie funkcje są udostępniane przez pętle w funkcjach.</span><span class="sxs-lookup"><span data-stu-id="4664d-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="4664d-156">While — pętla</span><span class="sxs-lookup"><span data-stu-id="4664d-156">While Loop</span></span>

<span data-ttu-id="4664d-157">Wzorce REPEAT-until-Success mają bardzo connotation specyficzny dla Quantum.</span><span class="sxs-lookup"><span data-stu-id="4664d-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="4664d-158">Są one powszechnie używane w określonych klasach algorytmów Quantum — a tym samym — dedykowana konstrukcja języka w Q #.</span><span class="sxs-lookup"><span data-stu-id="4664d-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="4664d-159">Jednak pętle, które są przerywane w zależności od warunku, a długość wykonywania jest w tym przypadku nieznana w czasie kompilacji, muszą być obsługiwane z uwzględnieniem szczególnych informacji w środowisku uruchomieniowym Quantum.</span><span class="sxs-lookup"><span data-stu-id="4664d-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="4664d-160">Ich użycie w ramach funkcji z drugiej strony jest nieproblematyczne, ponieważ tylko zawierają kod, który będzie wykonywany na konwencjonalnym sprzęcie (innym niż Quantum).</span><span class="sxs-lookup"><span data-stu-id="4664d-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="4664d-161">W związku z tym funkcja Q # obsługuje używanie pętli while tylko wewnątrz funkcji.</span><span class="sxs-lookup"><span data-stu-id="4664d-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="4664d-162">`while`Instrukcja składa się ze słowa kluczowego `while` , otwartego nawiasu `(` , warunku (tj. wyrażenia logicznego), zamykającego nawiasu `)` i bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="4664d-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="4664d-163">Blok instrukcji (treść pętli) jest wykonywany tak długo, jak warunek jest obliczany `true` .</span><span class="sxs-lookup"><span data-stu-id="4664d-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="4664d-164">Return, instrukcja</span><span class="sxs-lookup"><span data-stu-id="4664d-164">Return Statement</span></span>

<span data-ttu-id="4664d-165">Instrukcja return kończąca wykonywanie operacji lub funkcji i zwraca wartość do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="4664d-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="4664d-166">Składa się ze słowa kluczowego `return` , po którym następuje wyrażenie odpowiedniego typu i kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="4664d-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="4664d-167">Wywoływany, który zwraca pustą krotkę, nie `()` wymaga instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="4664d-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="4664d-168">Jeśli pożądane jest wczesne wyjście, można `return ()` go użyć w tym przypadku.</span><span class="sxs-lookup"><span data-stu-id="4664d-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="4664d-169">Możliwe do zwrócenia wszystkie inne typy wymagają końcowej instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="4664d-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="4664d-170">W obrębie operacji nie ma maksymalnej liczby instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="4664d-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="4664d-171">Kompilator może emitować ostrzeżenie, jeśli instrukcje są zgodne z instrukcją Return w bloku.</span><span class="sxs-lookup"><span data-stu-id="4664d-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="4664d-172">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="4664d-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="4664d-173">lub</span><span class="sxs-lookup"><span data-stu-id="4664d-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="4664d-174">lub</span><span class="sxs-lookup"><span data-stu-id="4664d-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="4664d-175">Instrukcja zakończony niepowodzeniem</span><span class="sxs-lookup"><span data-stu-id="4664d-175">Fail Statement</span></span>

<span data-ttu-id="4664d-176">Instrukcja Fail kończy wykonywanie operacji i zwraca wartość błędu do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="4664d-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="4664d-177">Składa się ze słowa kluczowego `fail` , po którym następuje ciąg i kończący się średnik.</span><span class="sxs-lookup"><span data-stu-id="4664d-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="4664d-178">Ten ciąg jest zwracany do klasycznego sterownika jako komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="4664d-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="4664d-179">W obrębie operacji nie ma ograniczeń dotyczących liczby instrukcji zakończonych niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="4664d-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="4664d-180">Kompilator może emitować ostrzeżenie, jeśli instrukcje obserwują instrukcję Fail w bloku.</span><span class="sxs-lookup"><span data-stu-id="4664d-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="4664d-181">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="4664d-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="4664d-182">lub korzystając z [ciągów interpolowanych](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="4664d-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="4664d-183">Przykłady powtarzania do sukcesu</span><span class="sxs-lookup"><span data-stu-id="4664d-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="4664d-184">Wzorzec jednostek ru dla pojedynczego obrotu qubit o osi niewymiernej</span><span class="sxs-lookup"><span data-stu-id="4664d-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="4664d-185">W typowym przypadku użycia Następująca operacja Q # implementuje obrót wokół osi niewymiernej $ (I + 2i Z)/\sqrt {5} $ w sferze Bloch.</span><span class="sxs-lookup"><span data-stu-id="4664d-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="4664d-186">Jest to realizowane przy użyciu znanego wzorca jednostek ru:</span><span class="sxs-lookup"><span data-stu-id="4664d-186">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="4664d-187">Pętla jednostek ru z modyfikowalną zmienną w zakresie</span><span class="sxs-lookup"><span data-stu-id="4664d-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="4664d-188">Ten przykład pokazuje użycie zmiennej modyfikowalnej, `finished` która znajduje się w zakresie całej pętli REPEAT-until-Naprawa i która zostaje zainicjowana przed pętlą i zaktualizowaną w kroku naprawy.</span><span class="sxs-lookup"><span data-stu-id="4664d-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="4664d-189">JEDNOSTEK ru bez`fixup`</span><span class="sxs-lookup"><span data-stu-id="4664d-189">RUS without `fixup`</span></span>

<span data-ttu-id="4664d-190">Na przykład poniższy kod jest obwodem usługi probabilistyczne, który implementuje ważną bramę rotacji $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ przy `H` użyciu `T` bram i.</span><span class="sxs-lookup"><span data-stu-id="4664d-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="4664d-191">Pętla kończy się na wartościach $ \frac {8} {5} $.</span><span class="sxs-lookup"><span data-stu-id="4664d-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="4664d-192">Zobacz [*powtarzanie-do-sukces: Niedeterministyczny dekompozycja qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick i Svore, 2014), aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="4664d-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="4664d-193">JEDNOSTEK ru przygotowania stanu Quantum</span><span class="sxs-lookup"><span data-stu-id="4664d-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="4664d-194">Na koniec pokazujemy przykład wzorca jednostek ru, aby przygotować stan Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, rozpoczynając od stanu $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="4664d-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="4664d-195">Zobacz również [przykład testowania jednostkowego w standardowej bibliotece](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="4664d-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="4664d-196">Istotne funkcje programistyczne przedstawione w tej operacji to bardziej skomplikowana `fixup` część pętli, która obejmuje operacje Quantum i użycie `AssertProb` instrukcji w celu ustalenia prawdopodobieństwa mierzenia stanu Quantum w określonych punktach w programie.</span><span class="sxs-lookup"><span data-stu-id="4664d-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="4664d-197">Więcej informacji na temat operacji i można znaleźć w temacie [testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging) [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) .</span><span class="sxs-lookup"><span data-stu-id="4664d-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="whats-next"></a><span data-ttu-id="4664d-198">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="4664d-198">What's Next?</span></span>
<span data-ttu-id="4664d-199">Więcej informacji na temat [testowania i debugowania](xref:microsoft.quantum.guide.testingdebugging) w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="4664d-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
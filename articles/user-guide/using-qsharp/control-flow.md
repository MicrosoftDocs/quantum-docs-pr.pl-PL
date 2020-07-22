---
title: 'Przepływ sterowania w p #'
description: Pętle, warunkowe itd.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: b652736168a71b905deaf7c4fdb29a8751b3dfaf
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870995"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="ab6c5-103">Przepływ sterowania w p #</span><span class="sxs-lookup"><span data-stu-id="ab6c5-103">Control flow in Q#</span></span>

<span data-ttu-id="ab6c5-104">W ramach operacji lub funkcji każda instrukcja jest uruchamiana w kolejności, podobnie jak w przypadku innych typowych języków, których to dotyczy.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="ab6c5-105">Można jednak zmodyfikować przepływ kontroli na trzy różne sposoby:</span><span class="sxs-lookup"><span data-stu-id="ab6c5-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="ab6c5-106">`if`zatwierdzeni</span><span class="sxs-lookup"><span data-stu-id="ab6c5-106">`if` statements</span></span>
* <span data-ttu-id="ab6c5-107">`for`pętli</span><span class="sxs-lookup"><span data-stu-id="ab6c5-107">`for` loops</span></span>
* <span data-ttu-id="ab6c5-108">`repeat-until-success`pętli</span><span class="sxs-lookup"><span data-stu-id="ab6c5-108">`repeat-until-success` loops</span></span>

<span data-ttu-id="ab6c5-109">`if` `for` Konstrukcje przepływu sterowania i są realizowane w dobrze znanym znaczeniu dla większości klasycznych języków programowania.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-109">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="ab6c5-110">[`Repeat-until-success`](#repeat-until-success-loop)pętle zostały omówione w dalszej części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-110">[`Repeat-until-success`](#repeat-until-success-loop) loops are discussed later in this article.</span></span>

<span data-ttu-id="ab6c5-111">Należy pamiętać, że `for` pętle i `if` instrukcje mogą być używane w operacjach, dla których [specjalizacje](xref:microsoft.quantum.guide.operationsfunctions) są generowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-111">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="ab6c5-112">W tym scenariuszu sąsiadująca `for` Pętla odwraca kierunek i przyjmuje sąsiadujące poszczególne iteracje.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-112">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="ab6c5-113">Ta akcja jest zgodna z zasadą "buty i-SOCKS": Jeśli chcesz cofnąć umieszczenie w usłudze SOCKS, a następnie kliknij pozycję Wycofaj w odniesieniu do butów, a następnie Cofnij umieszczenie w obszarze SOCKS.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-113">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="ab6c5-114">If, Else-IF, else</span><span class="sxs-lookup"><span data-stu-id="ab6c5-114">If, Else-if, Else</span></span>

<span data-ttu-id="ab6c5-115">`if`Instrukcja obsługuje wykonywanie warunkowe.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-115">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="ab6c5-116">Składa się ze słowa kluczowego `if` , wyrażenia logicznego w nawiasach i bloku instrukcji (bloku _then_ ).</span><span class="sxs-lookup"><span data-stu-id="ab6c5-116">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="ab6c5-117">Opcjonalnie można wykonać dowolną liczbę klauzul else-IF, z których każdy składa się ze słowa kluczowego `elif` , wyrażenia logicznego w nawiasach i bloku instrukcji (bloku _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="ab6c5-117">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="ab6c5-118">Na koniec instrukcja może opcjonalnie zakończyć z klauzulą else, która składa się ze słowa kluczowego, `else` po którym następuje inny blok instrukcji (blok _else_ ).</span><span class="sxs-lookup"><span data-stu-id="ab6c5-118">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="ab6c5-119">`if`Warunek jest obliczany, a jeśli ma *wartość true*, blok *then* jest uruchamiany.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-119">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="ab6c5-120">Jeśli warunek ma *wartość false*, zostanie obliczony pierwszy warunek else-if; Jeśli ma wartość true, blok *else-if* jest uruchamiany.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-120">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="ab6c5-121">W przeciwnym razie drugi blok else-IF jest obliczany, a następnie trzeci i tak dalej, dopóki nie zostanie napotkana klauzula z prawdziwym warunkiem lub nie ma żadnych klauzul else-IF.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-121">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="ab6c5-122">Jeśli oryginalny warunek *if* i wszystkie klauzule else-if mają *wartość false*, blok *else* jest uruchamiany, jeśli jest podany.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-122">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="ab6c5-123">Należy zauważyć, że w zależności od tego, czy blokowane są uruchomienia, działa w ramach własnego zakresu.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-123">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="ab6c5-124">Powiązania wykonane wewnątrz elementu `if` , `elif` lub `else` bloku nie są widoczne po zakończeniu bloku.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-124">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="ab6c5-125">Przykład:</span><span class="sxs-lookup"><span data-stu-id="ab6c5-125">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="ab6c5-126">lub</span><span class="sxs-lookup"><span data-stu-id="ab6c5-126">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="ab6c5-127">Pętla for</span><span class="sxs-lookup"><span data-stu-id="ab6c5-127">For loop</span></span>

<span data-ttu-id="ab6c5-128">`for`Instrukcja obsługuje iterację w zakresie liczb całkowitych lub tablicy.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-128">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="ab6c5-129">Instrukcja składa się ze słowa kluczowego `for` , po którym następuje symbol lub krotka symboli, słowo kluczowe `in` i wyrażenie typu `Range` lub tablicy, wszystkie w nawiasach i bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-129">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="ab6c5-130">Blok instrukcji (treść pętli) jest uruchamiany wielokrotnie, ze zdefiniowanym symbolem (zmienna pętli) powiązaną z każdą wartością z zakresu lub tablicy.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-130">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="ab6c5-131">Należy zauważyć, że jeśli wyrażenie zakresu szacuje pusty zakres lub tablicę, treść nie jest w ogóle uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-131">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="ab6c5-132">Wyrażenie jest w pełni oceniane przed wprowadzeniem pętli i nie zmienia się w czasie wykonywania pętli.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-132">The expression is fully evaluated before entering the loop, and does not change while the loop is executing.</span></span>

<span data-ttu-id="ab6c5-133">Zmienna pętla jest powiązana z każdym wejściem do treści pętli i jest niepowiązana na końcu treści.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-133">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="ab6c5-134">Zmienna Loop nie jest powiązana po zakończeniu pętli for.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-134">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="ab6c5-135">Powiązanie zmiennej pętli jest niezmienne i jest zgodne z tymi samymi regułami, co inne powiązania zmiennych.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-135">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="ab6c5-136">W tych przykładach `qubits` jest rejestrem qubits (tj. typu `Qubit[]` ),</span><span class="sxs-lookup"><span data-stu-id="ab6c5-136">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="ab6c5-137">Należy pamiętać, że na końcu wykorzystujemy operator binarny z przesunięciem w lewo z lewej strony `<<<` .</span><span class="sxs-lookup"><span data-stu-id="ab6c5-137">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="ab6c5-138">Aby uzyskać więcej informacji, zobacz [wyrażenia liczbowe](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="ab6c5-138">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="ab6c5-139">Pętla REPEAT-until-Success</span><span class="sxs-lookup"><span data-stu-id="ab6c5-139">Repeat-until-success loop</span></span>

<span data-ttu-id="ab6c5-140">Język Q # zezwala, aby klasyczny przepływ sterowania był zależny od wyników pomiaru qubits.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="ab6c5-141">Ta funkcja z kolei umożliwia wdrażanie zaawansowanych probabilistyczneych gadżetów, które mogą zmniejszyć koszt obliczeniowy wdrożenia unitaries.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-141">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="ab6c5-142">Przykładami są wzorce *powtarzające się do sukcesu* (jednostek ru) w Q #.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-142">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="ab6c5-143">Te wzorce jednostek ru są programami probabilistyczne, które mają *przewidywane* niskie koszty w zakresie bram elementarnych; poniesiony koszt zależy od rzeczywistego przebiegu i przeplotu wielu możliwych rozgałęzień.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="ab6c5-144">Aby ułatwić wzorce powtarzania do sukcesu (jednostek ru), Q # obsługuje konstrukcje</span><span class="sxs-lookup"><span data-stu-id="ab6c5-144">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="ab6c5-145">gdzie `expression` jest dowolnym prawidłowym wyrażeniem, którego wynikiem jest wartość typu `Bool` .</span><span class="sxs-lookup"><span data-stu-id="ab6c5-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="ab6c5-146">Zostanie uruchomiona pętla, a następnie warunek jest obliczany.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-146">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="ab6c5-147">Jeśli warunek ma wartość true, instrukcja zostanie zakończona; w przeciwnym razie przebiega naprawy i instrukcja zostanie ponownie uruchomiona, rozpoczynając od treści pętli.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-147">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="ab6c5-148">Wszystkie trzy części pętli jednostek ru (treść, test i naprawa) są traktowane jako pojedynczy zakres *dla każdego powtórzenia*, dlatego symbole, które są powiązane w treści są dostępne zarówno w teście, jak i w naprawie.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-148">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="ab6c5-149">Jednak wykonanie naprawy kończy zakres instrukcji, tak aby powiązania symboli wykonane w trakcie treści lub naprawy nie były dostępne w kolejnych powtórzeniach.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-149">However, completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="ab6c5-150">Ponadto `fixup` instrukcja jest często przydatna, ale nie zawsze jest konieczna.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="ab6c5-151">W przypadkach, gdy nie jest to konieczne, konstrukcja</span><span class="sxs-lookup"><span data-stu-id="ab6c5-151">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="ab6c5-152">jest również prawidłowym wzorcem jednostek ru.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="ab6c5-153">Aby uzyskać więcej przykładów i szczegółów, zobacz [przykłady powtarzania do sukcesu](#repeat-until-success-examples) w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-153">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="ab6c5-154">Unikaj używania pętli REPEAT-until-Success wewnątrz funkcji.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="ab6c5-155">Użyj *while* pętle, aby zapewnić odpowiednie funkcje wewnątrz funkcji.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-155">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="ab6c5-156">While — pętla</span><span class="sxs-lookup"><span data-stu-id="ab6c5-156">While loop</span></span>

<span data-ttu-id="ab6c5-157">Wzorce REPEAT-until-Success mają bardzo connotation specyficzny dla Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="ab6c5-158">Są one powszechnie używane w określonych klasach algorytmów Quantum — dlatego też dedykowana konstrukcja języka w Q #.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-158">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="ab6c5-159">Jednak pętle, które są przerywane w zależności od warunku, a długość wykonywania jest w tym przypadku nieznana w czasie kompilacji, są obsługiwane z uwzględnieniem szczególnej opieki w środowisku uruchomieniowym Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-159">However, loops that break based on a condition and whose execution length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="ab6c5-160">Jednak ich użycie w funkcjach nie działa, ponieważ pętle zawierają tylko kod, który jest uruchamiany na sprzęcie konwencjonalnym (innym niż Quantum).</span><span class="sxs-lookup"><span data-stu-id="ab6c5-160">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="ab6c5-161">W związku z tym funkcja Q # obsługuje używanie pętli while tylko w obrębie funkcji.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-161">Q#, therefore, supports to use of while loops within functions only.</span></span> <span data-ttu-id="ab6c5-162">`while`Instrukcja składa się z słowa kluczowego `while` , wyrażenia logicznego w nawiasach i bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-162">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="ab6c5-163">Blok instrukcji (treść pętli) działa tak długo, jak warunek zostanie obliczony `true` .</span><span class="sxs-lookup"><span data-stu-id="ab6c5-163">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a><span data-ttu-id="ab6c5-164">Return, instrukcja</span><span class="sxs-lookup"><span data-stu-id="ab6c5-164">Return Statement</span></span>

<span data-ttu-id="ab6c5-165">Instrukcja return zamyka przebieg operacji lub funkcji i zwraca wartość do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-165">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="ab6c5-166">Składa się ze słowa kluczowego `return` , po którym następuje wyrażenie odpowiedniego typu i kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="ab6c5-167">Przykład:</span><span class="sxs-lookup"><span data-stu-id="ab6c5-167">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="ab6c5-168">lub</span><span class="sxs-lookup"><span data-stu-id="ab6c5-168">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="ab6c5-169">Wywoływany, który zwraca pustą krotkę, nie `()` wymaga instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-169">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="ab6c5-170">Aby określić wczesne wyjście z operacji lub funkcji, użyj polecenia `return ();` .</span><span class="sxs-lookup"><span data-stu-id="ab6c5-170">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="ab6c5-171">Możliwe do zwrócenia wszystkie inne typy wymagają końcowej instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-171">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="ab6c5-172">W obrębie operacji nie ma maksymalnej liczby instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-172">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="ab6c5-173">Kompilator może emitować ostrzeżenie, jeśli instrukcje są zgodne z instrukcją Return w bloku.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-173">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="ab6c5-174">Instrukcja zakończony niepowodzeniem</span><span class="sxs-lookup"><span data-stu-id="ab6c5-174">Fail statement</span></span>

<span data-ttu-id="ab6c5-175">Instrukcja Fail kończy wykonywanie operacji i zwraca wartość błędu do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-175">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="ab6c5-176">Składa się ze słowa kluczowego `fail` , po którym następuje ciąg i kończący się średnik.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-176">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="ab6c5-177">Instrukcja zwraca ciąg do klasycznego sterownika jako komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-177">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="ab6c5-178">W obrębie operacji nie ma ograniczeń dotyczących liczby instrukcji zakończonych niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-178">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="ab6c5-179">Kompilator może emitować ostrzeżenie, jeśli instrukcje obserwują instrukcję Fail w bloku.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-179">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="ab6c5-180">Przykład:</span><span class="sxs-lookup"><span data-stu-id="ab6c5-180">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="ab6c5-181">lub korzystając z [ciągów interpolowanych](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="ab6c5-181">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="ab6c5-182">Przykłady powtarzania do sukcesu</span><span class="sxs-lookup"><span data-stu-id="ab6c5-182">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="ab6c5-183">Wzorzec jednostek ru dla obrotu pojedynczej qubit o osi niewymiernej</span><span class="sxs-lookup"><span data-stu-id="ab6c5-183">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="ab6c5-184">W typowym przypadku użycia Następująca operacja Q # implementuje obrót wokół osi niewymiernej $ (I + 2i Z)/\sqrt {5} $ w sferze Bloch.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-184">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="ab6c5-185">Implementacja używa znanego wzorca jednostek ru:</span><span class="sxs-lookup"><span data-stu-id="ab6c5-185">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="ab6c5-186">Pętla jednostek ru z zmienną modyfikowalną w zakresie</span><span class="sxs-lookup"><span data-stu-id="ab6c5-186">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="ab6c5-187">Ten przykład pokazuje użycie zmiennej modyfikowalnej, `finished` która znajduje się w zakresie całej pętli REPEAT-until-Naprawa i która zostaje zainicjowana przed pętlą i zaktualizowaną w kroku naprawy.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-187">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="ab6c5-188">JEDNOSTEK ru bez`fixup`</span><span class="sxs-lookup"><span data-stu-id="ab6c5-188">RUS without `fixup`</span></span>

<span data-ttu-id="ab6c5-189">Ten przykład pokazuje pętlę jednostek ru bez kroku naprawy.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-189">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="ab6c5-190">Kod jest obwodem usługi probabilistyczne, który implementuje ważną bramę rotacji $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ przy użyciu `H` `T` bram i.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-190">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="ab6c5-191">Pętla kończy się na wartościach $ \frac {8} {5} $.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="ab6c5-192">Zobacz [*powtarzanie-do-sukces: Niedeterministyczny dekompozycja qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick i Svore, 2014), aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="ab6c5-193">JEDNOSTEK ru przygotowania stanu Quantum</span><span class="sxs-lookup"><span data-stu-id="ab6c5-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="ab6c5-194">Na koniec przedstawiono przykład wzorca jednostek ru, aby przygotować stan Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, rozpoczynając od stanu $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-194">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="ab6c5-195">Istotne funkcje programistyczne wyświetlane w tej operacji to:</span><span class="sxs-lookup"><span data-stu-id="ab6c5-195">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="ab6c5-196">Bardziej złożona `fixup` część pętli, która obejmuje operacje Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-196">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="ab6c5-197">Użycie `AssertMeasurementProbability` instrukcji w celu ustalenia prawdopodobieństwa mierzenia stanu Quantum w określonych punktach w programie.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-197">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="ab6c5-198">Aby uzyskać więcej informacji na [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) temat [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operacji i, zobacz [testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="ab6c5-198">For more information about the [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

<span data-ttu-id="ab6c5-199">Aby uzyskać więcej informacji, zobacz [przykładowe testy jednostkowe dostępne w bibliotece standardowej](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="ab6c5-199">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="ab6c5-200">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="ab6c5-200">Next steps</span></span>

<span data-ttu-id="ab6c5-201">Więcej informacji na temat [testowania i debugowania](xref:microsoft.quantum.guide.testingdebugging) w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="ab6c5-201">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>

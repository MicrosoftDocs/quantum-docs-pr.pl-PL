---
title: 'Przepływ sterowania w Q#'
description: Pętle, warunkowe itd.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: eca37202e5fe9b48dcfdec4eeb4ba6cafaac8723
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691088"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="c9893-103">Przepływ sterowania w Q#</span><span class="sxs-lookup"><span data-stu-id="c9893-103">Control flow in Q#</span></span>

<span data-ttu-id="c9893-104">W ramach operacji lub funkcji każda instrukcja jest uruchamiana w kolejności, podobnie jak w przypadku innych typowych języków, których to dotyczy.</span><span class="sxs-lookup"><span data-stu-id="c9893-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="c9893-105">Można jednak zmodyfikować przepływ kontroli na trzy różne sposoby:</span><span class="sxs-lookup"><span data-stu-id="c9893-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="c9893-106">`if` zatwierdzeni</span><span class="sxs-lookup"><span data-stu-id="c9893-106">`if` statements</span></span>
* <span data-ttu-id="c9893-107">`for` pętli</span><span class="sxs-lookup"><span data-stu-id="c9893-107">`for` loops</span></span>
* <span data-ttu-id="c9893-108">`repeat-until-success` pętli</span><span class="sxs-lookup"><span data-stu-id="c9893-108">`repeat-until-success` loops</span></span>
* <span data-ttu-id="c9893-109">liczby sprzężone ( `apply-within` instrukcje)</span><span class="sxs-lookup"><span data-stu-id="c9893-109">conjugations (`apply-within` statements)</span></span>

<span data-ttu-id="c9893-110">`if` `for` Konstrukcje przepływu sterowania i są realizowane w dobrze znanym znaczeniu dla większości klasycznych języków programowania.</span><span class="sxs-lookup"><span data-stu-id="c9893-110">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="c9893-111">[`Repeat-until-success`](#repeat-until-success-loop) pętle i [sprzężenia](#conjugations) zostały omówione w dalszej części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="c9893-111">[`Repeat-until-success`](#repeat-until-success-loop) loops and [conjugations](#conjugations) are discussed later in this article.</span></span>

<span data-ttu-id="c9893-112">Należy pamiętać, że `for` pętle i `if` instrukcje mogą być używane w operacjach, dla których [specjalizacje](xref:microsoft.quantum.guide.operationsfunctions) są generowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="c9893-112">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="c9893-113">W tym scenariuszu sąsiadująca `for` Pętla odwraca kierunek i przyjmuje sąsiadujące poszczególne iteracje.</span><span class="sxs-lookup"><span data-stu-id="c9893-113">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="c9893-114">Ta akcja jest zgodna z zasadą "buty i-SOCKS": Jeśli chcesz cofnąć umieszczenie w usłudze SOCKS, a następnie kliknij pozycję Wycofaj w odniesieniu do butów, a następnie Cofnij umieszczenie w obszarze SOCKS.</span><span class="sxs-lookup"><span data-stu-id="c9893-114">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="c9893-115">If, Else-IF, else</span><span class="sxs-lookup"><span data-stu-id="c9893-115">If, Else-if, Else</span></span>

<span data-ttu-id="c9893-116">`if`Instrukcja obsługuje przetwarzanie warunkowe.</span><span class="sxs-lookup"><span data-stu-id="c9893-116">The `if` statement supports conditional processing.</span></span>
<span data-ttu-id="c9893-117">Składa się ze słowa kluczowego `if` , wyrażenia logicznego w nawiasach i bloku instrukcji (bloku _then_ ).</span><span class="sxs-lookup"><span data-stu-id="c9893-117">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="c9893-118">Opcjonalnie można wykonać dowolną liczbę klauzul else-IF, z których każdy składa się ze słowa kluczowego `elif` , wyrażenia logicznego w nawiasach i bloku instrukcji (bloku _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="c9893-118">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="c9893-119">Na koniec instrukcja może opcjonalnie zakończyć z klauzulą else, która składa się ze słowa kluczowego, `else` po którym następuje inny blok instrukcji (blok _else_ ).</span><span class="sxs-lookup"><span data-stu-id="c9893-119">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="c9893-120">`if`Warunek jest obliczany, a jeśli ma *wartość true* , blok *then* jest uruchamiany.</span><span class="sxs-lookup"><span data-stu-id="c9893-120">The `if` condition is evaluated, and if it is *true* , the *then* block is run.</span></span>
<span data-ttu-id="c9893-121">Jeśli warunek ma *wartość false* , zostanie obliczony pierwszy warunek else-if; Jeśli ma wartość true, blok *else-if* jest uruchamiany.</span><span class="sxs-lookup"><span data-stu-id="c9893-121">If the condition is *false* , then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="c9893-122">W przeciwnym razie drugi blok else-IF jest obliczany, a następnie trzeci i tak dalej, dopóki nie zostanie napotkana klauzula z prawdziwym warunkiem lub nie ma żadnych klauzul else-IF.</span><span class="sxs-lookup"><span data-stu-id="c9893-122">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="c9893-123">Jeśli oryginalny warunek *if* i wszystkie klauzule else-if mają *wartość false* , blok *else* jest uruchamiany, jeśli jest podany.</span><span class="sxs-lookup"><span data-stu-id="c9893-123">If the original *if* condition and all the else-if clauses evaluate to *false* , the *else* block is run, if provided.</span></span>

<span data-ttu-id="c9893-124">Należy zauważyć, że w zależności od tego, czy blokowane są uruchomienia, działa w ramach własnego zakresu.</span><span class="sxs-lookup"><span data-stu-id="c9893-124">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="c9893-125">Powiązania wykonane wewnątrz elementu `if` , `elif` lub `else` bloku nie są widoczne po zakończeniu bloku.</span><span class="sxs-lookup"><span data-stu-id="c9893-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="c9893-126">Przykład:</span><span class="sxs-lookup"><span data-stu-id="c9893-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="c9893-127">lub</span><span class="sxs-lookup"><span data-stu-id="c9893-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="c9893-128">Pętla for</span><span class="sxs-lookup"><span data-stu-id="c9893-128">For loop</span></span>

<span data-ttu-id="c9893-129">`for`Instrukcja obsługuje iterację w zakresie liczb całkowitych lub tablicy.</span><span class="sxs-lookup"><span data-stu-id="c9893-129">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="c9893-130">Instrukcja składa się ze słowa kluczowego `for` , po którym następuje symbol lub krotka symboli, słowo kluczowe `in` i wyrażenie typu `Range` lub tablicy, wszystkie w nawiasach i bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c9893-130">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="c9893-131">Blok instrukcji (treść pętli) jest uruchamiany wielokrotnie, ze zdefiniowanym symbolem (zmienna pętli) powiązaną z każdą wartością z zakresu lub tablicy.</span><span class="sxs-lookup"><span data-stu-id="c9893-131">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="c9893-132">Należy zauważyć, że jeśli wyrażenie zakresu szacuje pusty zakres lub tablicę, treść nie jest w ogóle uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="c9893-132">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="c9893-133">Wyrażenie jest w pełni oceniane przed wprowadzeniem pętli i nie zmienia się, gdy pętla jest uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="c9893-133">The expression is fully evaluated before entering the loop, and does not change while the loop is running.</span></span>

<span data-ttu-id="c9893-134">Zmienna pętla jest powiązana z każdym wejściem do treści pętli i jest niepowiązana na końcu treści.</span><span class="sxs-lookup"><span data-stu-id="c9893-134">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="c9893-135">Zmienna Loop nie jest powiązana po zakończeniu pętli for.</span><span class="sxs-lookup"><span data-stu-id="c9893-135">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="c9893-136">Powiązanie zmiennej pętli jest niezmienne i jest zgodne z tymi samymi regułami, co inne powiązania zmiennych.</span><span class="sxs-lookup"><span data-stu-id="c9893-136">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="c9893-137">W tych przykładach `qubits` jest rejestrem qubits (tj. typu `Qubit[]` ),</span><span class="sxs-lookup"><span data-stu-id="c9893-137">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="c9893-138">Należy pamiętać, że na końcu wykorzystujemy operator binarny z przesunięciem w lewo z lewej strony `<<<` .</span><span class="sxs-lookup"><span data-stu-id="c9893-138">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="c9893-139">Aby uzyskać więcej informacji, zobacz [wyrażenia liczbowe](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="c9893-139">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="c9893-140">Pętla REPEAT-until-Success</span><span class="sxs-lookup"><span data-stu-id="c9893-140">Repeat-until-success loop</span></span>

<span data-ttu-id="c9893-141">Q#Język pozwala, aby klasyczny przepływ sterowania był zależny od wyników pomiaru qubits.</span><span class="sxs-lookup"><span data-stu-id="c9893-141">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="c9893-142">Ta funkcja z kolei umożliwia wdrażanie zaawansowanych probabilistyczneych gadżetów, które mogą zmniejszyć koszt obliczeniowy wdrożenia unitaries.</span><span class="sxs-lookup"><span data-stu-id="c9893-142">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="c9893-143">Przykładami są wzorce *powtarzania do sukcesu* (jednostek ru) w programie Q# .</span><span class="sxs-lookup"><span data-stu-id="c9893-143">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="c9893-144">Te wzorce jednostek ru są programami probabilistyczne, które mają *przewidywane* niskie koszty w zakresie bram elementarnych; poniesiony koszt zależy od rzeczywistego przebiegu i przeplotu wielu możliwych rozgałęzień.</span><span class="sxs-lookup"><span data-stu-id="c9893-144">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="c9893-145">Aby ułatwić wzorce powtarzania do sukcesu (jednostek ru), Q# obsługuje konstrukcje</span><span class="sxs-lookup"><span data-stu-id="c9893-145">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="c9893-146">gdzie `expression` jest dowolnym prawidłowym wyrażeniem, którego wynikiem jest wartość typu `Bool` .</span><span class="sxs-lookup"><span data-stu-id="c9893-146">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="c9893-147">Zostanie uruchomiona pętla, a następnie warunek jest obliczany.</span><span class="sxs-lookup"><span data-stu-id="c9893-147">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="c9893-148">Jeśli warunek ma wartość true, instrukcja zostanie zakończona; w przeciwnym razie przebiega naprawy i instrukcja zostanie ponownie uruchomiona, rozpoczynając od treści pętli.</span><span class="sxs-lookup"><span data-stu-id="c9893-148">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="c9893-149">Wszystkie trzy części pętli jednostek ru (treść, test i naprawa) są traktowane jako pojedynczy zakres *dla każdego powtórzenia* , dlatego symbole, które są powiązane w treści są dostępne zarówno w teście, jak i w naprawie.</span><span class="sxs-lookup"><span data-stu-id="c9893-149">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition* , so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="c9893-150">Jednak ukończenie przebiegu naprawy kończy zakres instrukcji, tak aby powiązania symboli wykonane podczas treści lub naprawy nie były dostępne w kolejnych powtórzeniach.</span><span class="sxs-lookup"><span data-stu-id="c9893-150">However, completing the run of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="c9893-151">Ponadto `fixup` instrukcja jest często przydatna, ale nie zawsze jest konieczna.</span><span class="sxs-lookup"><span data-stu-id="c9893-151">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="c9893-152">W przypadkach, gdy nie jest to konieczne, konstrukcja</span><span class="sxs-lookup"><span data-stu-id="c9893-152">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="c9893-153">jest również prawidłowym wzorcem jednostek ru.</span><span class="sxs-lookup"><span data-stu-id="c9893-153">is also a valid RUS pattern.</span></span>

<span data-ttu-id="c9893-154">Aby uzyskać więcej przykładów i szczegółów, zobacz [przykłady powtarzania do sukcesu](#repeat-until-success-examples) w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="c9893-154">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="c9893-155">Unikaj używania pętli REPEAT-until-Success wewnątrz funkcji.</span><span class="sxs-lookup"><span data-stu-id="c9893-155">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="c9893-156">Użyj *while* pętle, aby zapewnić odpowiednie funkcje wewnątrz funkcji.</span><span class="sxs-lookup"><span data-stu-id="c9893-156">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="c9893-157">Pętla while</span><span class="sxs-lookup"><span data-stu-id="c9893-157">While loop</span></span>

<span data-ttu-id="c9893-158">Wzorce REPEAT-until-Success mają bardzo connotation specyficzny dla Quantum.</span><span class="sxs-lookup"><span data-stu-id="c9893-158">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="c9893-159">Są one powszechnie używane w określonych klasach algorytmów Quantum — dlatego w przypadku dedykowanego języka konstrukcja w Q# .</span><span class="sxs-lookup"><span data-stu-id="c9893-159">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="c9893-160">Jednak pętle, które są przerywane w zależności od stanu i długość przebiegu są nieznane w czasie kompilacji, są obsługiwane z szczególnym uwzględnieniem w środowisku uruchomieniowym Quantum.</span><span class="sxs-lookup"><span data-stu-id="c9893-160">However, loops that break based on a condition and whose run length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="c9893-161">Jednak ich użycie w funkcjach nie działa, ponieważ pętle zawierają tylko kod, który jest uruchamiany na sprzęcie konwencjonalnym (innym niż Quantum).</span><span class="sxs-lookup"><span data-stu-id="c9893-161">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="c9893-162">Q#w związku z tym obsługuje używanie pętli while tylko w obrębie funkcji.</span><span class="sxs-lookup"><span data-stu-id="c9893-162">Q#, therefore, supports to use of while loops within functions only.</span></span>
<span data-ttu-id="c9893-163">`while`Instrukcja składa się z słowa kluczowego `while` , wyrażenia logicznego w nawiasach i bloku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c9893-163">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="c9893-164">Blok instrukcji (treść pętli) działa tak długo, jak warunek zostanie obliczony `true` .</span><span class="sxs-lookup"><span data-stu-id="c9893-164">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a><span data-ttu-id="c9893-165">Liczby sprzężone</span><span class="sxs-lookup"><span data-stu-id="c9893-165">Conjugations</span></span>

<span data-ttu-id="c9893-166">W przeciwieństwie do klasycznych bitów zwalnianie pamięci Quantum jest nieco bardziej zamierzone, ponieważ niequbitse Resetowanie może mieć niepożądane skutki dla pozostałych obliczeń, jeśli qubits nadal Entangled.</span><span class="sxs-lookup"><span data-stu-id="c9893-166">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="c9893-167">Te efekty można uniknąć przez prawidłowe wykonanie obliczeń przed przystąpieniem do zwolnienia pamięci.</span><span class="sxs-lookup"><span data-stu-id="c9893-167">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="c9893-168">Typowym wzorcem przetwarzania Quantum jest następujące:</span><span class="sxs-lookup"><span data-stu-id="c9893-168">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="c9893-169">Q# obsługuje instrukcję sprzężenia implementującą poprzednią transformację.</span><span class="sxs-lookup"><span data-stu-id="c9893-169">Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="c9893-170">Korzystając z tej instrukcji, `ApplyWith` można zaimplementować operację w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c9893-170">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="c9893-171">Taka instrukcja sprzężona jest przydatna, jeśli zewnętrzne i wewnętrzne przekształcenia nie są łatwo dostępne jako operacje, ale są bardziej wygodne do opisania przez blok składający się z kilku instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c9893-171">Such a conjugation statement becomes useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="c9893-172">Przekształcenie odwrotne dla instrukcji zdefiniowanych w bloku jest automatycznie generowane przez kompilator i uruchamiane po zakończeniu zastosowania instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c9893-172">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="c9893-173">Ponieważ żadne zmienne modyfikowalne używane jako część wewnątrz bloku nie mogą być ponownie powiązane w bloku Apply, wygenerowane przekształcenie jest gwarantowane jako sąsiadujące obliczenie w bloku.</span><span class="sxs-lookup"><span data-stu-id="c9893-173">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="return-statement"></a><span data-ttu-id="c9893-174">Return, instrukcja</span><span class="sxs-lookup"><span data-stu-id="c9893-174">Return Statement</span></span>

<span data-ttu-id="c9893-175">Instrukcja return zamyka przebieg operacji lub funkcji i zwraca wartość do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="c9893-175">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="c9893-176">Składa się ze słowa kluczowego `return` , po którym następuje wyrażenie odpowiedniego typu i kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="c9893-176">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="c9893-177">Przykład:</span><span class="sxs-lookup"><span data-stu-id="c9893-177">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="c9893-178">lub</span><span class="sxs-lookup"><span data-stu-id="c9893-178">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="c9893-179">Wywoływany, który zwraca pustą krotkę, nie `()` wymaga instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="c9893-179">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="c9893-180">Aby określić wczesne wyjście z operacji lub funkcji, użyj polecenia `return ();` .</span><span class="sxs-lookup"><span data-stu-id="c9893-180">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="c9893-181">Możliwe do zwrócenia wszystkie inne typy wymagają końcowej instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="c9893-181">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="c9893-182">W obrębie operacji nie ma maksymalnej liczby instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="c9893-182">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="c9893-183">Kompilator może emitować ostrzeżenie, jeśli instrukcje są zgodne z instrukcją Return w bloku.</span><span class="sxs-lookup"><span data-stu-id="c9893-183">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="c9893-184">Instrukcja zakończony niepowodzeniem</span><span class="sxs-lookup"><span data-stu-id="c9893-184">Fail statement</span></span>

<span data-ttu-id="c9893-185">Instrukcja Fail kończy wykonywanie operacji i zwraca wartość błędu do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="c9893-185">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="c9893-186">Składa się ze słowa kluczowego `fail` , po którym następuje ciąg i kończący się średnik.</span><span class="sxs-lookup"><span data-stu-id="c9893-186">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="c9893-187">Instrukcja zwraca ciąg do klasycznego sterownika jako komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="c9893-187">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="c9893-188">W obrębie operacji nie ma ograniczeń dotyczących liczby instrukcji zakończonych niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="c9893-188">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="c9893-189">Kompilator może emitować ostrzeżenie, jeśli instrukcje obserwują instrukcję Fail w bloku.</span><span class="sxs-lookup"><span data-stu-id="c9893-189">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="c9893-190">Przykład:</span><span class="sxs-lookup"><span data-stu-id="c9893-190">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="c9893-191">lub korzystając z [ciągów interpolowanych](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="c9893-191">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="c9893-192">Przykłady powtarzania do sukcesu</span><span class="sxs-lookup"><span data-stu-id="c9893-192">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="c9893-193">Wzorzec jednostek ru dla obrotu pojedynczej qubit o osi niewymiernej</span><span class="sxs-lookup"><span data-stu-id="c9893-193">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="c9893-194">W typowym przypadku użycia następująca Q# operacja implementuje obrót wokół osi niewymiernej $ (I + 2i z)/\sqrt {5} $ w sferze Bloch.</span><span class="sxs-lookup"><span data-stu-id="c9893-194">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="c9893-195">Implementacja używa znanego wzorca jednostek ru:</span><span class="sxs-lookup"><span data-stu-id="c9893-195">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="c9893-196">Pętla jednostek ru z zmienną modyfikowalną w zakresie</span><span class="sxs-lookup"><span data-stu-id="c9893-196">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="c9893-197">Ten przykład pokazuje użycie zmiennej modyfikowalnej, `finished` która znajduje się w zakresie całej pętli REPEAT-until-Naprawa i która zostaje zainicjowana przed pętlą i zaktualizowaną w kroku naprawy.</span><span class="sxs-lookup"><span data-stu-id="c9893-197">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="c9893-198">JEDNOSTEK ru bez `fixup`</span><span class="sxs-lookup"><span data-stu-id="c9893-198">RUS without `fixup`</span></span>

<span data-ttu-id="c9893-199">Ten przykład pokazuje pętlę jednostek ru bez kroku naprawy.</span><span class="sxs-lookup"><span data-stu-id="c9893-199">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="c9893-200">Kod jest obwodem usługi probabilistyczne, który implementuje ważną bramę rotacji $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ przy użyciu `H` `T` bram i.</span><span class="sxs-lookup"><span data-stu-id="c9893-200">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="c9893-201">Pętla kończy się na wartościach $ \frac {8} {5} $.</span><span class="sxs-lookup"><span data-stu-id="c9893-201">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="c9893-202">Zobacz [*powtarzanie-do-sukces: Niedeterministyczny dekompozycja qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick i Svore, 2014), aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="c9893-202">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="c9893-203">JEDNOSTEK ru przygotowania stanu Quantum</span><span class="sxs-lookup"><span data-stu-id="c9893-203">RUS to prepare a quantum state</span></span>

<span data-ttu-id="c9893-204">Na koniec przedstawiono przykład wzorca jednostek ru, aby przygotować stan Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, rozpoczynając od stanu $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="c9893-204">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="c9893-205">Istotne funkcje programistyczne wyświetlane w tej operacji to:</span><span class="sxs-lookup"><span data-stu-id="c9893-205">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="c9893-206">Bardziej złożona `fixup` część pętli, która obejmuje operacje Quantum.</span><span class="sxs-lookup"><span data-stu-id="c9893-206">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="c9893-207">Użycie `AssertMeasurementProbability` instrukcji w celu ustalenia prawdopodobieństwa mierzenia stanu Quantum w określonych punktach w programie.</span><span class="sxs-lookup"><span data-stu-id="c9893-207">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="c9893-208">Aby uzyskać więcej informacji na [`AssertMeasurement`](xref:Microsoft.Quantum.Diagnostics.assertmeasurement) temat [`AssertMeasurementProbability`](xref:Microsoft.Quantum.Diagnostics.assertmeasurementprobability) operacji i, zobacz [testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="c9893-208">For more information about the [`AssertMeasurement`](xref:Microsoft.Quantum.Diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:Microsoft.Quantum.Diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

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

<span data-ttu-id="c9893-209">Aby uzyskać więcej informacji, zobacz [przykładowe testy jednostkowe dostępne w bibliotece standardowej](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="c9893-209">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9893-210">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="c9893-210">Next steps</span></span>

<span data-ttu-id="c9893-211">Więcej informacji na temat [testowania i debugowania](xref:microsoft.quantum.guide.testingdebugging) w programie Q# .</span><span class="sxs-lookup"><span data-stu-id="c9893-211">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>

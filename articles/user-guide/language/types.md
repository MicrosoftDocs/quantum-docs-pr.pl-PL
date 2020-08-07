---
title: Typy wQ#
description: Dowiedz się więcej na temat różnych typów używanych w Q# języku programowania.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: b034af0b1d3b967b5680403341813407e4412f93
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869600"
---
# <a name="types-in-no-locq"></a><span data-ttu-id="35d21-103">Typy wQ#</span><span class="sxs-lookup"><span data-stu-id="35d21-103">Types in Q#</span></span>

<span data-ttu-id="35d21-104">W tym artykule opisano Q# model typu i składnię służącą do określania typów i pracy z tymi typami.</span><span class="sxs-lookup"><span data-stu-id="35d21-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="35d21-105">Aby uzyskać szczegółowe informacje na temat sposobu tworzenia i obsługi wyrażeń tych typów, zobacz [wyrażenia typu](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="35d21-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="35d21-106">Należy pamiętać, że Q# jest *strongly-typed* to wulgarny język, w taki sposób, że staranne korzystanie z tych typów może pomóc kompilatorowi zapewnić silne gwarancje dotyczące Q# programów w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="35d21-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="35d21-107">Aby zapewnić najmocniejsze gwarancje, konwersje między typami w Q# muszą być jawne przy użyciu wywołań do funkcji, które wyrażają tę konwersję.</span><span class="sxs-lookup"><span data-stu-id="35d21-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> 
<span data-ttu-id="35d21-108">Q#oferuje różne funkcje, które są częścią <xref:microsoft.quantum.convert> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="35d21-108">Q# provides a variety of such functions as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="35d21-109">Przerzuty do zgodnych typów, z drugiej strony, nastąpią niejawnie.</span><span class="sxs-lookup"><span data-stu-id="35d21-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="35d21-110">Q#zawiera typy pierwotne, które są używane bezpośrednio, i różne sposoby tworzenia nowych typów z innych typów.</span><span class="sxs-lookup"><span data-stu-id="35d21-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="35d21-111">Opiszemy każdą z nich w dalszej części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="35d21-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="35d21-112">Typy pierwotne</span><span class="sxs-lookup"><span data-stu-id="35d21-112">Primitive Types</span></span>

<span data-ttu-id="35d21-113">Q#Język zawiera następujące *typy pierwotne*, z których można korzystać bezpośrednio w Q# programach.</span><span class="sxs-lookup"><span data-stu-id="35d21-113">The Q# language provides the following *primitive types*, all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="35d21-114">Można również użyć tych typów pierwotnych do konstruowania nowych typów.</span><span class="sxs-lookup"><span data-stu-id="35d21-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="35d21-115">`Int`Typ reprezentuje 64-bitową liczbę całkowitą ze znakiem, na przykład,, `2` `107` `-5` .</span><span class="sxs-lookup"><span data-stu-id="35d21-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="35d21-116">`BigInt`Typ reprezentuje podpisaną liczbę całkowitą z dowolnego rozmiaru, na przykład, `2L` , `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="35d21-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="35d21-117">Ten typ jest oparty na platformie .NET<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="35d21-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="35d21-118">Wprowadź.</span><span class="sxs-lookup"><span data-stu-id="35d21-118">type.</span></span>

- <span data-ttu-id="35d21-119">`Double`Typ reprezentuje liczbę zmiennoprzecinkową o podwójnej precyzji, na przykład,, `0.0` `-1.3` `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="35d21-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="35d21-120">`Bool`Typ reprezentuje wartość logiczną albo `true` lub `false` .</span><span class="sxs-lookup"><span data-stu-id="35d21-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="35d21-121">`Range`Typ reprezentuje sekwencję liczb całkowitych, oznaczaną przez `start..step..stop` , gdzie oznacza to, że ten krok jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="35d21-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="35d21-122">Na przykład `start .. stop` odpowiada `start..1..stop` , i `1..2..7` reprezentuje sekwencję $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="35d21-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="35d21-123">`String`Typ jest sekwencją znaków Unicode, które są nieprzezroczyste dla użytkownika po utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="35d21-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="35d21-124">Użyj `string` typu, aby zgłosić komunikaty do klasycznego hosta w przypadku błędu lub zdarzenia diagnostycznego.</span><span class="sxs-lookup"><span data-stu-id="35d21-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="35d21-125">`Unit`Typ może mieć tylko jedną wartość, `()` .</span><span class="sxs-lookup"><span data-stu-id="35d21-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="35d21-126">Użyj tego typu, aby wskazać, że Q# Funkcja lub operacja nie zwraca żadnych informacji.</span><span class="sxs-lookup"><span data-stu-id="35d21-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="35d21-127">`Qubit`Typ reprezentuje bit Quantum lub qubit.</span><span class="sxs-lookup"><span data-stu-id="35d21-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="35d21-128">`Qubit`s nie jest nieprzezroczysty dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="35d21-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="35d21-129">Jedyną operacją dopuszczalną dla nich, inną niż przekazanie jej do innej operacji, jest przetestowanie pod kątem tożsamości (równość).</span><span class="sxs-lookup"><span data-stu-id="35d21-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="35d21-130">Ostatecznie wdrażasz akcje na `Qubit` s, wywołując instrukcje wewnętrzne na procesorach Quantum (lub w symulatorze Quantum).</span><span class="sxs-lookup"><span data-stu-id="35d21-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="35d21-131">`Pauli`Typ reprezentuje jeden z czterech operatorów Pauli pojedynczej qubit.</span><span class="sxs-lookup"><span data-stu-id="35d21-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="35d21-132">Użyj tego typu, aby zauważyć podstawową operację dla rotacji i określić zauważalny pomiar.</span><span class="sxs-lookup"><span data-stu-id="35d21-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="35d21-133">Jest to typ wyliczeniowy, który ma cztery możliwe wartości: `PauliI` , `PauliX` , `PauliY` , i `PauliZ` , które są stałymi typu `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="35d21-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="35d21-134">`Result`Typ reprezentuje wynik pomiaru.</span><span class="sxs-lookup"><span data-stu-id="35d21-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="35d21-135">Jest to typ wyliczeniowy z dwoma możliwymi wartościami: `One` i `Zero` , które są stałymi typu `Result` .</span><span class="sxs-lookup"><span data-stu-id="35d21-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="35d21-136">`Zero`wskazuje, że eigenvalue + 1 została zmierzona; `One`wskazuje, że eigenvalue — 1.</span><span class="sxs-lookup"><span data-stu-id="35d21-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="35d21-137">Stałe,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` i `Zero` są zastrzeżonymi symbolami w Q# .</span><span class="sxs-lookup"><span data-stu-id="35d21-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="35d21-138">Typy tablic</span><span class="sxs-lookup"><span data-stu-id="35d21-138">Array Types</span></span>

* <span data-ttu-id="35d21-139">Dla dowolnego prawidłowego Q# typu istnieje typ, który reprezentuje tablicę wartości tego typu.</span><span class="sxs-lookup"><span data-stu-id="35d21-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="35d21-140">Na przykład `Qubit[]` i `(Bool, Pauli)[]` reprezentuje tablice `Qubit` wartości i `(Bool, Pauli)` wartości krotek.</span><span class="sxs-lookup"><span data-stu-id="35d21-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="35d21-141">Tablica tablic jest również prawidłowa.</span><span class="sxs-lookup"><span data-stu-id="35d21-141">An array of arrays is also valid.</span></span> <span data-ttu-id="35d21-142">Rozszerzanie w poprzednim przykładzie, tablica `(Bool, Pauli)` tablic jest oznaczona `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="35d21-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="35d21-143">Ten przykład, `(Bool, Pauli)[][]` , reprezentuje potencjalnie nieregularną tablicę tablic, a nie prostokątną dwuwymiarową tablicę.</span><span class="sxs-lookup"><span data-stu-id="35d21-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="35d21-144">Q#nie obsługuje prostokątnych tablic wielowymiarowych.</span><span class="sxs-lookup"><span data-stu-id="35d21-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="35d21-145">Wartość tablicy może być zapisywana w Q# kodzie źródłowym przy użyciu nawiasów kwadratowych wokół elementów tablicy, jak w `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="35d21-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="35d21-146">Wspólny typ podstawowy wszystkich elementów w tablicy określa typ literału tablicy.</span><span class="sxs-lookup"><span data-stu-id="35d21-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="35d21-147">W związku z tym konstruowanie tablicy z elementami, które nie mają wspólnego typu podstawowego, zgłasza błąd.</span><span class="sxs-lookup"><span data-stu-id="35d21-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="35d21-148">Aby zapoznać się z przykładem, zobacz [tablice o możliwych wartościach](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span><span class="sxs-lookup"><span data-stu-id="35d21-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="35d21-149">Po utworzeniu elementy tablicy nie mogą być zmieniane.</span><span class="sxs-lookup"><span data-stu-id="35d21-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="35d21-150">Aby utworzyć zmodyfikowaną tablicę, należy użyć [instrukcji Update-and-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) lub [wyrażeń Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="35d21-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="35d21-151">Alternatywnie można utworzyć tablicę na podstawie jej rozmiaru przy użyciu `new` słowa kluczowego:</span><span class="sxs-lookup"><span data-stu-id="35d21-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="35d21-152">Użyj funkcji Core, `Length` Aby uzyskać liczbę elementów z tablicy jako `Int` .</span><span class="sxs-lookup"><span data-stu-id="35d21-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="35d21-153">Tablice można indeksować, aby uzyskać pojedyncze elementy lub nowe tablice zawierające podzestaw elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="35d21-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="35d21-154">Indeksy dolne tablic są oparte na zero i muszą być typu `Int` lub typu `Range` :</span><span class="sxs-lookup"><span data-stu-id="35d21-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="35d21-155">Typy krotek</span><span class="sxs-lookup"><span data-stu-id="35d21-155">Tuple Types</span></span>

<span data-ttu-id="35d21-156">Krotki są zaawansowaną koncepcją używaną przez cały Q# program do zbierania wartości w jednej wartości, co ułatwia ich przekazywanie.</span><span class="sxs-lookup"><span data-stu-id="35d21-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="35d21-157">W szczególności przy użyciu notacji krotki można wyrazić, że każda operacja i możliwy do odwoływać przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.</span><span class="sxs-lookup"><span data-stu-id="35d21-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="35d21-158">Podaną zero lub kilka różnych typów,,..., `T0` `T1` można zauważyć, że `Tn` Nowy *Typ krotki* jako `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="35d21-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="35d21-159">Typy używane do konstruowania nowego typu krotki mogą sami być krotkami, jak w `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="35d21-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="35d21-160">Takie zagnieżdżenie jest zawsze ograniczone, jednak ponieważ typy krotek nie mogą znajdować się w żadnych okolicznościach.</span><span class="sxs-lookup"><span data-stu-id="35d21-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="35d21-161">Wartości nowego typu krotki są krotkami tworzonymi przez sekwencje wartości z każdego typu w spójnej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="35d21-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="35d21-162">Na przykład `(3, false)` jest to krotka, której typem jest typ krotki `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="35d21-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="35d21-163">Istnieje możliwość tworzenia tablic krotek, spójnych kolekcji tablic, krotek podkolekcji i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="35d21-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="35d21-164">Od Q# 0,3, `Unit` jest nazwą *typu* pustej krotki; `()` jest używana dla *wartości* pustej krotki.</span><span class="sxs-lookup"><span data-stu-id="35d21-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="35d21-165">Wystąpienia krotki są niezmienne.</span><span class="sxs-lookup"><span data-stu-id="35d21-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="35d21-166">Q#Program nie udostępnia mechanizmu zmiany zawartości spójnej kolekcji po utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="35d21-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="35d21-167">Równoważna krotka singleton</span><span class="sxs-lookup"><span data-stu-id="35d21-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="35d21-168">Możliwe jest utworzenie pojedynczej krotki (pojedynczego elementu) `('T1)` , takiej jak `(5)` lub `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="35d21-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="35d21-169">Jednakże Q# traktuje pojedynczą krotkę jako odpowiednik wartości zamkniętego typu.</span><span class="sxs-lookup"><span data-stu-id="35d21-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="35d21-170">Oznacza to, że nie ma różnicy między `5` i `(5)` , lub między i i między i `5` `(((5)))` `(5, (6))` `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="35d21-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="35d21-171">Jest to równie ważne, aby można było pisać `(5)+3` w miarę pisania `5+3` ; oba wyrażenia są oceniane do `8` .</span><span class="sxs-lookup"><span data-stu-id="35d21-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="35d21-172">Ta równoważność ma zastosowanie do wszystkich celów, w tym przypisania i wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="35d21-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="35d21-173">Uwzględniając dowolne wyrażenie, to samo wyrażenie ujęte w nawiasy jest wyrażeniem tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="35d21-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="35d21-174">Na przykład `(7)` jest wyrażeniem typu `Int` , `([1,2,3])` jest wyrażeniem typu `Int[]` i `((1,2))` jest wyrażeniem typu `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="35d21-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="35d21-175">W szczególności oznacza to, że można wyświetlić operację lub funkcję, której kolekcja wejściowa lub typ krotki danych wyjściowych ma jedno pole jako przyjmujące pojedynczy argument lub zwraca pojedynczą wartość.</span><span class="sxs-lookup"><span data-stu-id="35d21-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="35d21-176">Nazywamy tę właściwość jako _równoważność spójnej kolekcji_.</span><span class="sxs-lookup"><span data-stu-id="35d21-176">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="35d21-177">Typy zdefiniowane przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="35d21-177">User-Defined Types</span></span>

<span data-ttu-id="35d21-178">Deklaracja typu zdefiniowanego przez użytkownika składa się ze słowa kluczowego `newtype` , po którym następuje nazwa typu zdefiniowanego przez użytkownika, elementu `=` , prawidłowej specyfikacji typu i kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="35d21-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="35d21-179">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="35d21-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="35d21-180">Każdy Q# plik źródłowy może deklarować dowolną liczbę typów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="35d21-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="35d21-181">Nazwy typów muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktów z nazwami operacji i funkcji.</span><span class="sxs-lookup"><span data-stu-id="35d21-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="35d21-182">Typy zdefiniowane przez użytkownika są różne, nawet jeśli typy podstawowe są identyczne.</span><span class="sxs-lookup"><span data-stu-id="35d21-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="35d21-183">W szczególności nie istnieje Automatyczna konwersja między wartościami dwóch typów zdefiniowanych przez użytkownika, nawet jeśli typy bazowe są identyczne.</span><span class="sxs-lookup"><span data-stu-id="35d21-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="35d21-184">Elementy nazwane a anonimowe</span><span class="sxs-lookup"><span data-stu-id="35d21-184">Named vs. anonymous items</span></span>

<span data-ttu-id="35d21-185">Q#Plik może definiować nowy nazwany typ zawierający pojedynczą wartość dowolnego typu prawnego.</span><span class="sxs-lookup"><span data-stu-id="35d21-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="35d21-186">Dla dowolnego typu krotki `T` można zadeklarować nowy typ zdefiniowany przez użytkownika, który jest podtypem `T` `newtype` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="35d21-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="35d21-187">Na @"microsoft.quantum.math" przykład w przestrzeni nazw liczba zespolona jest definiowana jako typ zdefiniowany przez użytkownika:</span><span class="sxs-lookup"><span data-stu-id="35d21-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="35d21-188">Ta instrukcja tworzy nowy typ z dwoma anonimowymi elementami typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="35d21-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="35d21-189">Poza elementami anonimowymi typy zdefiniowane przez użytkownika obsługują również *nazwane elementy* w Q# wersji 0,7 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="35d21-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="35d21-190">Można na przykład nazwać elementy do `Re` dla podwójnego reprezentowania rzeczywistej części liczby zespolonej i `Im` dla części urojonej:</span><span class="sxs-lookup"><span data-stu-id="35d21-190">For example, you could name the items to `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="35d21-191">Nazewnictwo jednego elementu w typie zdefiniowanym przez użytkownika nie oznacza, że wszystkie elementy muszą mieć nazwę, a także obsługiwane są dowolne kombinacje elementów nazwanych i nienazwanych.</span><span class="sxs-lookup"><span data-stu-id="35d21-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="35d21-192">Ponadto elementy wewnętrzne mogą być również nazwane.</span><span class="sxs-lookup"><span data-stu-id="35d21-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="35d21-193">Typ `Nested` , jak pokazano poniżej, ma typ podstawowy `(Double, (Int, String))` , którego tylko element typu `Int` ma nazwę, a wszystkie inne elementy są anonimowe.</span><span class="sxs-lookup"><span data-stu-id="35d21-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="35d21-194">Elementy nazwane mają zalety, do których można uzyskiwać dostęp bezpośrednio za pośrednictwem *operatora dostępu* `::` .</span><span class="sxs-lookup"><span data-stu-id="35d21-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="35d21-195">Oprócz udostępniania krótkich aliasów dla potencjalnie skomplikowanych typów krotek, istotną zaletą definiowania takich typów jest możliwość udokumentowania zamiaru określonej wartości.</span><span class="sxs-lookup"><span data-stu-id="35d21-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="35d21-196">Powracanie do przykładu `Complex` , może być również zdefiniowane współrzędne bieguna 2D jako typ zdefiniowany przez użytkownika:</span><span class="sxs-lookup"><span data-stu-id="35d21-196">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="35d21-197">Mimo że oba te `Complex` i `Polar` oba mają typ podstawowy `(Double, Double)` , te dwa typy są całkowicie niezgodne Q# , co minimalizuje ryzyko przypadkowego wywołania złożonej funkcji matematycznej z współrzędnymi biegunowymi i odwrotnie.</span><span class="sxs-lookup"><span data-stu-id="35d21-197">Even though both `Complex` and `Polar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="35d21-198">Dostęp do anonimowych elementów za pomocą operatora rozwinięcia</span><span class="sxs-lookup"><span data-stu-id="35d21-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="35d21-199">Aby uzyskać dostęp do anonimowych elementów, najpierw Wyodrębnij wartość opakowaną przy użyciu operatora przyrostkowego `!` .</span><span class="sxs-lookup"><span data-stu-id="35d21-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="35d21-200">Za pomocą operatora "unotocz" `!` można wyodrębnić wartość zawartą w typie zdefiniowanym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="35d21-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="35d21-201">Typ takiego wyrażenia "unotoka" jest typem podstawowym typu zdefiniowanego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="35d21-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="35d21-202">Pojedynczy operator odpakowywania odpakuje jedną warstwę otoki.</span><span class="sxs-lookup"><span data-stu-id="35d21-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="35d21-203">Użyj wielu nieopakowanych operatorów, aby uzyskać dostęp do wartości w postaci mnożenia.</span><span class="sxs-lookup"><span data-stu-id="35d21-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="35d21-204">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="35d21-204">For example:</span></span>

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

<span data-ttu-id="35d21-205">Aby uzyskać więcej informacji na temat operatora rozwinięcia, zobacz [wyrażenia typów Q# w ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="35d21-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="35d21-206">Tworzenie wartości typów zdefiniowanych przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="35d21-206">Creating values of user-defined types</span></span>

<span data-ttu-id="35d21-207">Utwórz wartości typu zdefiniowanego przez użytkownika, wywołując odpowiedni Konstruktor typów:</span><span class="sxs-lookup"><span data-stu-id="35d21-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="35d21-208">Alternatywnie można tworzyć nowe wartości z istniejących przy użyciu [wyrażeń Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="35d21-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="35d21-209">Podobnie jak w przypadku tablic, wyrażeń kopiowania i aktualizacji Kopiuj wszystkie wartości elementu oryginalnego wyrażenia z wyjątkiem określonych nazwanych elementów.</span><span class="sxs-lookup"><span data-stu-id="35d21-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="35d21-210">Dla tych wyjątków wartości tych elementów są wartości zdefiniowane po prawej stronie wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="35d21-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="35d21-211">Wszystkie inne konstrukcje językowe dostępne dla elementów tablicowych, na przykład [instrukcje Update-and-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), istnieją dla elementów nazwanych w typach zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="35d21-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

* <span data-ttu-id="35d21-212">Możesz użyć typów zdefiniowanych przez użytkownika wszędzie tam, gdzie używasz dowolnego innego typu.</span><span class="sxs-lookup"><span data-stu-id="35d21-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="35d21-213">W szczególności można zdefiniować tablicę typu zdefiniowanego przez użytkownika i dołączenia typu zdefiniowanego przez użytkownika jako elementu typu krotki.</span><span class="sxs-lookup"><span data-stu-id="35d21-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="35d21-214">Nie można tworzyć struktur typów cyklicznych.</span><span class="sxs-lookup"><span data-stu-id="35d21-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="35d21-215">Oznacza to, że typ definiujący typ zdefiniowany przez użytkownika nie może być typem krotki, który zawiera element typu zdefiniowanego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="35d21-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="35d21-216">Ogólnie rzecz biorąc, typy zdefiniowane przez użytkownika mogą nie zawierać cyklicznych zależności od siebie, więc następujący zestaw definicji typu jest nieprawidłowy:</span><span class="sxs-lookup"><span data-stu-id="35d21-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="35d21-217">Typy operacji i funkcji</span><span class="sxs-lookup"><span data-stu-id="35d21-217">Operation and Function Types</span></span>

<span data-ttu-id="35d21-218">Uwzględniając typy `'Tinput` i `'Tresult` :</span><span class="sxs-lookup"><span data-stu-id="35d21-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="35d21-219">`('Tinput => 'Tresult)`jest typem podstawowym dla każdej *operacji*, na przykład `((Qubit, Pauli) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="35d21-219">`('Tinput => 'Tresult)` is the basic type for any *operation*, for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="35d21-220">`('Tinput -> 'Tresult)`jest typem podstawowym dla dowolnej *funkcji*, na przykład `(Int -> Int)` .</span><span class="sxs-lookup"><span data-stu-id="35d21-220">`('Tinput -> 'Tresult)` is the basic type for any *function*, for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="35d21-221">Są one nazywane *sygnaturą* wywołania.</span><span class="sxs-lookup"><span data-stu-id="35d21-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="35d21-222">Wszystkie Q# wartości są wywoływane jako dane wejściowe i zwracają pojedynczą wartość jako dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="35d21-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="35d21-223">Można używać krotek zarówno dla wartości wejściowych, jak i wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="35d21-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="35d21-224">Liczba, która nie ma wyniku, zwraca `Unit` .</span><span class="sxs-lookup"><span data-stu-id="35d21-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="35d21-225">Możliwe do nadania, że żadne dane wejściowe nie przyjmują pustej kolekcji jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="35d21-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="35d21-226">Funktory</span><span class="sxs-lookup"><span data-stu-id="35d21-226">Functors</span></span>

<span data-ttu-id="35d21-227">Typy *funkcji* są w pełni określone przez ich sygnaturę.</span><span class="sxs-lookup"><span data-stu-id="35d21-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="35d21-228">Na przykład funkcja, która oblicza sinus kąta, będzie miała typ `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="35d21-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="35d21-229">*Operacje* mają pewne dodatkowe cechy, które są wyrażane jako część typu operacji.</span><span class="sxs-lookup"><span data-stu-id="35d21-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="35d21-230">Takie charakterystyki zawierają informacje o tym, które *funktory* operacja obsługuje.</span><span class="sxs-lookup"><span data-stu-id="35d21-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="35d21-231">Na przykład, jeśli wykonanie operacji opiera się na stanie innych qubits, powinien on obsługiwać `Controlled` Funktor; Jeśli operacja ma odwrotność, powinien obsługiwać `Adjoint` Funktor.</span><span class="sxs-lookup"><span data-stu-id="35d21-231">For example, if the execution of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="35d21-232">W tym artykule omówiono, jak funktory zmienić sygnaturę operacji.</span><span class="sxs-lookup"><span data-stu-id="35d21-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="35d21-233">Aby uzyskać więcej informacji na temat funktory i operacji, zobacz [operacje i Q# funkcje w ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="35d21-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="35d21-234">Aby wymagać obsługi dla `Controlled` i/lub `Adjoint` Funktor w typie operacji, należy dodać adnotację wskazującą odpowiadające jej cechy.</span><span class="sxs-lookup"><span data-stu-id="35d21-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="35d21-235">Adnotacja `is Ctl` (na przykład `(Qubit => Unit is Ctl)` ) wskazuje, że operacja jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="35d21-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="35d21-236">Oznacza to, że jego wykonywanie opiera się na stanie innego qubit lub qubits.</span><span class="sxs-lookup"><span data-stu-id="35d21-236">That is, its execution relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="35d21-237">Podobnie adnotacja `is Adj` wskazuje, że operacja ma sąsiadujące, to oznacza, że może być "odwrócona", co oznacza, że po zastosowaniu operacji, a następnie jej współdziałanie do stanu pozostawia stan niezmieniony.</span><span class="sxs-lookup"><span data-stu-id="35d21-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="35d21-238">Jeśli chcesz wymagać, aby operacja tego typu obsługiwała zarówno element, `Adjoint` jak i `Controlled` Funktor, możesz to zrobić jako `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="35d21-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="35d21-239">Na przykład wbudowana <xref:microsoft.quantum.intrinsic.x> operacja Pauli ma typ `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="35d21-239">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="35d21-240">Typ operacji, która nie obsługuje żadnej funktory, jest określany za pomocą samego typu danych wejściowych i wyjściowych, bez dodatkowej adnotacji.</span><span class="sxs-lookup"><span data-stu-id="35d21-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="35d21-241">Funkcje i operacje sparametryzowane typu</span><span class="sxs-lookup"><span data-stu-id="35d21-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="35d21-242">Możliwe do napisania typy mogą zawierać *parametry typu*.</span><span class="sxs-lookup"><span data-stu-id="35d21-242">Callable types may contain *type parameters*.</span></span>
<span data-ttu-id="35d21-243">Użyj symbolu poprzedzonego znakiem pojedynczego cudzysłowu, aby wyznaczyć parametr typu; na przykład `'A` jest parametrem typu prawnego.</span><span class="sxs-lookup"><span data-stu-id="35d21-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="35d21-244">Aby uzyskać więcej informacji i szczegółowe informacje na temat sposobu definiowania dożądanych parametrów typu, zobacz [operacje i Q# funkcje w ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span><span class="sxs-lookup"><span data-stu-id="35d21-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="35d21-245">Parametr typu może pojawić się więcej niż raz w pojedynczym podpisie.</span><span class="sxs-lookup"><span data-stu-id="35d21-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="35d21-246">Na przykład funkcja, która stosuje inną funkcję do każdego elementu tablicy i zwraca zebrany wynik ma sygnaturę `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="35d21-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="35d21-247">Podobnie funkcja, która zwraca skład dwóch operacji, ma sygnaturę `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="35d21-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="35d21-248">Po wywołaniu wywołania typu sparametryzowanego wszystkie argumenty, które mają ten sam parametr typu, muszą być tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="35d21-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="35d21-249">Q#Program nie udostępnia mechanizmu ograniczania możliwych typów, które użytkownik może zastąpić parametrem typu.</span><span class="sxs-lookup"><span data-stu-id="35d21-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="35d21-250">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="35d21-250">Next steps</span></span>

<span data-ttu-id="35d21-251">Teraz, gdy wykorzystano wszystkie typy, które składają się na Q# język, zobacz [typy wyrażeń Q# w](xref:microsoft.quantum.guide.expressions) , aby dowiedzieć się, jak tworzyć i manipulować wyrażeniami tych różnych typów.</span><span class="sxs-lookup"><span data-stu-id="35d21-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>

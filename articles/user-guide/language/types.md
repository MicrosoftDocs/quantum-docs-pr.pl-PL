---
title: Typy w języku Q#
description: 'Dowiedz się więcej na temat różnych typów używanych w języku programowania Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: f7a3ac3813966c0ef695068297ce4d9949ead554
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327292"
---
# <a name="types-in-q"></a><span data-ttu-id="fe2e8-103">Typy w języku Q#</span><span class="sxs-lookup"><span data-stu-id="fe2e8-103">Types in Q#</span></span>

<span data-ttu-id="fe2e8-104">Na tej stronie przedstawiono model typu Q # i opisano składnię służącą do określania typów i pracy z typami.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="fe2e8-105">Następna strona, [wyrażenia typu](xref:microsoft.quantum.guide.expressions), szczegóły dotyczące tworzenia i operowania wyrażeniami tych typów.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="fe2e8-106">Należy pamiętać, że funkcja Q # jest językiem o *jednoznacznie określonym* typie, w taki sposób, że dokładne użycie tych typów może pomóc kompilatorowi zapewnić silne gwarancje dotyczące programów Q # w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="fe2e8-107">Aby zapewnić najwyższy możliwy poziom gwarancji, konwersje między typami w Q # muszą być jawne przy użyciu wywołań do funkcji, które wyrażają konwersję.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="fe2e8-108">Różne takie funkcje są dostępne jako część <xref:microsoft.quantum.convert> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="fe2e8-109">Rzutowanie na zgodne typy z drugiej strony odbywa się niejawnie.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="fe2e8-110">Polecenie Q # zapewnia typy pierwotne, które mogą być używane bezpośrednio, i różne sposoby tworzenia nowych typów z innych typów.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="fe2e8-111">Opiszemy każdą z nich w pozostałej części tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="fe2e8-112">Typy pierwotne</span><span class="sxs-lookup"><span data-stu-id="fe2e8-112">Primitive Types</span></span>

<span data-ttu-id="fe2e8-113">Język Q # zawiera kilka *typów pierwotnych*, z których można utworzyć inne typy:</span><span class="sxs-lookup"><span data-stu-id="fe2e8-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="fe2e8-114">`Int`Typ reprezentuje 64-bitową liczbę całkowitą ze znakiem, np.: `2` , `107` , `-5` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="fe2e8-115">`BigInt`Typ reprezentuje podpisaną liczbę całkowitą o dowolnym rozmiarze, np. `2L` , `107L` , `-5L` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="fe2e8-116">Ten typ jest oparty na platformie .NET<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="fe2e8-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="fe2e8-117">Wprowadź.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-117">type.</span></span>
- <span data-ttu-id="fe2e8-118">`Double`Typ reprezentuje liczbę zmiennoprzecinkową o podwójnej precyzji, np.: `0.0` , `-1.3` , `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="fe2e8-119">`Bool`Typ reprezentuje wartość logiczną, która może być `true` lub `false` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="fe2e8-120">`Range`Typ reprezentuje sekwencję liczb całkowitych, oznaczaną przez `start..step..stop` , gdzie oznacza to, że ten krok jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="fe2e8-121">Odpowiada to `start .. stop` `start..1..stop` , a np. `1..2..7` reprezentuje sekwencję $ \{ 1, 3, 5, 7 \} $.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="fe2e8-122">`String`Typ jest sekwencją znaków Unicode, które są nieprzezroczyste dla użytkownika po utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="fe2e8-123">Ten typ służy do zgłaszania komunikatów do klasycznego hosta w przypadku błędu lub zdarzenia diagnostycznego.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="fe2e8-124">`Unit`Typ jest typem, który dopuszcza tylko jedną wartość `()` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="fe2e8-125">Ten typ jest używany do wskazania, że funkcja Q # lub operacja nie zwraca żadnych informacji.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="fe2e8-126">`Qubit`Typ reprezentuje bit Quantum lub qubit.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="fe2e8-127">`Qubit`s nie jest nieprzezroczysty dla użytkownika; Jedyną operacją dopuszczalną dla nich, inną niż przekazanie jej do innej operacji, jest przetestowanie pod kątem tożsamości (równość).</span><span class="sxs-lookup"><span data-stu-id="fe2e8-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="fe2e8-128">Ostatecznie akcje na `Qubit` s są implementowane przez wywołanie wewnętrznych instrukcji na procesorze Quantum (lub w jego symulacji).</span><span class="sxs-lookup"><span data-stu-id="fe2e8-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="fe2e8-129">`Pauli`Typ reprezentuje jeden z czterech operatorów Pauli pojedynczej qubit.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="fe2e8-130">Ten typ służy do oznaczania operacji podstawowej dla rotacji i do określenia zauważalnego pomiaru.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="fe2e8-131">Jest to typ wyliczeniowy, który ma cztery możliwe wartości: `PauliI` , `PauliX` , `PauliY` , i `PauliZ` , które są stałymi typu `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="fe2e8-132">`Result`Typ reprezentuje wynik pomiaru.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="fe2e8-133">Jest to typ wyliczeniowy z dwoma możliwymi wartościami: `One` i `Zero` , które są stałymi typu `Result` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="fe2e8-134">`Zero`wskazuje, że eigenvalue + 1 została zmierzona; `One`wskazuje wartość-1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="fe2e8-135">Stałe,,,,,, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` i `Zero` są zastrzeżonymi symbolami w Q #.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="fe2e8-136">Typy tablic</span><span class="sxs-lookup"><span data-stu-id="fe2e8-136">Array Types</span></span>

<span data-ttu-id="fe2e8-137">Uwzględniając dowolny prawidłowy typ Q # `'T` , istnieje typ, który reprezentuje tablicę wartości typu `'T` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="fe2e8-138">Ten typ tablicy jest reprezentowany jako `'T[]` ; na przykład `Qubit[]` lub `Int[][]` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="fe2e8-139">Na przykład, kolekcja liczb całkowitych jest oznaczona `Int[]` , podczas gdy tablica tablic `(Bool, Pauli)` wartości jest oznaczona `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="fe2e8-140">W drugim przykładzie należy zauważyć, że reprezentuje to potencjalnie nieregularną tablicę tablic, a nie prostokątną dwuwymiarową tablicę.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="fe2e8-141">Usługa Q # nie zapewnia obsługi prostokątnych tablic wielowymiarowych.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="fe2e8-142">Wartość tablicy można napisać w kodzie źródłowym Q # przy użyciu nawiasów kwadratowych wokół elementów tablicy, jak w `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="fe2e8-143">Typ literału tablicy jest określany przez wspólny typ podstawowy wszystkich elementów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> <span data-ttu-id="fe2e8-144">W związku z tym próba skonstruowania tablicy z elementami, które nie mają wspólnego typu podstawowego, spowoduje wystąpienie błędu.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-144">Hence trying to construct an array with elements that have no common base type will raise an error.</span></span>  
<span data-ttu-id="fe2e8-145">Zapoznaj się z [tablicami](xref:microsoft.quantum.guide.expressions#arrays-of-callables) żądanych przykładów.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-145">See [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables) for an example of this.</span></span>

> [!WARNING]
> <span data-ttu-id="fe2e8-146">Elementy tablicy nie mogą być zmieniane po utworzeniu tablicy.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-146">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="fe2e8-147">[Instrukcje Update-and-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) i/lub [wyrażenia Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) mogą służyć do konstruowania zmodyfikowanej tablicy.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-147">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="fe2e8-148">Alternatywnie można utworzyć tablicę na podstawie jej rozmiaru przy użyciu `new` słowa kluczowego:</span><span class="sxs-lookup"><span data-stu-id="fe2e8-148">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="fe2e8-149">W obu przypadkach, gdy tablica została skonstruowana, funkcja podstawowa `Length` może służyć do uzyskania liczby elementów jako `Int` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-149">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="fe2e8-150">Tablice można indeksować za pomocą nawiasów kwadratowych, z indeksami dolnymi albo typem `Int` lub typem `Range` , aby uzyskać pojedyncze elementy lub nowe tablice zawierające podzestaw elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-150">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="fe2e8-151">Indeksy dolne tablic są oparte na zero:</span><span class="sxs-lookup"><span data-stu-id="fe2e8-151">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="fe2e8-152">Typy krotek</span><span class="sxs-lookup"><span data-stu-id="fe2e8-152">Tuple Types</span></span>

<span data-ttu-id="fe2e8-153">Podaną zero lub kilka różnych typów,,..., `T0` `T1` `Tn` można zauważyć, że nowy *Typ krotki* jest w postaci `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-153">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="fe2e8-154">Typy używane do konstruowania nowego typu krotki mogą sami być krotkami, jak w `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-154">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="fe2e8-155">Takie zagnieżdżenie jest zawsze ograniczone, jednak ponieważ typy krotek nie mogą znajdować się w żadnych okolicznościach.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-155">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="fe2e8-156">Wartości nowego typu krotki są krotkami tworzonymi przez sekwencje wartości z każdego typu w spójnej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-156">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="fe2e8-157">Na przykład `(3, false)` jest krotką, której typem jest typ krotki `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-157">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="fe2e8-158">Istnieje możliwość tworzenia tablic spójnych krotek, krotek tablic, krotek podkolekcji itd.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-158">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="fe2e8-159">Począwszy od Q # 0,3, `Unit` jest nazwą *typu* pustej krotki; `()` jest używana dla pustej *wartości*krotki.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-159">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="fe2e8-160">Wystąpienia krotki są niezmienne.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-160">Tuple instances are immutable.</span></span>
<span data-ttu-id="fe2e8-161">Usługa Q # nie udostępnia mechanizmu zmiany zawartości spójnej kolekcji po utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-161">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="fe2e8-162">Krotki są zaawansowaną koncepcją używaną przez funkcję Q # do zbierania wartości w jednej wartości, co ułatwia ich przekazywanie.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-162">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="fe2e8-163">W szczególności, za pomocą notacji spójnej, możemy wyrazić, że każda operacja i możliwy do oddzwonienia przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-163">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="fe2e8-164">Równoważna krotka singleton</span><span class="sxs-lookup"><span data-stu-id="fe2e8-164">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="fe2e8-165">Można utworzyć pojedynczą (jednoelementową) krotkę, `('T1)` taką jak `(5)` lub `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-165">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="fe2e8-166">Jednakże Q # traktuje pojedynczą krotkę jako całkowicie równoważną wartości typu zamkniętego.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-166">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="fe2e8-167">Oznacza to, że nie ma różnicy między `5` i `(5)` , lub między i i między i `5` `(((5)))` `(5, (6))` `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-167">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="fe2e8-168">Jest równie ważna do zapisu `(5)+3` jako do zapisu `5+3` , a oba wyrażenia będą oceniane do `8` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-168">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="fe2e8-169">Ta równoważność ma zastosowanie do wszystkich celów, w tym przypisania i wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-169">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="fe2e8-170">Uwzględniając dowolne wyrażenie, to samo wyrażenie ujęte w nawiasy jest wyrażeniem tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-170">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="fe2e8-171">Na przykład, `(7)` jest wyrażeniem `Int` , `([1,2,3])` jest wyrażeniem typu Array `Int` -s i `((1,2))` jest wyrażeniem typu `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-171">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="fe2e8-172">W szczególności oznacza to, że operacja lub funkcja, której kolekcja wejściowa lub typ krotki danych wyjściowych ma jedno pole może być uważane za przyjmujące pojedynczy argument lub zwracającą pojedynczą wartość.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-172">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="fe2e8-173">Nazywamy tę właściwość jako _równoważność spójnej kolekcji_.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-173">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="fe2e8-174">Typy zdefiniowane przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="fe2e8-174">User-Defined Types</span></span>

<span data-ttu-id="fe2e8-175">Deklaracja typu zdefiniowanego przez użytkownika składa się ze słowa kluczowego `newtype` , po którym następuje nazwa typu zdefiniowanego przez użytkownika, elementu `=` , prawidłowej specyfikacji typu i kończącego się średnika.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-175">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="fe2e8-176">Przykład:</span><span class="sxs-lookup"><span data-stu-id="fe2e8-176">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="fe2e8-177">Każdy plik źródłowy Q # może deklarować dowolną liczbę typów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-177">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="fe2e8-178">Nazwy typów muszą być unikatowe w obrębie przestrzeni nazw i mogą nie powodować konfliktów z nazwami operacji i funkcji.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-178">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="fe2e8-179">Typy zdefiniowane przez użytkownika są różne, nawet jeśli typy podstawowe są identyczne.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-179">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="fe2e8-180">W szczególności nie istnieje Automatyczna konwersja między wartościami dwóch typów zdefiniowanych przez użytkownika, nawet jeśli typy bazowe są identyczne.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-180">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="fe2e8-181">Elementy nazwane a anonimowe</span><span class="sxs-lookup"><span data-stu-id="fe2e8-181">Named vs. anonymous items</span></span>

<span data-ttu-id="fe2e8-182">Plik Q # może definiować nowy nazwany typ zawierający pojedynczą wartość dowolnego typu prawnego.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-182">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="fe2e8-183">Dla dowolnego typu krotki `T` można zadeklarować nowy typ zdefiniowany przez użytkownika, który jest podtypem `T` `newtype` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-183">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="fe2e8-184">Na @"microsoft.quantum.math" przykład w przestrzeni nazw liczba zespolona jest definiowana jako typ zdefiniowany przez użytkownika:</span><span class="sxs-lookup"><span data-stu-id="fe2e8-184">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="fe2e8-185">Ta instrukcja tworzy nowy typ z dwoma anonimowymi elementami typu `Double` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-185">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="fe2e8-186">Poza elementami anonimowymi typy zdefiniowane przez użytkownika obsługują również *nazwane elementy* w przypadku Q # w wersji 0,7 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-186">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="fe2e8-187">Na przykład możemy mieć nazwę do elementów `Re` dla podwójnego reprezentowania rzeczywistej części liczby zespolonej i `Im` dla części urojonej:</span><span class="sxs-lookup"><span data-stu-id="fe2e8-187">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="fe2e8-188">Nazewnictwo jednego elementu w typie zdefiniowanym przez użytkownika nie oznacza, że wszystkie elementy muszą mieć nazwę, a także obsługiwane są dowolne kombinacje elementów nazwanych i nienazwanych.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-188">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="fe2e8-189">Ponadto elementy wewnętrzne mogą być również nazwane.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-189">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="fe2e8-190">Typ, `Nested` zgodnie z definicją poniżej, ma typ podstawowy `(Double, (Int, String))` , którego tylko element typu `Int` ma nazwę i wszystkie pozostałe elementy są anonimowe.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-190">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="fe2e8-191">Elementy nazwane mają zalety, do których można uzyskiwać dostęp bezpośrednio za pośrednictwem *operatora dostępu* `::` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-191">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="fe2e8-192">Oprócz udostępniania krótkich aliasów dla potencjalnie skomplikowanych typów krotek, jedną istotną zaletą zdefiniowania takich typów jest możliwość udokumentowania zamiaru określonej wartości.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-192">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="fe2e8-193">Powracanie do przykładu `Complex` , może być również zdefiniowane współrzędne bieguna 2D jako typ zdefiniowany przez użytkownika:</span><span class="sxs-lookup"><span data-stu-id="fe2e8-193">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="fe2e8-194">Mimo że oba `Complex` i `Polar` oba mają typ podstawowy `(Double, Double)` , dwa typy są całkowicie niezgodne z Q #, minimalizując ryzyko przypadkowego wywołania złożonej funkcji matematycznej ze współrzędnymi biegunowymi i odwrotnie.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-194">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="fe2e8-195">W ten sposób zdefiniowane przez użytkownika typy mają podobną rolę jako rekordy w języku F #.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-195">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="fe2e8-196">Dostęp do anonimowych elementów za pomocą operatora rozwinięcia</span><span class="sxs-lookup"><span data-stu-id="fe2e8-196">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="fe2e8-197">Aby można było uzyskać dostęp do anonimowych elementów z drugiej strony, najpierw musi zostać wyodrębniona wartość opakowana przy użyciu operatora przyrostkowego `!` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-197">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="fe2e8-198">Operator "unotocz" `!` umożliwia wyodrębnienie wartości zawartej w typie zdefiniowanym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-198">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="fe2e8-199">Typ takiego wyrażenia "unotoka" jest typem podstawowym typu zdefiniowanego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-199">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="fe2e8-200">Operator rozwinięcia odpakuje dokładnie jedną warstwę zawijania.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-200">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="fe2e8-201">Wielokrotne operatory odwinięcia mogą być używane w celu uzyskania dostępu do wartości przepakowanej wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-201">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="fe2e8-202">Przykład:</span><span class="sxs-lookup"><span data-stu-id="fe2e8-202">For instance:</span></span>

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

<span data-ttu-id="fe2e8-203">Więcej szczegółów dotyczących operatora odpakowania można znaleźć w [wyrażeniach typu w Q #](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="fe2e8-203">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="fe2e8-204">Tworzenie wartości typów zdefiniowanych przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="fe2e8-204">Creating values of user-defined types</span></span>

<span data-ttu-id="fe2e8-205">Wartości typu zdefiniowanego przez użytkownika można utworzyć, wywołując odpowiedni Konstruktor typów:</span><span class="sxs-lookup"><span data-stu-id="fe2e8-205">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="fe2e8-206">Alternatywnie nowe wartości można tworzyć z istniejących przy użyciu [wyrażeń Copy-and-Update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="fe2e8-206">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="fe2e8-207">Podobnie jak w przypadku tablic, takie wyrażenia kopiują wszystkie wartości elementu oryginalnego wyrażenia, z wyjątkiem określonych nazwanych elementów.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-207">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="fe2e8-208">Dla tych wartości są ustawiane na te, które zostały zdefiniowane po prawej stronie wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-208">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="fe2e8-209">Wszystkie inne konstrukcje języka, takie jak przykładowe [instrukcje Update-and-Reassign](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), które są dostępne dla elementów tablicy istnieje dla elementów nazwanych w typach zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-209">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

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

<span data-ttu-id="fe2e8-210">Typy zdefiniowane przez użytkownika mogą być używane wszędzie tam, gdzie można korzystać z dowolnego innego typu.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-210">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="fe2e8-211">W szczególności można zdefiniować tablicę typu zdefiniowanego przez użytkownika i dołączenia typu zdefiniowanego przez użytkownika jako elementu typu krotki.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-211">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="fe2e8-212">Uwaga nie można utworzyć struktur typów cyklicznych.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-212">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="fe2e8-213">Oznacza to, że typ definiujący typ zdefiniowany przez użytkownika nie może być typem krotki, który zawiera element typu zdefiniowanego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-213">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="fe2e8-214">Ogólnie rzecz biorąc, typy zdefiniowane przez użytkownika mogą nie zawierać cyklicznych zależności od siebie, więc następujący zestaw definicji typu byłby niedozwolony:</span><span class="sxs-lookup"><span data-stu-id="fe2e8-214">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="fe2e8-215">Typy operacji i funkcji</span><span class="sxs-lookup"><span data-stu-id="fe2e8-215">Operation and Function Types</span></span>

<span data-ttu-id="fe2e8-216">Typ podstawowy dla każdego elementu, który można wywołać, jest zapisywana jako `('Tinput => 'Tresult)` lub `('Tinput -> 'Tresult)` , gdzie oba `'Tinput` i `'Tresult` są typami.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-216">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="fe2e8-217">Są one nazywane *sygnaturą* wywołania.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-217">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="fe2e8-218">Wszystkie wywoływane wartości Q # są traktowane jako dane wejściowe i zwracają pojedynczą wartość jako dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-218">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="fe2e8-219">Zarówno wartość wejściowa, jak i wyjściowa mogą być krotki.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-219">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="fe2e8-220">Możliwe do zwrócenia, które nie zwracają wyniku `Unit` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-220">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="fe2e8-221">Możliwe do nadania, że żadne dane wejściowe nie przyjmują pustej kolekcji jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-221">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="fe2e8-222">Pierwszy formularz, z `=>` , jest używany do operacji; drugi formularz, z `->` , dla usługi Functions.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-222">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="fe2e8-223">Na przykład `((Qubit, Pauli) => Result)` reprezentuje podpis dla możliwej operacji pomiaru pojedynczej qubit.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-223">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="fe2e8-224">Typy *funkcji* są w pełni określone przez ich sygnaturę.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-224">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="fe2e8-225">Na przykład funkcja, która oblicza sinus kąta, będzie miała typ `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-225">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="fe2e8-226">*Operacje*---, ale nie funkcje---mają pewne dodatkowe cechy, które są wyrażane jako część typu operacji.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-226">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="fe2e8-227">Takie charakterystyki zawierają informacje o tym, co *funktory* operacja obsługuje.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-227">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="fe2e8-228">Na przykład, jeśli wykonanie operacji może być kondycjonowane na stanie innych qubits, powinien obsługiwać `Controlled` Funktor; Jeśli operacja ma odwrotność, powinien obsługiwać `Adjoint` Funktor.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-228">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="fe2e8-229">Funktory i operacje są szczegółowo omówione w temacie [Operations and Functions in Q #](xref:microsoft.quantum.guide.operationsfunctions), ale po prostu omawiamy, jak to zmienia sygnaturę operacji.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-229">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="fe2e8-230">Aby wymagać obsługi dla `Controlled` i/lub `Adjoint` Funktor w typie operacji, musimy dodać adnotację wskazującą odpowiednie cechy.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-230">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="fe2e8-231">Adnotacja `is Ctl` (np. `(Qubit => Unit is Ctl)` ) wskazuje, że operacja jest sterowana---, co oznacza, że jest wykonywana na stanie innego qubit lub qubits.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-231">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="fe2e8-232">Podobnie, `is Adj` oznacza to, że operacja ma sąsiadujące; lub po prostu może być "odwrócona", co oznacza, że po zastosowaniu operacji, a następnie jej przyłączenie do stanu pozostawia stan bez zmian.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-232">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="fe2e8-233">Jeśli chcemy wymagać, aby operacja tego typu obsługiwała zarówno `Adjoint` i Funktor, `Controlled` jak to możliwe `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-233">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="fe2e8-234">Na przykład wbudowana <xref:microsoft.quantum.intrinsic.x> operacja Pauli ma typ `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-234">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="fe2e8-235">Typ operacji, która nie obsługuje żadnej funktory, jest określany za pomocą samego typu danych wejściowych i wyjściowych, bez dodatkowej adnotacji.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-235">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="fe2e8-236">Funkcje i operacje sparametryzowane typu</span><span class="sxs-lookup"><span data-stu-id="fe2e8-236">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="fe2e8-237">Możliwe do napisania typy mogą zawierać parametry typu.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-237">Callable types may contain type parameters.</span></span>
<span data-ttu-id="fe2e8-238">Parametry typu są wskazywane przez symbol poprzedzony pojedynczym cudzysłowem; na przykład `'A` jest parametrem typu prawnego.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-238">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="fe2e8-239">Szczegóły dotyczące definiowania parametrów z parametrami, które są wywoływane, są dostępne na stronie [operacje i funkcje w polu Q #](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-239">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="fe2e8-240">Parametr typu może pojawić się więcej niż raz w pojedynczym podpisie.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-240">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="fe2e8-241">Na przykład funkcja, która stosuje inną funkcję do każdego elementu tablicy i zwraca zebrane wyniki byłyby sygnaturą `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-241">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="fe2e8-242">Podobnie funkcja, która zwraca skład dwóch operacji, może mieć sygnaturę `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="fe2e8-242">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="fe2e8-243">W przypadku wywołania sparametryzowanego typu, wszystkie argumenty, które mają ten sam parametr typu, muszą być tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-243">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="fe2e8-244">Funkcja Q # nie udostępnia mechanizmu ograniczenia możliwych typów, które mogą zostać zastąpione dla parametru typu.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-244">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe2e8-245">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="fe2e8-245">Next steps</span></span>

<span data-ttu-id="fe2e8-246">Teraz, gdy wykorzystano wszystkie typy, które składają się na język Q #, można umieścić [wyrażenia w polu q #](xref:microsoft.quantum.guide.expressions) , aby zobaczyć, jak tworzyć i manipulować wyrażeniami różnych typów.</span><span class="sxs-lookup"><span data-stu-id="fe2e8-246">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>



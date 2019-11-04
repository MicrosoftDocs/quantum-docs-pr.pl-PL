---
title: 'Typ modelu Q # | Microsoft Docs'
description: 'Model typu Q #'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184750"
---
# <a name="the-type-model"></a><span data-ttu-id="9250e-103">Model typu</span><span class="sxs-lookup"><span data-stu-id="9250e-103">The Type Model</span></span>

<span data-ttu-id="9250e-104">W tej sekcji przedstawiono model typu Q # i opisano składnię służącą do określania typów i pracy z typami.</span><span class="sxs-lookup"><span data-stu-id="9250e-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="9250e-105">Należy pamiętać, że funkcja Q # jest językiem o *jednoznacznie określonym* typie, w taki sposób, że dokładne użycie tych typów może pomóc kompilatorowi zapewnić silne gwarancje dotyczące programów Q # w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="9250e-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="9250e-106">Aby zapewnić najwyższy możliwy poziom gwarancji, konwersje między typami w Q # muszą być jawne przy użyciu wywołań do funkcji, które wyrażają konwersję.</span><span class="sxs-lookup"><span data-stu-id="9250e-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="9250e-107">Różne takie funkcje są dostępne jako część przestrzeni nazw <xref:microsoft.quantum.convert>.</span><span class="sxs-lookup"><span data-stu-id="9250e-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="9250e-108">Rzutowanie na zgodne typy z drugiej strony odbywa się niejawnie.</span><span class="sxs-lookup"><span data-stu-id="9250e-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="9250e-109">Polecenie Q # zapewnia typy pierwotne, które mogą być używane bezpośrednio, i różne sposoby tworzenia nowych typów z innych typów.</span><span class="sxs-lookup"><span data-stu-id="9250e-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="9250e-110">Opiszemy każdą z nich w pozostałej części tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="9250e-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="9250e-111">Typy pierwotne</span><span class="sxs-lookup"><span data-stu-id="9250e-111">Primitive Types</span></span>

<span data-ttu-id="9250e-112">Język Q # zawiera kilka *typów pierwotnych*, z których można utworzyć inne typy:</span><span class="sxs-lookup"><span data-stu-id="9250e-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="9250e-113">Typ `Int` reprezentuje 64-bitową liczbę całkowitą ze znakiem, np.: `2`, `107``-5`.</span><span class="sxs-lookup"><span data-stu-id="9250e-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="9250e-114">Typ `BigInt` reprezentuje podpisaną liczbę całkowitą o dowolnym rozmiarze, np. `2L`, `107L``-5L`.</span><span class="sxs-lookup"><span data-stu-id="9250e-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="9250e-115">Ten typ jest oparty na <xref:System.Numerics.BigInteger> .NET</span><span class="sxs-lookup"><span data-stu-id="9250e-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="9250e-116">Wprowadź.</span><span class="sxs-lookup"><span data-stu-id="9250e-116">type.</span></span>
- <span data-ttu-id="9250e-117">Typ `Double` reprezentuje liczbę zmiennoprzecinkową o podwójnej precyzji, np.: `0.0`, `-1.3``4e-7`.</span><span class="sxs-lookup"><span data-stu-id="9250e-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="9250e-118">Typ `Bool` reprezentuje wartość logiczną, która może być `true` lub `false`.</span><span class="sxs-lookup"><span data-stu-id="9250e-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="9250e-119">Typ `Qubit` reprezentuje bit Quantum lub qubit.</span><span class="sxs-lookup"><span data-stu-id="9250e-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="9250e-120">`Qubit`s są nieprzezroczyste dla użytkownika; Jedyną operacją dopuszczalną dla nich, inną niż przekazanie jej do innej operacji, jest przetestowanie pod kątem tożsamości (równość).</span><span class="sxs-lookup"><span data-stu-id="9250e-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="9250e-121">W rezultacie akcje na `Qubit`s są implementowane przez wywoływanie instrukcji wewnętrznych na procesorze Quantum (lub w jego symulacji).</span><span class="sxs-lookup"><span data-stu-id="9250e-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="9250e-122">Typ `Pauli` reprezentuje jeden z czterech operatorów Pauli (Single-qubit).</span><span class="sxs-lookup"><span data-stu-id="9250e-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="9250e-123">Ten typ służy do oznaczania operacji podstawowej dla rotacji i do określenia zauważalnego pomiaru.</span><span class="sxs-lookup"><span data-stu-id="9250e-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="9250e-124">Jest to typ wyliczeniowy, który ma cztery możliwe wartości: `PauliI`, `PauliX`, `PauliY`i `PauliZ`, które są stałymi typu `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="9250e-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="9250e-125">Typ `Result` reprezentuje wynik pomiaru.</span><span class="sxs-lookup"><span data-stu-id="9250e-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="9250e-126">Jest to typ wyliczeniowy z dwoma możliwymi wartościami: `One` i `Zero`, które są stałymi typu `Result`.</span><span class="sxs-lookup"><span data-stu-id="9250e-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="9250e-127">`Zero` wskazuje, że eigenvalue + 1 została zmierzona; `One` wskazuje-1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="9250e-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="9250e-128">Typ `Range` reprezentuje sekwencję liczb całkowitych, która jest oznaczona przez `start..step..stop`, gdzie oznacza to, że jest to opcja.</span><span class="sxs-lookup"><span data-stu-id="9250e-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="9250e-129">`start .. stop` odpowiada `start..1..stop`, a na przykład `1..2..7` reprezentuje sekwencję $\{1, 3, 5, 7\}$.</span><span class="sxs-lookup"><span data-stu-id="9250e-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="9250e-130">Typ `String` jest sekwencją znaków Unicode, które są nieprzezroczyste dla użytkownika po utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="9250e-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="9250e-131">Ten typ służy do zgłaszania komunikatów do klasycznego hosta w przypadku błędu lub zdarzenia diagnostycznego.</span><span class="sxs-lookup"><span data-stu-id="9250e-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="9250e-132">Typ `Unit` jest typem, który dopuszcza tylko jedną wartość `()`.</span><span class="sxs-lookup"><span data-stu-id="9250e-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="9250e-133">Ten typ jest używany do wskazania, że funkcja Q # lub operacja nie zwraca żadnych informacji.</span><span class="sxs-lookup"><span data-stu-id="9250e-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="9250e-134">Stałe `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`i `Zero` są zastrzeżonymi symbolami w Q #.</span><span class="sxs-lookup"><span data-stu-id="9250e-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="9250e-135">Typy tablic</span><span class="sxs-lookup"><span data-stu-id="9250e-135">Array Types</span></span>

<span data-ttu-id="9250e-136">Uwzględniając dowolny prawidłowy typ Q # `'T`, istnieje typ, który reprezentuje tablicę wartości typu `'T`.</span><span class="sxs-lookup"><span data-stu-id="9250e-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="9250e-137">Ten typ tablicy jest reprezentowany jako `'T[]`; na przykład `Qubit[]` lub `Int[][]`.</span><span class="sxs-lookup"><span data-stu-id="9250e-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="9250e-138">Na przykład kolekcja liczb całkowitych jest oznaczona `Int[]`, podczas gdy tablica tablic `(Bool, Pauli)` wartości jest oznaczona jako `(Bool, Pauli)[][]`.</span><span class="sxs-lookup"><span data-stu-id="9250e-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="9250e-139">W drugim przykładzie należy zauważyć, że reprezentuje to potencjalnie nieregularną tablicę tablic, a nie prostokątną dwuwymiarową tablicę.</span><span class="sxs-lookup"><span data-stu-id="9250e-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="9250e-140">Usługa Q # nie zapewnia obsługi prostokątnych tablic wielowymiarowych.</span><span class="sxs-lookup"><span data-stu-id="9250e-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="9250e-141">Wartość tablicy można napisać w kodzie źródłowym Q # przy użyciu nawiasów kwadratowych wokół elementów tablicy, jak w `[PauliI, PauliX, PauliY, PauliZ]`.</span><span class="sxs-lookup"><span data-stu-id="9250e-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="9250e-142">Typ literału tablicy jest określany przez wspólny typ podstawowy wszystkich elementów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="9250e-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="9250e-143">Elementy tablicy nie mogą być zmieniane po utworzeniu tablicy.</span><span class="sxs-lookup"><span data-stu-id="9250e-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="9250e-144">Instrukcje Update-and-Reassign i/lub wyrażenia Copy-and-Update mogą służyć do konstruowania zmodyfikowanej tablicy.</span><span class="sxs-lookup"><span data-stu-id="9250e-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="9250e-145">Alternatywnie można utworzyć tablicę na podstawie jej rozmiaru przy użyciu słowa kluczowego `new`:</span><span class="sxs-lookup"><span data-stu-id="9250e-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="9250e-146">W obu przypadkach, gdy macierz została skonstruowana, funkcja podstawowa `Length` może służyć do uzyskania liczby elementów jako `Int`.</span><span class="sxs-lookup"><span data-stu-id="9250e-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="9250e-147">Tablice można indeksować za pomocą nawiasów kwadratowych, ze indeksami dolnymi lub typem `Int` lub `Range`, aby uzyskać pojedyncze elementy lub nowe tablice zawierające podzestaw elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="9250e-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="9250e-148">Indeksy dolne tablic są oparte na zero:</span><span class="sxs-lookup"><span data-stu-id="9250e-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="9250e-149">Typy krotek</span><span class="sxs-lookup"><span data-stu-id="9250e-149">Tuple Types</span></span>

<span data-ttu-id="9250e-150">Nadawane zero lub więcej różnych typów `T0`, `T1`,..., `Tn`, możemy zauważyć nowy *Typ krotki* jako `(T0, T1, ..., Tn)`.</span><span class="sxs-lookup"><span data-stu-id="9250e-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="9250e-151">Typy używane do konstruowania nowego typu krotki mogą być krotkami, jak w `(Int, (Qubit, Qubit))`.</span><span class="sxs-lookup"><span data-stu-id="9250e-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="9250e-152">Takie zagnieżdżenie jest zawsze ograniczone, jednak ponieważ typy krotek nie mogą znajdować się w żadnych okolicznościach.</span><span class="sxs-lookup"><span data-stu-id="9250e-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="9250e-153">Wartości nowego typu krotki są krotkami tworzonymi przez sekwencje wartości z każdego typu w spójnej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="9250e-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="9250e-154">Na przykład `(3, false)` jest krotką, której typem jest typ krotki `(Int, Bool)`.</span><span class="sxs-lookup"><span data-stu-id="9250e-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="9250e-155">Istnieje możliwość tworzenia tablic spójnych krotek, krotek tablic, krotek podkolekcji itd.</span><span class="sxs-lookup"><span data-stu-id="9250e-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="9250e-156">Począwszy od Q # 0,3, `Unit` jest nazwą *typu* pustej krotki; `()` jest używany dla pustej *wartości*krotki.</span><span class="sxs-lookup"><span data-stu-id="9250e-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="9250e-157">Wystąpienia krotki są niezmienne.</span><span class="sxs-lookup"><span data-stu-id="9250e-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="9250e-158">Usługa Q # nie udostępnia mechanizmu zmiany zawartości spójnej kolekcji po utworzeniu.</span><span class="sxs-lookup"><span data-stu-id="9250e-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="9250e-159">Krotki są zaawansowaną koncepcją używaną przez funkcję Q # do zbierania wartości w jednej wartości, co ułatwia ich przekazywanie.</span><span class="sxs-lookup"><span data-stu-id="9250e-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="9250e-160">W szczególności, za pomocą notacji spójnej, możemy wyrazić, że każda operacja i możliwy do oddzwonienia przyjmuje dokładnie jedno wejście i zwraca dokładnie jedno wyjście.</span><span class="sxs-lookup"><span data-stu-id="9250e-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="9250e-161">Równoważna krotka singleton</span><span class="sxs-lookup"><span data-stu-id="9250e-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="9250e-162">Istnieje możliwość utworzenia pojedynczego (pojedynczego elementu) krotki, `('T1)`, takiej jak `(5)` lub `([1,2,3])`.</span><span class="sxs-lookup"><span data-stu-id="9250e-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="9250e-163">Jednakże Q # traktuje pojedynczą krotkę jako całkowicie równoważną wartości typu zamkniętego.</span><span class="sxs-lookup"><span data-stu-id="9250e-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="9250e-164">Oznacza to, że nie ma różnicy między `5` i `(5)`, lub między `5` i `(((5)))`lub między `(5, (6))` i `(5, 6)`.</span><span class="sxs-lookup"><span data-stu-id="9250e-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="9250e-165">Ta równoważność ma zastosowanie do wszystkich celów, w tym przypisania i wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="9250e-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="9250e-166">Jest tak samo ważne, aby można było pisać `(5)+3` jak do zapisu `5+3`, a oba wyrażenia będą oceniane do `8`.</span><span class="sxs-lookup"><span data-stu-id="9250e-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="9250e-167">W szczególności oznacza to, że operacja lub funkcja, której kolekcja wejściowa lub typ krotki danych wyjściowych ma jedno pole może być uważane za przyjmujące pojedynczy argument lub zwracającą pojedynczą wartość.</span><span class="sxs-lookup"><span data-stu-id="9250e-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="9250e-168">Nazywamy tę właściwość jako _równoważność spójnej kolekcji_.</span><span class="sxs-lookup"><span data-stu-id="9250e-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="9250e-169">Typy zdefiniowane przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="9250e-169">User-Defined Types</span></span>

<span data-ttu-id="9250e-170">Plik Q # może definiować nowy nazwany typ zawierający pojedynczą wartość dowolnego typu prawnego.</span><span class="sxs-lookup"><span data-stu-id="9250e-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="9250e-171">Dla dowolnego typu krotki `T`można zadeklarować nowy typ zdefiniowany przez użytkownika, który jest podtypem `T` za pomocą instrukcji `newtype`.</span><span class="sxs-lookup"><span data-stu-id="9250e-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="9250e-172">W przestrzeni nazw @"microsoft.quantum.canon", na przykład liczba zespolona jest definiowana jako typ zdefiniowany przez użytkownika:</span><span class="sxs-lookup"><span data-stu-id="9250e-172">In the @"microsoft.quantum.canon" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="9250e-173">Ta instrukcja tworzy nowy typ z dwoma anonimowymi elementami typu `Double`.</span><span class="sxs-lookup"><span data-stu-id="9250e-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="9250e-174">Poza elementami anonimowymi typy zdefiniowane przez użytkownika obsługują również nazwane elementy w przypadku Q # w wersji 0,7 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="9250e-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="9250e-175">Można na przykład nazwać elementy do `Re` dla podwójnego reprezentowania rzeczywistej części liczby zespolonej i `Im` dla części urojonej:</span><span class="sxs-lookup"><span data-stu-id="9250e-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="9250e-176">Nazewnictwo jednego elementu w typie zdefiniowanym przez użytkownika nie oznacza, że wszystkie elementy muszą mieć nazwę, a także jest obsługiwana żadna kombinacja elementów nazwanych i nienazwanych.</span><span class="sxs-lookup"><span data-stu-id="9250e-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="9250e-177">Ponadto elementy wewnętrzne mogą być nazywane.</span><span class="sxs-lookup"><span data-stu-id="9250e-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="9250e-178">Typ `Nested`, jak zdefiniowano poniżej, ma `(Double, (Int, String))`typ podstawowy, dla którego tylko element typu `Int` ma nazwę i wszystkie pozostałe elementy są anonimowe.</span><span class="sxs-lookup"><span data-stu-id="9250e-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="9250e-179">Elementy nazwane mają zalety, do których można uzyskiwać dostęp bezpośrednio za pośrednictwem operatora dostępu `::`.</span><span class="sxs-lookup"><span data-stu-id="9250e-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="9250e-180">Aby można było uzyskać dostęp do anonimowych elementów z drugiej strony, najpierw musi zostać wyodrębniona wartość opakowana przy użyciu operatora przyrostkowego `!`.</span><span class="sxs-lookup"><span data-stu-id="9250e-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="9250e-181">Operator "unotocz" `!`, umożliwia wyodrębnienie wartości zawartej w typie zdefiniowanym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9250e-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="9250e-182">Typ takiego wyrażenia "unotoka" jest typem podstawowym typu zdefiniowanego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9250e-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintMsg (value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="9250e-183">Operator rozwinięcia odpakuje dokładnie jedną warstwę zawijania.</span><span class="sxs-lookup"><span data-stu-id="9250e-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="9250e-184">Wielokrotne operatory odwinięcia mogą być używane w celu uzyskania dostępu do wartości przepakowanej wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="9250e-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="9250e-185">Na wystąpienie:</span><span class="sxs-lookup"><span data-stu-id="9250e-185">For instance:</span></span>

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

<span data-ttu-id="9250e-186">Aby uzyskać więcej informacji, zapoznaj się z sekcją dotyczącą [niezawijania wyrażeń](xref:microsoft.quantum.language.expressions#unwrap-expressions) i [operatorów](xref:microsoft.quantum.language.expressions#operator-precedence) .</span><span class="sxs-lookup"><span data-stu-id="9250e-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="9250e-187">Wartości typu zdefiniowanego przez użytkownika można utworzyć, wywołując odpowiedni Konstruktor typów:</span><span class="sxs-lookup"><span data-stu-id="9250e-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="9250e-188">Alternatywnie nowe wartości można tworzyć z istniejących przy użyciu [wyrażeń Copy-and-Update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span><span class="sxs-lookup"><span data-stu-id="9250e-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="9250e-189">Podobnie jak w przypadku tablic, takie wyrażenia kopiują wszystkie wartości elementu oryginalnego wyrażenia, z wyjątkiem określonych nazwanych elementów.</span><span class="sxs-lookup"><span data-stu-id="9250e-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="9250e-190">Dla tych wartości są ustawiane na te, które zostały zdefiniowane po prawej stronie wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="9250e-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="9250e-191">Wszystkie inne konstrukcje języka, takie jak przykładowe [instrukcje Update-and-Reassign](xref:microsoft.quantum.language.statements#update-and-reassign-statement), które są dostępne dla elementów tablicy istnieje dla elementów nazwanych w typach zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9250e-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="9250e-192">Typy zdefiniowane przez użytkownika mogą być używane wszędzie tam, gdzie można korzystać z dowolnego innego typu.</span><span class="sxs-lookup"><span data-stu-id="9250e-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="9250e-193">W szczególności można zdefiniować tablicę typu zdefiniowanego przez użytkownika i dołączenia typu zdefiniowanego przez użytkownika jako elementu typu krotki.</span><span class="sxs-lookup"><span data-stu-id="9250e-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="9250e-194">Nie można tworzyć struktur typów cyklicznych.</span><span class="sxs-lookup"><span data-stu-id="9250e-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="9250e-195">Oznacza to, że typ definiujący typ zdefiniowany przez użytkownika nie może być typem krotki, który zawiera element typu zdefiniowanego przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9250e-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="9250e-196">Ogólnie rzecz biorąc, typy zdefiniowane przez użytkownika mogą nie zawierać cyklicznych zależności od siebie, więc następujący zestaw definicji typu byłby niedozwolony:</span><span class="sxs-lookup"><span data-stu-id="9250e-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="9250e-197">Oprócz udostępniania krótkich aliasów dla potencjalnie skomplikowanych typów krotek, jedną istotną zaletą zdefiniowania takich typów jest możliwość udokumentowania zamiaru określonej wartości.</span><span class="sxs-lookup"><span data-stu-id="9250e-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="9250e-198">Powracanie do przykładu `Complex`może mieć również zdefiniowane współrzędne bieguna 2D jako typ zdefiniowany przez użytkownika:</span><span class="sxs-lookup"><span data-stu-id="9250e-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="9250e-199">Mimo że oba `Complex` i `Polar` mają typ podstawowy `(Double, Double)`, dwa typy są w pełni niezgodne z Q #, minimalizując ryzyko przypadkowego wywołania złożonej funkcji matematycznej ze współrzędnymi biegunowymi i odwrotnie.</span><span class="sxs-lookup"><span data-stu-id="9250e-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="9250e-200">W ten sposób zdefiniowane przez użytkownika typy mają podobną rolę jako rekordy F# na przykład.</span><span class="sxs-lookup"><span data-stu-id="9250e-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="9250e-201">Typy operacji i funkcji</span><span class="sxs-lookup"><span data-stu-id="9250e-201">Operation and Function Types</span></span>

<span data-ttu-id="9250e-202">_Operacja_ Q # jest podprocedurą Quantum.</span><span class="sxs-lookup"><span data-stu-id="9250e-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="9250e-203">Oznacza to, że jest to procedura, która zawiera operacje Quantum.</span><span class="sxs-lookup"><span data-stu-id="9250e-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="9250e-204">_Funkcja_ Q # to klasyczna procedura użyta w algorytmie Quantum.</span><span class="sxs-lookup"><span data-stu-id="9250e-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="9250e-205">Może zawierać kod klasyczny, ale nie ma operacji Quantum.</span><span class="sxs-lookup"><span data-stu-id="9250e-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="9250e-206">W przeciwnym razie funkcje nie mogą przydzielić ani zażyczyć qubits ani nie mogą wywoływać operacji.</span><span class="sxs-lookup"><span data-stu-id="9250e-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="9250e-207">Można jednak przekazać im operacje lub qubits do przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="9250e-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="9250e-208">Funkcje są więc całkowicie deterministyczne w sensie, że wywołanie ich przy użyciu tych samych argumentów zawsze da ten sam wynik.</span><span class="sxs-lookup"><span data-stu-id="9250e-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="9250e-209">Razem operacje i funkcje _są wywoływane._</span><span class="sxs-lookup"><span data-stu-id="9250e-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="9250e-210">Poniżej znajdują się [przykłady](#examples) poniżej.</span><span class="sxs-lookup"><span data-stu-id="9250e-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="9250e-211">Wszystkie wywoływane wartości Q # są traktowane jako dane wejściowe i zwracają pojedynczą wartość jako dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="9250e-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="9250e-212">Zarówno wartość wejściowa, jak i wyjściowa mogą być krotki.</span><span class="sxs-lookup"><span data-stu-id="9250e-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="9250e-213">Liczba wywoływanych, które nie mają zwracanych wyników `Unit`.</span><span class="sxs-lookup"><span data-stu-id="9250e-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="9250e-214">Możliwe do nadania, że żadne dane wejściowe nie przyjmują pustej kolekcji jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="9250e-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="9250e-215">Typ podstawowy dla każdego elementu, który można wywołać, jest zapisywana jako `('Tinput => 'Tresult)` lub `('Tinput -> 'Tresult)`, gdzie zarówno `'Tinput`, jak i `'Tresult` są typami.</span><span class="sxs-lookup"><span data-stu-id="9250e-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="9250e-216">Pierwszy formularz z `=>`jest używany do operacji; Drugi formularz z `->`dla funkcji.</span><span class="sxs-lookup"><span data-stu-id="9250e-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="9250e-217">Na przykład `((Qubit, Pauli) => Result)` reprezentuje sygnaturę dla możliwej operacji pomiaru pojedynczej qubit.</span><span class="sxs-lookup"><span data-stu-id="9250e-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="9250e-218">Typy funkcji są w pełni określone przez ich sygnaturę.</span><span class="sxs-lookup"><span data-stu-id="9250e-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="9250e-219">Na przykład funkcja, która oblicza sinus kąta, będzie miała typ `(Double -> Double)`.</span><span class="sxs-lookup"><span data-stu-id="9250e-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="9250e-220">Operacje — ale nie funkcje — mają pewne dodatkowe _cechy_ , które są wyrażane jako część typu operacji.</span><span class="sxs-lookup"><span data-stu-id="9250e-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="9250e-221">Takie charakterystyki zawierają informacje o tym, co funktory operacja obsługuje.</span><span class="sxs-lookup"><span data-stu-id="9250e-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="9250e-222">Funktory są operacjami, które generują specjalizację operacji podstawowej; Zobacz [funktory](#functors), poniżej.</span><span class="sxs-lookup"><span data-stu-id="9250e-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="9250e-223">Typy operacji są określane przez ich typ danych wejściowych, typ danych wyjściowych i ich cechy.</span><span class="sxs-lookup"><span data-stu-id="9250e-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="9250e-224">Aby wymagać pomocy technicznej dla `Controlled` i/lub `Adjoint` Funktor w typie operacji, musimy dodać adnotację wskazującą odpowiednie cechy.</span><span class="sxs-lookup"><span data-stu-id="9250e-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="9250e-225">Adnotacja `is Ctl` na przykład wskazuje, że operacja jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="9250e-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="9250e-226">Jeśli chcemy wymagać, aby operacja tego typu obsługiwała zarówno `Adjoint`, jak i `Controlled` Funktor, możemy to zrobić jako `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="9250e-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="9250e-227">Charakterystyki używanej operacji `Adj` i `Ctl` ściśle wymawiają dwa wstępnie zdefiniowane zestawy etykiet, gdzie każda etykieta wskazuje konkretne właściwości operacji, takie jak np. Pomoc techniczna dla określonego Funktor.</span><span class="sxs-lookup"><span data-stu-id="9250e-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="9250e-228">W związku z tym `+` jest używany do wskazania Unii tych dwóch zestawów, a `*` jest używany do wskazania przedziału, tj. etykiet wspólnych dla obu zestawów.</span><span class="sxs-lookup"><span data-stu-id="9250e-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="9250e-229">Na przykład operacja Pauli `X` ma typ `(Qubit => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="9250e-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="9250e-230">Typ operacji, która nie obsługuje żadnej funktory, jest określany za pomocą samego typu danych wejściowych i wyjściowych, bez dodatkowej adnotacji.</span><span class="sxs-lookup"><span data-stu-id="9250e-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="9250e-231">Funkcje i operacje sparametryzowane typu</span><span class="sxs-lookup"><span data-stu-id="9250e-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="9250e-232">Możliwe do napisania typy mogą zawierać parametry typu.</span><span class="sxs-lookup"><span data-stu-id="9250e-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="9250e-233">Parametry typu są wskazywane przez symbol poprzedzony pojedynczym cudzysłowem; na przykład `'A` jest dozwolonym parametrem typu.</span><span class="sxs-lookup"><span data-stu-id="9250e-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="9250e-234">Parametr typu może pojawić się więcej niż raz w pojedynczym podpisie.</span><span class="sxs-lookup"><span data-stu-id="9250e-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="9250e-235">Na przykład funkcja, która stosuje inną funkcję do każdego elementu tablicy i zwraca zebrane wyniki, ma `(('A[], 'A->'A) -> 'A[])`sygnatur.</span><span class="sxs-lookup"><span data-stu-id="9250e-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="9250e-236">Podobnie funkcja, która zwraca skład dwóch operacji, może mieć sygnaturę `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span><span class="sxs-lookup"><span data-stu-id="9250e-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="9250e-237">W przypadku wywołania sparametryzowanego typu, wszystkie argumenty, które mają ten sam parametr typu, muszą być tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="9250e-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="9250e-238">Funkcja Q # nie udostępnia mechanizmu ograniczenia możliwych typów, które mogą zostać zastąpione dla parametru typu.</span><span class="sxs-lookup"><span data-stu-id="9250e-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="9250e-239">Zgodność typów</span><span class="sxs-lookup"><span data-stu-id="9250e-239">Type Compatibility</span></span>

<span data-ttu-id="9250e-240">Operacja z dodatkowymi obsługiwanymi funktory może być używana wszędzie tam, gdzie operacja jest mniejsza niż funktory, ale oczekiwano tego samego podpisu.</span><span class="sxs-lookup"><span data-stu-id="9250e-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="9250e-241">Na przykład operacja typu `(Qubit => Unit is Adj)` może być używana wszędzie tam, gdzie jest oczekiwana operacja typu `(Qubit => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="9250e-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="9250e-242">Q # jest współwariantem w odniesieniu do możliwego do zwrócenia typu zwracanego: wywoływany, który zwraca typ `'A` jest zgodny z tym samym typem danych wejściowych i typem wyniku, który `'A` jest zgodny z.</span><span class="sxs-lookup"><span data-stu-id="9250e-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="9250e-243">Q # jest kontrawariantne w odniesieniu do typów danych wejściowych: wywoływanie, który przyjmuje typ `'A` jako dane wejściowe jest zgodny z wywoływanym z tym samym typem wyniku i typem danych wejściowych zgodnym z `'A`.</span><span class="sxs-lookup"><span data-stu-id="9250e-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="9250e-244">Oznacza to, że podano następujące definicje:</span><span class="sxs-lookup"><span data-stu-id="9250e-244">That is, given the following definitions:</span></span>

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="9250e-245">spełnione są następujące kwestie:</span><span class="sxs-lookup"><span data-stu-id="9250e-245">the following are true:</span></span>

- <span data-ttu-id="9250e-246">`ConjugateInvertibleWith` operacji może być wywołana z argumentem `inner` `Invertible` lub `Unitary`.</span><span class="sxs-lookup"><span data-stu-id="9250e-246">The operation `ConjugateInvertibleWith` may be invoked with an `inner` argument of either `Invertible` or `Unitary`.</span></span>
- <span data-ttu-id="9250e-247">`ConjugateUnitaryWith` operacji może być wywołana z argumentem `inner` `Unitary`, ale nie `Invertible`.</span><span class="sxs-lookup"><span data-stu-id="9250e-247">The operation `ConjugateUnitaryWith` may be invoked with an `inner` argument of `Unitary`, but not `Invertible`.</span></span>
- <span data-ttu-id="9250e-248">Wartość typu `(Qubit[] => Unit is Adj + Ctl)` może być zwracana z `ConjugateInvertibleWith`.</span><span class="sxs-lookup"><span data-stu-id="9250e-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertibleWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9250e-249">Q # 0,3 wprowadza znaczącą różnicę w zachowaniu typów zdefiniowanych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9250e-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="9250e-250">Typy zdefiniowane przez użytkownika są traktowane jako opakowana wersja typu podstawowego, a nie jako podtyp.</span><span class="sxs-lookup"><span data-stu-id="9250e-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="9250e-251">Oznacza to, że wartość typu zdefiniowanego przez użytkownika nie jest użyteczna, gdy oczekiwana jest wartość typu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="9250e-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="9250e-252">Funktory</span><span class="sxs-lookup"><span data-stu-id="9250e-252">Functors</span></span>

<span data-ttu-id="9250e-253">Funktor w Q # to fabryka, która definiuje nową operację z innej operacji.</span><span class="sxs-lookup"><span data-stu-id="9250e-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="9250e-254">Funktory mają dostęp do implementacji operacji podstawowej podczas definiowania implementacji nowej operacji.</span><span class="sxs-lookup"><span data-stu-id="9250e-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="9250e-255">W ten sposób funktory może wykonywać bardziej złożone funkcje niż tradycyjne funkcje wyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="9250e-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="9250e-256">Funktory nie ma reprezentacji w systemie typu Q #.</span><span class="sxs-lookup"><span data-stu-id="9250e-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="9250e-257">Obecnie nie można powiązać ich ze zmienną lub przekazać ich jako argumenty.</span><span class="sxs-lookup"><span data-stu-id="9250e-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="9250e-258">Funktor jest używany przez zastosowanie go do operacji, zwracając nową operację.</span><span class="sxs-lookup"><span data-stu-id="9250e-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="9250e-259">Na przykład operacja będąca wynikiem zastosowania `Adjoint` Funktor do operacji `Y` jest zapisywana jako `Adjoint Y`.</span><span class="sxs-lookup"><span data-stu-id="9250e-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="9250e-260">Nowa operacja może następnie zostać wywołana jak każda inna operacja.</span><span class="sxs-lookup"><span data-stu-id="9250e-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="9250e-261">W tym celu `Adjoint Y(q1)` stosuje Funktor sąsiadujący do operacji `Y` w celu wygenerowania nowej operacji i stosuje tę nową operację do `q1`.</span><span class="sxs-lookup"><span data-stu-id="9250e-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="9250e-262">Podobnie `Controlled X(controls, target)` ma zastosowanie kontrolowane Funktor do operacji `X` w celu wygenerowania nowej operacji i stosuje tę nową operację do `controls` i `target`.</span><span class="sxs-lookup"><span data-stu-id="9250e-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="9250e-263">Dwa standardowe funktory w Q # są `Adjoint` i `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="9250e-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="9250e-264">Sąsiadująco</span><span class="sxs-lookup"><span data-stu-id="9250e-264">Adjoint</span></span>

<span data-ttu-id="9250e-265">W przypadku przetwarzania Quantum, sąsiadująca operacja jest złożona sprzężona operacja.</span><span class="sxs-lookup"><span data-stu-id="9250e-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="9250e-266">W przypadku operacji implementujących operator jednostki sąsiednie jest odwrotność operacji.</span><span class="sxs-lookup"><span data-stu-id="9250e-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="9250e-267">W przypadku prostej operacji, która po prostu wywołuje sekwencję innych operacji jednostkowych na zestawie qubits, sąsiadujący może być obliczany przez zastosowanie adjoints podrzędnych operacji w tym samym qubits, w odwrotnej sekwencji.</span><span class="sxs-lookup"><span data-stu-id="9250e-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="9250e-268">Po otrzymaniu wyrażenia operacji nowe wyrażenie operacji może być utworzone przy użyciu `Adjoint` Funktor.</span><span class="sxs-lookup"><span data-stu-id="9250e-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="9250e-269">Na przykład `Adjoint QFT` wyznacza sąsiadujący operacji `QFT`.</span><span class="sxs-lookup"><span data-stu-id="9250e-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="9250e-270">Nowa operacja ma ten sam podpis i typ co operacja podstawowa.</span><span class="sxs-lookup"><span data-stu-id="9250e-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="9250e-271">W szczególności Nowa operacja umożliwia również `Adjoint`i zezwala na `Controlled`, jeśli i tylko wtedy, gdy operacja podstawowa zakończyła się.</span><span class="sxs-lookup"><span data-stu-id="9250e-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="9250e-272">Sąsiadujący Funktor jest własnym odwrotnością; oznacza to, że `Adjoint Adjoint Op` jest zawsze taka sama jak `Op`.</span><span class="sxs-lookup"><span data-stu-id="9250e-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="9250e-273">Kontrolowane</span><span class="sxs-lookup"><span data-stu-id="9250e-273">Controlled</span></span>

<span data-ttu-id="9250e-274">Kontrolowana wersja operacji jest nową operacją, która efektywnie stosuje operację podstawową tylko wtedy, gdy wszystkie kontrolki qubits są w określonym stanie.</span><span class="sxs-lookup"><span data-stu-id="9250e-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="9250e-275">Jeśli kontrolka qubits znajduje się w położeniu, wówczas podstawowa operacja jest stosowana spójnie z odpowiednią częścią położenia.</span><span class="sxs-lookup"><span data-stu-id="9250e-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="9250e-276">W ten sposób kontrolowane operacje są często używane do generowania Entanglement.</span><span class="sxs-lookup"><span data-stu-id="9250e-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="9250e-277">W programie Q # kontrolowane wersje zawsze pobierają tablicę qubits kontroli, a określony stan jest zawsze przeznaczony dla wszystkich kontrolek qubits, które mają być w stanie `One` obliczeniowym (`PauliZ`), $ \ket{1}$.</span><span class="sxs-lookup"><span data-stu-id="9250e-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="9250e-278">Kontrolę w oparciu o inne Stany można osiągnąć przez zastosowanie odpowiedniej operacji jednostkowej do kontrolki qubits przed operacją kontrolowanej, a następnie zastosowanie odwrotności operacji jednostkowej po kontrolowanej operacji.</span><span class="sxs-lookup"><span data-stu-id="9250e-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="9250e-279">Na przykład zastosowanie operacji `X` do kontrolki qubit przed i po kontrolowanej operacji spowoduje, że operacja kontroluje stan `Zero` ($ \ket{0}$) dla tego qubit; zastosowanie `H` operacji przed i po nim będzie kontrolować stan `One` `PauliX`, czyli-1 eigenvalue Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$, a nie `PauliZ` `One`.</span><span class="sxs-lookup"><span data-stu-id="9250e-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="9250e-280">Po otrzymaniu wyrażenia operacji nowe wyrażenie operacji może być utworzone przy użyciu `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="9250e-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="9250e-281">Sygnatura nowej operacji jest oparta na podpisie oryginalnej operacji.</span><span class="sxs-lookup"><span data-stu-id="9250e-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="9250e-282">Typ wyniku jest taki sam, ale typ danych wejściowych jest krotką dwukrotną z tablicą qubit, która przechowuje qubit kontrolki jako pierwszy element i argumenty oryginalnej operacji jako drugi element.</span><span class="sxs-lookup"><span data-stu-id="9250e-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="9250e-283">Nowa operacja obsługuje `Controlled`i będzie obsługiwać `Adjoint`, jeśli i tylko wtedy, gdy oryginalna operacja zakończyła się.</span><span class="sxs-lookup"><span data-stu-id="9250e-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="9250e-284">Jeśli oryginalna Operacja trwała tylko z pojedynczym argumentem, w tym miejscu będzie można odtwarzać pojedynczej korelacji krotek.</span><span class="sxs-lookup"><span data-stu-id="9250e-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="9250e-285">Na przykład `Controlled X` jest kontrolowana wersja operacji `X`.</span><span class="sxs-lookup"><span data-stu-id="9250e-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="9250e-286">`X` ma `(Qubit => Unit is Adj + Ctl)`typu, dlatego `Controlled X` ma `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`typu; ze względu na równoważność spójnej kolekcji jest taka sama jak `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="9250e-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="9250e-287">Jeśli operacja podstawowa wymagała kilku argumentów, pamiętaj, aby ująć odpowiednie argumenty kontrolowanej wersji operacji w nawiasach, aby przekonwertować je na krotkę.</span><span class="sxs-lookup"><span data-stu-id="9250e-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="9250e-288">Na przykład `Controlled Rz` jest kontrolowana wersja operacji `Rz`.</span><span class="sxs-lookup"><span data-stu-id="9250e-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="9250e-289">`Rz` ma `((Double, Qubit) => Unit is Adj + Ctl)`typu, dlatego `Controlled Rz` ma `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`typu.</span><span class="sxs-lookup"><span data-stu-id="9250e-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="9250e-290">W tym celu `Controlled Rz(controls, (0.1, target))` być prawidłowym wywołaniem `Controlled Rz` (należy zauważyć nawiasy wokół `0.1, target`).</span><span class="sxs-lookup"><span data-stu-id="9250e-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="9250e-291">Innym przykładem `CNOT(control, target)` można zaimplementować jako `Controlled X([control], target)`.</span><span class="sxs-lookup"><span data-stu-id="9250e-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="9250e-292">Jeśli element docelowy powinien być kontrolowany przez 2 Control qubits (CCNOT), możemy użyć instrukcji `Controlled X([control1, control2], target)`.</span><span class="sxs-lookup"><span data-stu-id="9250e-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="9250e-293">Przykłady</span><span class="sxs-lookup"><span data-stu-id="9250e-293">Examples</span></span>

<span data-ttu-id="9250e-294">Ten przykład operacji Q # pochodzi z próbki [pomiarowej](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) .</span><span class="sxs-lookup"><span data-stu-id="9250e-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="9250e-295">W ramach operacji można przydzielić qubits i używać operacji Quantum na tych qubits, takich jak `H` i `X`:</span><span class="sxs-lookup"><span data-stu-id="9250e-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit

            set result = M(qubit);      // Measure the qubit

            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="9250e-296">Ten przykład funkcji pochodzi z przykładu [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="9250e-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="9250e-297">Zawiera czysto klasyczny kod.</span><span class="sxs-lookup"><span data-stu-id="9250e-297">It contains purely classical code.</span></span> <span data-ttu-id="9250e-298">Zobaczysz, że w przeciwieństwie do powyższego przykładu nie przydzielono żadnych qubits i nie są używane żadne operacje Quantum.</span><span class="sxs-lookup"><span data-stu-id="9250e-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="9250e-299">Jest również możliwe, aby funkcja przekazała qubits do przetwarzania, jak w tym przykładzie z przykładu [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) .</span><span class="sxs-lookup"><span data-stu-id="9250e-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="9250e-300">Qubits są przenoszone do funkcji i używane do przetwarzania, chociaż w żadnym momencie nie są modyfikowane qubit.</span><span class="sxs-lookup"><span data-stu-id="9250e-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```

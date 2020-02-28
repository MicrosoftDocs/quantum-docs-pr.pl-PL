---
title: 'Zmienne lokalne — techniki Q #'
description: 'Dowiedz się, jak definiować zmienne lokalne i korzystać z nich w Q #.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: cb6c662137c31a13c3dd6e9ca3f67879c469f788
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906869"
---
# <a name="local-variables"></a><span data-ttu-id="31932-103">Zmienne lokalne</span><span class="sxs-lookup"><span data-stu-id="31932-103">Local Variables</span></span> #

<span data-ttu-id="31932-104">Wartość dowolnego typu w Q # można przypisać do zmiennej do ponownego użycia w ramach operacji lub funkcji za pomocą słowa kluczowego `let`.</span><span class="sxs-lookup"><span data-stu-id="31932-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="31932-105">Na wystąpienie:</span><span class="sxs-lookup"><span data-stu-id="31932-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="31932-106">Przypisuje określoną tablicę operatorów Pauli do zmiennej o nazwie `measurementOperator`.</span><span class="sxs-lookup"><span data-stu-id="31932-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="31932-107">Należy zauważyć, że nie trzeba jawnie określać typu naszej nowej zmiennej, ponieważ wyrażenie po prawej stronie instrukcji `let` jest niejednoznaczne i typ jest wnioskowany przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="31932-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="31932-108">Zmienne w Q # są *niezmienne*, co oznacza, że gdy zmienna została zdefiniowana w ten sposób, nie można jej zmienić w jakikolwiek sposób.</span><span class="sxs-lookup"><span data-stu-id="31932-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="31932-109">Pozwala to na kilka optymalizacji, w tym optymalizację klasycznej logiki działającej na zmienne, które mają być zmieniane w celu zastosowania wariantu `Adjoint` operacji.</span><span class="sxs-lookup"><span data-stu-id="31932-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="31932-110">Zmienne zdefiniowane za pomocą powyższego powiązania `let` są lokalne dla określonego zakresu, takie jak treść operacji lub zawartość pętli `for`.</span><span class="sxs-lookup"><span data-stu-id="31932-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="31932-111">Zmienność</span><span class="sxs-lookup"><span data-stu-id="31932-111">Mutability</span></span> ##

<span data-ttu-id="31932-112">Alternatywnie, aby utworzyć zmienną o `let`, słowo kluczowe `mutable` utworzy specjalną zmienną modyfikowalną, którą można ponownie powiązać po jej początkowym utworzeniu za pomocą słowa kluczowego `set`.</span><span class="sxs-lookup"><span data-stu-id="31932-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="31932-113">Wszystkie typy w Q #, łącznie z tablicami, są zgodne z semantyką wartości.</span><span class="sxs-lookup"><span data-stu-id="31932-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="31932-114">W szczególności nie jest możliwe aktualizowanie elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="31932-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="31932-115">Aby zmodyfikować istniejącą tablicę, należy korzystać z mechanizmu kopiowania i aktualizowania podobnie jak dla rekordów w programie F#.</span><span class="sxs-lookup"><span data-stu-id="31932-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="31932-116">Za pomocą narzędzi biblioteki dla tablic dostępnych w [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)można na przykład łatwo zdefiniować funkcję, która zwraca tablicę Paul, gdzie Pauli przy indeksie `i` przyjmuje daną wartość, a wszystkie inne wpisy są tożsamość:</span><span class="sxs-lookup"><span data-stu-id="31932-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="31932-117">Dowiesz się więcej na temat pracy z tablicami podczas omawiania instrukcji i wyrażeń Q #.</span><span class="sxs-lookup"><span data-stu-id="31932-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="31932-118">Zmienność w elemencie Q # to koncepcja, która ma zastosowanie do *symbolu* , a nie typu lub wartości.</span><span class="sxs-lookup"><span data-stu-id="31932-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="31932-119">W przeciwnym razie nie ma reprezentacji w systemie typów, niejawnie lub niejawnie, i niezależnie od tego, czy powiązanie jest modyfikowalne (wskazywane przez słowo kluczowe `mutable`) czy niezmienne (zgodnie z definicją `let`) nie zmienia typu powiązanych zmiennych.</span><span class="sxs-lookup"><span data-stu-id="31932-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="31932-120">Zapewnia to istotny sposób izolowania zmienność w wyspecjalizowanych funkcjach i operacjach.</span><span class="sxs-lookup"><span data-stu-id="31932-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="31932-121">W szczególności, chociaż w przypadku operacji, która używa zmiennej modyfikowalnej nie może być automatycznie generowana, funkcja autogeneracji działa prawidłowo w przypadku operacji wywołującej funkcję, która używa zmienność.</span><span class="sxs-lookup"><span data-stu-id="31932-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="31932-122">Z tego powodu dobrym sposobem jest zapewnienie funkcji i operacji, które wykorzystują zmienność jako krótkie i kompaktowe, tak aby pozostała część programu Quantum mogła być napisywana przy użyciu standardowych, niezmiennych zmiennych.</span><span class="sxs-lookup"><span data-stu-id="31932-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="31932-123">Dekonstrukcja</span><span class="sxs-lookup"><span data-stu-id="31932-123">Deconstruction</span></span> ##

<span data-ttu-id="31932-124">Oprócz przypisywania pojedynczej zmiennej, `let` i `mutable` słów kluczowych — lub w rzeczywistości innych konstrukcji powiązań — umożliwia także rozpakowywanie zawartości [typu krotki](xref:microsoft.quantum.language.type-model#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="31932-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="31932-125">Przypisanie tego formularza jest określane w celu *odtworzenia* elementów tej krotki.</span><span class="sxs-lookup"><span data-stu-id="31932-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="31932-126">Na przykład w przypadku modelowania terminu w hamiltonian przez krotkę możemy użyć dekonstrukcji, aby uzyskać dostęp do różnych danych, które są potrzebne do symulowania w tym okresie:</span><span class="sxs-lookup"><span data-stu-id="31932-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```



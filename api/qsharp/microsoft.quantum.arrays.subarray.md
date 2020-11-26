---
uid: Microsoft.Quantum.Arrays.Subarray
title: Funkcja subarray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: cf72f04421b277ce64354d1eccec11cbc61d78cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220165"
---
# <a name="subarray-function"></a><span data-ttu-id="bb079-102">Funkcja subarray</span><span class="sxs-lookup"><span data-stu-id="bb079-102">Subarray function</span></span>

<span data-ttu-id="bb079-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bb079-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bb079-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb079-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb079-105">Pobiera tablicę i listę lokalizacji i tworzy nową tablicę utworzoną z elementów oryginalnej tablicy, które pasują do określonych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="bb079-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="bb079-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bb079-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="bb079-107">indeksy: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bb079-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="bb079-108">Lista liczb całkowitych, która jest używana do definiowania podtablicy.</span><span class="sxs-lookup"><span data-stu-id="bb079-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="bb079-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="bb079-109">array : 'T[]</span></span>

<span data-ttu-id="bb079-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="bb079-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="bb079-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="bb079-111">Output : 'T[]</span></span>

<span data-ttu-id="bb079-112">Tablica `out` elementów, których indeksy odpowiadają podtablicy, takiej jak `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="bb079-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bb079-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bb079-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bb079-114">'C</span><span class="sxs-lookup"><span data-stu-id="bb079-114">'T</span></span>

<span data-ttu-id="bb079-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="bb079-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb079-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bb079-116">Remarks</span></span>

<span data-ttu-id="bb079-117">Funkcja jest definiowana dla typów ogólnych, tzn., gdy mamy tablicę `'T[]` i listę lokalizacji `Int[]` definiujących podtablicę.</span><span class="sxs-lookup"><span data-stu-id="bb079-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="bb079-118">Konstrukcja podtablicy jest oparta na generowaniu nowej, głębokiej kopii danej tablicy, w przeciwieństwie do obsługi odwołań.</span><span class="sxs-lookup"><span data-stu-id="bb079-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="bb079-119">Jeśli `Length(indices) < Length(array)` Ta funkcja zwróci podzestaw elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="bb079-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="bb079-120">Z drugiej strony, jeśli `indices` zawiera powtarzające się elementy, odpowiednie elementy `array` są również powtarzane.</span><span class="sxs-lookup"><span data-stu-id="bb079-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="bb079-121">Jeśli `indices` i `array` ma tę samą długość, ta funkcja zapewnia permutacje `array` .</span><span class="sxs-lookup"><span data-stu-id="bb079-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>
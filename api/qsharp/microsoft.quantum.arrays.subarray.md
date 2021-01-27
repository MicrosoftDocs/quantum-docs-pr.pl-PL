---
uid: Microsoft.Quantum.Arrays.Subarray
title: Funkcja subarray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845433"
---
# <a name="subarray-function"></a><span data-ttu-id="dc0f2-102">Funkcja subarray</span><span class="sxs-lookup"><span data-stu-id="dc0f2-102">Subarray function</span></span>

<span data-ttu-id="dc0f2-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dc0f2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dc0f2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc0f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc0f2-105">Pobiera tablicę i listę lokalizacji i tworzy nową tablicę utworzoną z elementów oryginalnej tablicy, które pasują do określonych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="dc0f2-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="dc0f2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dc0f2-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="dc0f2-107">indeksy: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dc0f2-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="dc0f2-108">Lista liczb całkowitych, która jest używana do definiowania podtablicy.</span><span class="sxs-lookup"><span data-stu-id="dc0f2-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="dc0f2-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="dc0f2-109">array : 'T[]</span></span>

<span data-ttu-id="dc0f2-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="dc0f2-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="dc0f2-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="dc0f2-111">Output : 'T[]</span></span>

<span data-ttu-id="dc0f2-112">Tablica `out` elementów, których indeksy odpowiadają podtablicy, takiej jak `out[idx] == array[indices[idx]]` .</span><span class="sxs-lookup"><span data-stu-id="dc0f2-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dc0f2-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="dc0f2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc0f2-114">'C</span><span class="sxs-lookup"><span data-stu-id="dc0f2-114">'T</span></span>

<span data-ttu-id="dc0f2-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="dc0f2-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc0f2-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dc0f2-116">Remarks</span></span>

<span data-ttu-id="dc0f2-117">Funkcja jest definiowana dla typów ogólnych, tzn., gdy mamy tablicę `'T[]` i listę lokalizacji `Int[]` definiujących podtablicę.</span><span class="sxs-lookup"><span data-stu-id="dc0f2-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="dc0f2-118">Konstrukcja podtablicy jest oparta na generowaniu nowej, głębokiej kopii danej tablicy, w przeciwieństwie do obsługi odwołań.</span><span class="sxs-lookup"><span data-stu-id="dc0f2-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="dc0f2-119">Jeśli `Length(indices) < Length(array)` Ta funkcja zwróci podzestaw elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="dc0f2-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="dc0f2-120">Z drugiej strony, jeśli `indices` zawiera powtarzające się elementy, odpowiednie elementy `array` są również powtarzane.</span><span class="sxs-lookup"><span data-stu-id="dc0f2-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="dc0f2-121">Jeśli `indices` i `array` ma tę samą długość, ta funkcja zapewnia permutacje `array` .</span><span class="sxs-lookup"><span data-stu-id="dc0f2-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>
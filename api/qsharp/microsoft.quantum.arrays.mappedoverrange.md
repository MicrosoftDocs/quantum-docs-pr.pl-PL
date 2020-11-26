---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220692"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="bd098-102">MappedOverRange, funkcja</span><span class="sxs-lookup"><span data-stu-id="bd098-102">MappedOverRange function</span></span>

<span data-ttu-id="bd098-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bd098-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bd098-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd098-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd098-105">Uwzględniając zakres i funkcję, która przyjmuje liczbę całkowitą jako dane wejściowe, zwraca nową tablicę, która składa się z obrazów wartości zakresu w ramach funkcji.</span><span class="sxs-lookup"><span data-stu-id="bd098-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="bd098-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bd098-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="bd098-107">Maper: [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="bd098-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="bd098-108">Funkcja z `Int` do `'T` , która jest używana do mapowania wartości zakresu.</span><span class="sxs-lookup"><span data-stu-id="bd098-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="bd098-109">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="bd098-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="bd098-110">Zakres liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="bd098-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="bd098-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="bd098-111">Output : 'T[]</span></span>

<span data-ttu-id="bd098-112">Tablica `'T[]` elementów, które są mapowane przez `mapper` funkcję.</span><span class="sxs-lookup"><span data-stu-id="bd098-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bd098-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bd098-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd098-114">'C</span><span class="sxs-lookup"><span data-stu-id="bd098-114">'T</span></span>

<span data-ttu-id="bd098-115">Typ wyniku `mapper` funkcji.</span><span class="sxs-lookup"><span data-stu-id="bd098-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd098-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bd098-116">Remarks</span></span>

<span data-ttu-id="bd098-117">Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy funkcję, `mapper: Int -> 'T` możemy zmapować wartości zakresu i utworzyć tablicę typu `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="bd098-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd098-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bd098-118">See Also</span></span>

- [<span data-ttu-id="bd098-119">Microsoft. Quantum. Arrays. zmapowane</span><span class="sxs-lookup"><span data-stu-id="bd098-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)
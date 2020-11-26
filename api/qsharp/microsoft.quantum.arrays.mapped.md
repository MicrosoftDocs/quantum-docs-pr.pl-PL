---
uid: Microsoft.Quantum.Arrays.Mapped
title: Mapowana funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220743"
---
# <a name="mapped-function"></a><span data-ttu-id="88b37-102">Mapowana funkcja</span><span class="sxs-lookup"><span data-stu-id="88b37-102">Mapped function</span></span>

<span data-ttu-id="88b37-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="88b37-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="88b37-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88b37-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88b37-105">Dana tablica i funkcja, która jest zdefiniowana dla elementów tablicy, zwraca nową tablicę, która składa się z obrazów oryginalnej tablicy w funkcji.</span><span class="sxs-lookup"><span data-stu-id="88b37-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="88b37-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="88b37-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="88b37-107">Maper: brak > ' U</span><span class="sxs-lookup"><span data-stu-id="88b37-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="88b37-108">Funkcja z `'T` do `'U` , która jest używana do mapowania elementów.</span><span class="sxs-lookup"><span data-stu-id="88b37-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="88b37-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="88b37-109">array : 'T[]</span></span>

<span data-ttu-id="88b37-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="88b37-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="88b37-111">Wynik: "U []</span><span class="sxs-lookup"><span data-stu-id="88b37-111">Output : 'U[]</span></span>

<span data-ttu-id="88b37-112">Tablica `'U[]` elementów, które są mapowane przez `mapper` funkcję.</span><span class="sxs-lookup"><span data-stu-id="88b37-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="88b37-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="88b37-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="88b37-114">'C</span><span class="sxs-lookup"><span data-stu-id="88b37-114">'T</span></span>

<span data-ttu-id="88b37-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="88b37-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="88b37-116">' U</span><span class="sxs-lookup"><span data-stu-id="88b37-116">'U</span></span>

<span data-ttu-id="88b37-117">Typ wyniku `mapper` funkcji.</span><span class="sxs-lookup"><span data-stu-id="88b37-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="88b37-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="88b37-118">Remarks</span></span>

<span data-ttu-id="88b37-119">Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i funkcję, `mapper: 'T -> 'U` możemy zmapować elementy tablicy i utworzyć nową tablicę typu `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="88b37-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>
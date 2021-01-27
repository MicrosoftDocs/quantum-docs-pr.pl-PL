---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845668"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="02840-102">MappedByIndex, funkcja</span><span class="sxs-lookup"><span data-stu-id="02840-102">MappedByIndex function</span></span>

<span data-ttu-id="02840-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="02840-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="02840-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02840-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02840-105">Dana tablica i funkcja, która jest zdefiniowana dla indeksowanych elementów tablicy, zwraca nową tablicę, która składa się z obrazów oryginalnej tablicy w funkcji.</span><span class="sxs-lookup"><span data-stu-id="02840-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="02840-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="02840-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="02840-107">Maper: ([int](xref:microsoft.quantum.lang-ref.int), t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="02840-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="02840-108">Funkcja z `(Int, 'T)` do `'U` , która jest używana do mapowania elementów i ich indeksów.</span><span class="sxs-lookup"><span data-stu-id="02840-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="02840-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="02840-109">array : 'T[]</span></span>

<span data-ttu-id="02840-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="02840-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="02840-111">Wynik: "U []</span><span class="sxs-lookup"><span data-stu-id="02840-111">Output : 'U[]</span></span>

<span data-ttu-id="02840-112">Tablica `'U[]` elementów, które są mapowane przez `mapper` funkcję.</span><span class="sxs-lookup"><span data-stu-id="02840-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="02840-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="02840-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02840-114">'C</span><span class="sxs-lookup"><span data-stu-id="02840-114">'T</span></span>

<span data-ttu-id="02840-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="02840-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="02840-116">' U</span><span class="sxs-lookup"><span data-stu-id="02840-116">'U</span></span>

<span data-ttu-id="02840-117">Typ wyniku `mapper` funkcji.</span><span class="sxs-lookup"><span data-stu-id="02840-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="02840-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="02840-118">Example</span></span>

<span data-ttu-id="02840-119">Dwa następujące wiersze są równoważne:</span><span class="sxs-lookup"><span data-stu-id="02840-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="02840-120">oraz</span><span class="sxs-lookup"><span data-stu-id="02840-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="02840-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="02840-121">See Also</span></span>

- [<span data-ttu-id="02840-122">Microsoft. Quantum. Arrays. zmapowane</span><span class="sxs-lookup"><span data-stu-id="02840-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)
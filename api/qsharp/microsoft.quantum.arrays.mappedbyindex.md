---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719052"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="8f30e-102">MappedByIndex, funkcja</span><span class="sxs-lookup"><span data-stu-id="8f30e-102">MappedByIndex function</span></span>

<span data-ttu-id="8f30e-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8f30e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8f30e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8f30e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8f30e-105">Dana tablica i funkcja, która jest zdefiniowana dla indeksowanych elementów tablicy, zwraca nową tablicę, która składa się z obrazów oryginalnej tablicy w funkcji.</span><span class="sxs-lookup"><span data-stu-id="8f30e-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="8f30e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8f30e-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="8f30e-107">Maper: ([int](xref:microsoft.quantum.lang-ref.int), t)-> ' U</span><span class="sxs-lookup"><span data-stu-id="8f30e-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="8f30e-108">Funkcja z `(Int, 'T)` do `'U` , która jest używana do mapowania elementów i ich indeksów.</span><span class="sxs-lookup"><span data-stu-id="8f30e-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="8f30e-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="8f30e-109">array : 'T[]</span></span>

<span data-ttu-id="8f30e-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="8f30e-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="8f30e-111">Wynik: "U []</span><span class="sxs-lookup"><span data-stu-id="8f30e-111">Output : 'U[]</span></span>

<span data-ttu-id="8f30e-112">Tablica `'U[]` elementów, które są mapowane przez `mapper` funkcję.</span><span class="sxs-lookup"><span data-stu-id="8f30e-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8f30e-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8f30e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f30e-114">'C</span><span class="sxs-lookup"><span data-stu-id="8f30e-114">'T</span></span>

<span data-ttu-id="8f30e-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="8f30e-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="8f30e-116">' U</span><span class="sxs-lookup"><span data-stu-id="8f30e-116">'U</span></span>

<span data-ttu-id="8f30e-117">Typ wyniku `mapper` funkcji.</span><span class="sxs-lookup"><span data-stu-id="8f30e-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f30e-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8f30e-118">See Also</span></span>

- [<span data-ttu-id="8f30e-119">Microsoft. Quantum. Arrays. zmapowane</span><span class="sxs-lookup"><span data-stu-id="8f30e-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)
---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operacja ForEach
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: b362d28e77c8dea2b3daeed4a4d605e1dd42e487
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221151"
---
# <a name="foreach-operation"></a><span data-ttu-id="ad8eb-102">Operacja ForEach</span><span class="sxs-lookup"><span data-stu-id="ad8eb-102">ForEach operation</span></span>

<span data-ttu-id="ad8eb-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ad8eb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ad8eb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad8eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad8eb-105">Dana tablica i operacja, która jest zdefiniowana dla elementów tablicy, zwraca nową tablicę, która składa się z obrazów oryginalnej tablicy w ramach operacji.</span><span class="sxs-lookup"><span data-stu-id="ad8eb-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="ad8eb-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ad8eb-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="ad8eb-107">Akcja: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="ad8eb-107">action : 'T => 'U</span></span> 

<span data-ttu-id="ad8eb-108">Operacja z `'T` do do `'U` , która jest stosowana do każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="ad8eb-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="ad8eb-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="ad8eb-109">array : 'T[]</span></span>

<span data-ttu-id="ad8eb-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="ad8eb-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="ad8eb-111">Wynik: "U []</span><span class="sxs-lookup"><span data-stu-id="ad8eb-111">Output : 'U[]</span></span>

<span data-ttu-id="ad8eb-112">Tablica `'U[]` elementów, które są mapowane przez `action` operację.</span><span class="sxs-lookup"><span data-stu-id="ad8eb-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ad8eb-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ad8eb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ad8eb-114">'C</span><span class="sxs-lookup"><span data-stu-id="ad8eb-114">'T</span></span>

<span data-ttu-id="ad8eb-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="ad8eb-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="ad8eb-116">' U</span><span class="sxs-lookup"><span data-stu-id="ad8eb-116">'U</span></span>

<span data-ttu-id="ad8eb-117">Typ wyniku `action` operacji.</span><span class="sxs-lookup"><span data-stu-id="ad8eb-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad8eb-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ad8eb-118">Remarks</span></span>

<span data-ttu-id="ad8eb-119">Operacja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i operację, `action : 'T -> 'U` możemy zmapować elementy tablicy i utworzyć nową tablicę typu `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="ad8eb-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>
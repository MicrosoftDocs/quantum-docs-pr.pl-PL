---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operacja ForEach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848586"
---
# <a name="foreach-operation"></a><span data-ttu-id="6f286-102">Operacja ForEach</span><span class="sxs-lookup"><span data-stu-id="6f286-102">ForEach operation</span></span>

<span data-ttu-id="6f286-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6f286-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6f286-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f286-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f286-105">Dana tablica i operacja, która jest zdefiniowana dla elementów tablicy, zwraca nową tablicę, która składa się z obrazów oryginalnej tablicy w ramach operacji.</span><span class="sxs-lookup"><span data-stu-id="6f286-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="6f286-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6f286-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="6f286-107">Akcja: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="6f286-107">action : 'T => 'U</span></span> 

<span data-ttu-id="6f286-108">Operacja z `'T` do do `'U` , która jest stosowana do każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="6f286-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="6f286-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="6f286-109">array : 'T[]</span></span>

<span data-ttu-id="6f286-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="6f286-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="6f286-111">Wynik: "U []</span><span class="sxs-lookup"><span data-stu-id="6f286-111">Output : 'U[]</span></span>

<span data-ttu-id="6f286-112">Tablica `'U[]` elementów, które są mapowane przez `action` operację.</span><span class="sxs-lookup"><span data-stu-id="6f286-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6f286-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6f286-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6f286-114">'C</span><span class="sxs-lookup"><span data-stu-id="6f286-114">'T</span></span>

<span data-ttu-id="6f286-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="6f286-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="6f286-116">' U</span><span class="sxs-lookup"><span data-stu-id="6f286-116">'U</span></span>

<span data-ttu-id="6f286-117">Typ wyniku `action` operacji.</span><span class="sxs-lookup"><span data-stu-id="6f286-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f286-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6f286-118">Remarks</span></span>

<span data-ttu-id="6f286-119">Operacja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i operację, `action : 'T -> 'U` możemy zmapować elementy tablicy i utworzyć nową tablicę typu `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="6f286-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>
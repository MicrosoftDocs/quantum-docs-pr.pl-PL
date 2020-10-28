---
uid: Microsoft.Quantum.Arrays.Count
title: Count — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 408a4a42dda6a4827db6d5865e2b4b8a8df5b37a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719400"
---
# <a name="count-function"></a><span data-ttu-id="47e0f-102">Count — funkcja</span><span class="sxs-lookup"><span data-stu-id="47e0f-102">Count function</span></span>

<span data-ttu-id="47e0f-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="47e0f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="47e0f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47e0f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47e0f-105">Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, zwraca liczbę elementów tablicy, która składa się z tych elementów, które spełniają predykat.</span><span class="sxs-lookup"><span data-stu-id="47e0f-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="47e0f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="47e0f-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="47e0f-107">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="47e0f-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="47e0f-108">Funkcja z `'T` do wartości logicznej, która jest używana do filtrowania elementów.</span><span class="sxs-lookup"><span data-stu-id="47e0f-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="47e0f-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="47e0f-109">array : 'T[]</span></span>

<span data-ttu-id="47e0f-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="47e0f-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="47e0f-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47e0f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47e0f-112">Liczba elementów w `array` , które spełniają predykat.</span><span class="sxs-lookup"><span data-stu-id="47e0f-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="47e0f-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="47e0f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47e0f-114">'C</span><span class="sxs-lookup"><span data-stu-id="47e0f-114">'T</span></span>

<span data-ttu-id="47e0f-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="47e0f-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="47e0f-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="47e0f-116">Remarks</span></span>

<span data-ttu-id="47e0f-117">Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i predykat `'T -> Bool` możemy filtrować elementy.</span><span class="sxs-lookup"><span data-stu-id="47e0f-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>
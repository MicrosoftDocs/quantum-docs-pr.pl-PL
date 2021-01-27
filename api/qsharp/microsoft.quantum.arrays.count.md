---
uid: Microsoft.Quantum.Arrays.Count
title: Count — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842847"
---
# <a name="count-function"></a><span data-ttu-id="c1834-102">Count — funkcja</span><span class="sxs-lookup"><span data-stu-id="c1834-102">Count function</span></span>

<span data-ttu-id="c1834-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c1834-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c1834-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c1834-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c1834-105">Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, zwraca liczbę elementów tablicy, która składa się z tych elementów, które spełniają predykat.</span><span class="sxs-lookup"><span data-stu-id="c1834-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="c1834-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c1834-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="c1834-107">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c1834-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c1834-108">Funkcja z `'T` do wartości logicznej, która jest używana do filtrowania elementów.</span><span class="sxs-lookup"><span data-stu-id="c1834-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="c1834-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="c1834-109">array : 'T[]</span></span>

<span data-ttu-id="c1834-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="c1834-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="c1834-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1834-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1834-112">Liczba elementów w `array` , które spełniają predykat.</span><span class="sxs-lookup"><span data-stu-id="c1834-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c1834-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c1834-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c1834-114">'C</span><span class="sxs-lookup"><span data-stu-id="c1834-114">'T</span></span>

<span data-ttu-id="c1834-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="c1834-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="c1834-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="c1834-116">Example</span></span>

<span data-ttu-id="c1834-117">Poniższy kod demonstruje funkcję "Count".</span><span class="sxs-lookup"><span data-stu-id="c1834-117">The following code demonstrates the "Count" function.</span></span>
<span data-ttu-id="c1834-118">Predykat jest definiowany przy użyciu @"microsoft.quantum.logical.greaterthani" funkcji:</span><span class="sxs-lookup"><span data-stu-id="c1834-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a><span data-ttu-id="c1834-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c1834-119">Remarks</span></span>

<span data-ttu-id="c1834-120">Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i predykat `'T -> Bool` możemy filtrować elementy.</span><span class="sxs-lookup"><span data-stu-id="c1834-120">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>
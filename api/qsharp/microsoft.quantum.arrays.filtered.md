---
uid: Microsoft.Quantum.Arrays.Filtered
title: Funkcja filtrowana
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847160"
---
# <a name="filtered-function"></a><span data-ttu-id="60aad-102">Funkcja filtrowana</span><span class="sxs-lookup"><span data-stu-id="60aad-102">Filtered function</span></span>

<span data-ttu-id="60aad-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="60aad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="60aad-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60aad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60aad-105">Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, zwraca tablicę, która składa się z tych elementów, które spełniają predykat.</span><span class="sxs-lookup"><span data-stu-id="60aad-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="60aad-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="60aad-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="60aad-107">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="60aad-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="60aad-108">Funkcja z `'T` do wartości logicznej, która jest używana do filtrowania elementów.</span><span class="sxs-lookup"><span data-stu-id="60aad-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="60aad-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="60aad-109">array : 'T[]</span></span>

<span data-ttu-id="60aad-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="60aad-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="60aad-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="60aad-111">Output : 'T[]</span></span>

<span data-ttu-id="60aad-112">Tablica `'T[]` elementów, które spełniają predykat.</span><span class="sxs-lookup"><span data-stu-id="60aad-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="60aad-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="60aad-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60aad-114">'C</span><span class="sxs-lookup"><span data-stu-id="60aad-114">'T</span></span>

<span data-ttu-id="60aad-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="60aad-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="60aad-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="60aad-116">Example</span></span>

<span data-ttu-id="60aad-117">Poniższy kod demonstruje funkcję "Filtered".</span><span class="sxs-lookup"><span data-stu-id="60aad-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="60aad-118">Predykat jest definiowany przy użyciu @"microsoft.quantum.logical.greaterthani" funkcji:</span><span class="sxs-lookup"><span data-stu-id="60aad-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="60aad-119">Wynik powinien oczekiwać od tego przykładu, będzie tablicą liczb większą niż 5.</span><span class="sxs-lookup"><span data-stu-id="60aad-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="60aad-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="60aad-120">Remarks</span></span>

<span data-ttu-id="60aad-121">Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i predykat `'T -> Bool` możemy filtrować elementy.</span><span class="sxs-lookup"><span data-stu-id="60aad-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>
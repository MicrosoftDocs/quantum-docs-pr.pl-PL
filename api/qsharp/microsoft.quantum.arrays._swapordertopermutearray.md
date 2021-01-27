---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funkcja _SwapOrderToPermuteArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846288"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="5512b-102">Funkcja _SwapOrderToPermuteArray</span><span class="sxs-lookup"><span data-stu-id="5512b-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="5512b-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5512b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5512b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5512b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5512b-105">Zwraca elementy zamówienia w tablicy, które muszą zostać zamienione w celu utworzenia uporządkowanej tablicy.</span><span class="sxs-lookup"><span data-stu-id="5512b-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="5512b-106">Przyjęto zamianę na miejsce.</span><span class="sxs-lookup"><span data-stu-id="5512b-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="5512b-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5512b-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="5512b-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5512b-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5512b-109">Tablica z Permutacją indeksów nowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="5512b-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="5512b-110">Powinny być $n elementy $, każda z nich jest unikatową liczbą całkowitą z zakresu od $0 do $n – $1.</span><span class="sxs-lookup"><span data-stu-id="5512b-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="5512b-111">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="5512b-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="5512b-112">Krotka reprezentuje dwa indeksy, które mają zostać zamienione.</span><span class="sxs-lookup"><span data-stu-id="5512b-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="5512b-113">Zamiany zaczynają się na najniższym indeksie.</span><span class="sxs-lookup"><span data-stu-id="5512b-113">The swaps begin at the lowest index.</span></span>

## <a name="example"></a><span data-ttu-id="5512b-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="5512b-114">Example</span></span>

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a><span data-ttu-id="5512b-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5512b-115">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="5512b-116">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="5512b-116">Psuedocode</span></span>

<span data-ttu-id="5512b-117">for (indeks in 0.. length (newOrder)-1) {while newOrder [index]! = index {Switch newOrder [index] with newOrder [newOrder [indeks]]}}</span><span class="sxs-lookup"><span data-stu-id="5512b-117">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>
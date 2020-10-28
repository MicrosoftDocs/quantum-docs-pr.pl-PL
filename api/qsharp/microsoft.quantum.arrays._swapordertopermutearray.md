---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funkcja _SwapOrderToPermuteArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719493"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="80b36-102">Funkcja _SwapOrderToPermuteArray</span><span class="sxs-lookup"><span data-stu-id="80b36-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="80b36-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="80b36-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="80b36-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80b36-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80b36-105">Zwraca elementy zamówienia w tablicy, które muszą zostać zamienione w celu utworzenia uporządkowanej tablicy.</span><span class="sxs-lookup"><span data-stu-id="80b36-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="80b36-106">Przyjęto zamianę na miejsce.</span><span class="sxs-lookup"><span data-stu-id="80b36-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="80b36-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="80b36-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="80b36-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="80b36-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="80b36-109">Tablica z Permutacją indeksów nowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="80b36-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="80b36-110">Powinny być $n elementy $, każda z nich jest unikatową liczbą całkowitą z zakresu od $0 do $n – $1.</span><span class="sxs-lookup"><span data-stu-id="80b36-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="80b36-111">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="80b36-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="80b36-112">Krotka reprezentuje dwa indeksy, które mają zostać zamienione.</span><span class="sxs-lookup"><span data-stu-id="80b36-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="80b36-113">Zamiany zaczynają się na najniższym indeksie.</span><span class="sxs-lookup"><span data-stu-id="80b36-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="80b36-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="80b36-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="80b36-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="80b36-115">Psuedocode</span></span>

<span data-ttu-id="80b36-116">for (indeks in 0.. length (newOrder)-1) {while newOrder [index]! = index {Switch newOrder [index] with newOrder [newOrder [indeks]]}}</span><span class="sxs-lookup"><span data-stu-id="80b36-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>
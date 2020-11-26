---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: Funkcja _SwapOrderToPermuteArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221712"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="e3d9e-102">Funkcja _SwapOrderToPermuteArray</span><span class="sxs-lookup"><span data-stu-id="e3d9e-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="e3d9e-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e3d9e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e3d9e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3d9e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3d9e-105">Zwraca elementy zamówienia w tablicy, które muszą zostać zamienione w celu utworzenia uporządkowanej tablicy.</span><span class="sxs-lookup"><span data-stu-id="e3d9e-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="e3d9e-106">Przyjęto zamianę na miejsce.</span><span class="sxs-lookup"><span data-stu-id="e3d9e-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="e3d9e-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e3d9e-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="e3d9e-108">newOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e3d9e-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e3d9e-109">Tablica z Permutacją indeksów nowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="e3d9e-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="e3d9e-110">Powinny być $n elementy $, każda z nich jest unikatową liczbą całkowitą z zakresu od $0 do $n – $1.</span><span class="sxs-lookup"><span data-stu-id="e3d9e-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="e3d9e-111">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="e3d9e-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="e3d9e-112">Krotka reprezentuje dwa indeksy, które mają zostać zamienione.</span><span class="sxs-lookup"><span data-stu-id="e3d9e-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="e3d9e-113">Zamiany zaczynają się na najniższym indeksie.</span><span class="sxs-lookup"><span data-stu-id="e3d9e-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3d9e-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e3d9e-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="e3d9e-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="e3d9e-115">Psuedocode</span></span>

<span data-ttu-id="e3d9e-116">for (indeks in 0.. length (newOrder)-1) {while newOrder [index]! = index {Switch newOrder [index] with newOrder [newOrder [indeks]]}}</span><span class="sxs-lookup"><span data-stu-id="e3d9e-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>
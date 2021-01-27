---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840277"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="18da3-102">IterateThroughCartesianProduct, operacja</span><span class="sxs-lookup"><span data-stu-id="18da3-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="18da3-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="18da3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="18da3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18da3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18da3-105">Stosuje operację dla każdego indeksu w kartezjańskiego produktu kilku zakresów.</span><span class="sxs-lookup"><span data-stu-id="18da3-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="18da3-106">Opis</span><span class="sxs-lookup"><span data-stu-id="18da3-106">Description</span></span>

<span data-ttu-id="18da3-107">Iteracyjnie stosuje operację dla każdego elementu kartezjańskiego produktu `0..(bounds[0] - 1)` ,,... `0..(bounds[1] - 1)` , `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="18da3-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="18da3-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="18da3-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="18da3-109">granice: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="18da3-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="18da3-110">Tablica określająca zakresy, które mają być powtarzane, z każdym zakresem określanym jako długość całkowita.</span><span class="sxs-lookup"><span data-stu-id="18da3-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="18da3-111">op: [int](xref:microsoft.quantum.lang-ref.int)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="18da3-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="18da3-112">Operacja, która ma zostać wywołana dla każdego elementu danego produktu kartezjańskiego.</span><span class="sxs-lookup"><span data-stu-id="18da3-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="18da3-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="18da3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="18da3-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="18da3-114">Example</span></span>

<span data-ttu-id="18da3-115">Po danej operacji `op` następujące dwa fragmenty kodu są równoważne:</span><span class="sxs-lookup"><span data-stu-id="18da3-115">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a><span data-ttu-id="18da3-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="18da3-116">See Also</span></span>

- [<span data-ttu-id="18da3-117">Microsoft. Quantum. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="18da3-117">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)
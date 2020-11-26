---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: 6340c7a972253e6f583a3856df93a7066ced3139
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206446"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="f0727-102">IterateThroughCartesianProduct, operacja</span><span class="sxs-lookup"><span data-stu-id="f0727-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="f0727-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f0727-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f0727-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0727-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0727-105">Stosuje operację dla każdego indeksu w kartezjańskiego produktu kilku zakresów.</span><span class="sxs-lookup"><span data-stu-id="f0727-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="f0727-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f0727-106">Description</span></span>

<span data-ttu-id="f0727-107">Iteracyjnie stosuje operację dla każdego elementu kartezjańskiego produktu `0..(bounds[0] - 1)` ,,... `0..(bounds[1] - 1)` , `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="f0727-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="f0727-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f0727-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="f0727-109">granice: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f0727-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f0727-110">Tablica określająca zakresy, które mają być powtarzane, z każdym zakresem określanym jako długość całkowita.</span><span class="sxs-lookup"><span data-stu-id="f0727-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="f0727-111">op: [int](xref:microsoft.quantum.lang-ref.int)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f0727-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f0727-112">Operacja, która ma zostać wywołana dla każdego elementu danego produktu kartezjańskiego.</span><span class="sxs-lookup"><span data-stu-id="f0727-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f0727-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0727-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f0727-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f0727-114">See Also</span></span>

- [<span data-ttu-id="f0727-115">Microsoft. Quantum. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="f0727-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)
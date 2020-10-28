---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716039"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="5cfec-102">IterateThroughCartesianProduct, operacja</span><span class="sxs-lookup"><span data-stu-id="5cfec-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="5cfec-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5cfec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5cfec-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5cfec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5cfec-105">Stosuje operację dla każdego indeksu w kartezjańskiego produktu kilku zakresów.</span><span class="sxs-lookup"><span data-stu-id="5cfec-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="5cfec-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5cfec-106">Description</span></span>

<span data-ttu-id="5cfec-107">Iteracyjnie stosuje operację dla każdego elementu kartezjańskiego produktu `0..(bounds[0] - 1)` ,,... `0..(bounds[1] - 1)` , `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="5cfec-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="5cfec-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5cfec-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="5cfec-109">granice: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5cfec-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5cfec-110">Tablica określająca zakresy, które mają być powtarzane, z każdym zakresem określanym jako długość całkowita.</span><span class="sxs-lookup"><span data-stu-id="5cfec-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="5cfec-111">op: [int](xref:microsoft.quantum.lang-ref.int)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="5cfec-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5cfec-112">Operacja, która ma zostać wywołana dla każdego elementu danego produktu kartezjańskiego.</span><span class="sxs-lookup"><span data-stu-id="5cfec-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5cfec-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5cfec-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5cfec-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5cfec-114">See Also</span></span>

- [<span data-ttu-id="5cfec-115">Microsoft. Quantum. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="5cfec-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)
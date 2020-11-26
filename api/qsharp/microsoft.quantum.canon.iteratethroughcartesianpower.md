---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206480"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="404b9-102">IterateThroughCartesianPower, operacja</span><span class="sxs-lookup"><span data-stu-id="404b9-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="404b9-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="404b9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="404b9-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="404b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="404b9-105">Stosuje operację dla każdego indeksu w Kartezjańskiegoej liczbie całkowitej.</span><span class="sxs-lookup"><span data-stu-id="404b9-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="404b9-106">Opis</span><span class="sxs-lookup"><span data-stu-id="404b9-106">Description</span></span>

<span data-ttu-id="404b9-107">Iteracyjnie stosuje operację dla każdego elementu Kartezjańskiegoego zakresu `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="404b9-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="404b9-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="404b9-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="404b9-109">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="404b9-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="404b9-110">Kartezjańskiego, do którego `0..(bound - 1)` ma zostać zgłoszony zakres.</span><span class="sxs-lookup"><span data-stu-id="404b9-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="404b9-111">powiązane: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="404b9-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="404b9-112">Specyfikacja zakresu, który ma być powtarzany, wyrażony jako długość zakresu.</span><span class="sxs-lookup"><span data-stu-id="404b9-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="404b9-113">op: [int](xref:microsoft.quantum.lang-ref.int)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="404b9-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="404b9-114">Operacja, która ma zostać wywołana dla każdego elementu w danej kartezjańskiego.</span><span class="sxs-lookup"><span data-stu-id="404b9-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="404b9-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="404b9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="404b9-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="404b9-116">See Also</span></span>

- [<span data-ttu-id="404b9-117">Microsoft. Quantum. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="404b9-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)
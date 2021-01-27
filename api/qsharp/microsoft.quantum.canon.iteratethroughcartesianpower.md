---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840293"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="888be-102">IterateThroughCartesianPower, operacja</span><span class="sxs-lookup"><span data-stu-id="888be-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="888be-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="888be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="888be-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="888be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="888be-105">Stosuje operację dla każdego indeksu w Kartezjańskiegoej liczbie całkowitej.</span><span class="sxs-lookup"><span data-stu-id="888be-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="888be-106">Opis</span><span class="sxs-lookup"><span data-stu-id="888be-106">Description</span></span>

<span data-ttu-id="888be-107">Iteracyjnie stosuje operację dla każdego elementu Kartezjańskiegoego zakresu `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="888be-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="888be-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="888be-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="888be-109">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="888be-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="888be-110">Kartezjańskiego, do którego `0..(bound - 1)` ma zostać zgłoszony zakres.</span><span class="sxs-lookup"><span data-stu-id="888be-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="888be-111">powiązane: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="888be-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="888be-112">Specyfikacja zakresu, który ma być powtarzany, wyrażony jako długość zakresu.</span><span class="sxs-lookup"><span data-stu-id="888be-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="888be-113">op: [int](xref:microsoft.quantum.lang-ref.int)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="888be-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="888be-114">Operacja, która ma zostać wywołana dla każdego elementu w danej kartezjańskiego.</span><span class="sxs-lookup"><span data-stu-id="888be-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="888be-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="888be-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="888be-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="888be-116">Example</span></span>

<span data-ttu-id="888be-117">Po danej operacji `op` następujące dwa fragmenty kodu są równoważne:</span><span class="sxs-lookup"><span data-stu-id="888be-117">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a><span data-ttu-id="888be-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="888be-118">See Also</span></span>

- [<span data-ttu-id="888be-119">Microsoft. Quantum. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="888be-119">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)
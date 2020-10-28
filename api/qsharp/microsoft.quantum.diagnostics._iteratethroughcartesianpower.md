---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: Operacja _iterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: 36666238b40d036e3f6a8949b22f5806216d71f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713141"
---
# <a name="_iteratethroughcartesianpower-operation"></a><span data-ttu-id="9c9d7-102">Operacja _iterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="9c9d7-102">_iterateThroughCartesianPower operation</span></span>

<span data-ttu-id="9c9d7-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9c9d7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9c9d7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c9d7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c9d7-105">Iteruje zmienną za pomocą kartezjańskiego produktu [0, granice [0]-1] × [0, granice [1]-1] × [0, ograniczenia [Długość (granice)-1]-1] i wywołania operacji (ARR) dla każdego elementu produktu kartezjańskiego</span><span class="sxs-lookup"><span data-stu-id="9c9d7-105">Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product</span></span>

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="9c9d7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9c9d7-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="9c9d7-107">Długość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c9d7-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="value--int"></a><span data-ttu-id="9c9d7-108">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c9d7-108">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--int--unit"></a><span data-ttu-id="9c9d7-109">op: [int](xref:microsoft.quantum.lang-ref.int)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="9c9d7-109">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="9c9d7-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c9d7-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


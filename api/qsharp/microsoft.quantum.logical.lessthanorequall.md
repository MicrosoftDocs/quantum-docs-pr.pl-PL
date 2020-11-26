---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 2322ae4dd6025108d322d29770f42953213aa025
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197605"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="bd1af-102">LessThanOrEqualL, funkcja</span><span class="sxs-lookup"><span data-stu-id="bd1af-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="bd1af-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="bd1af-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="bd1af-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd1af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd1af-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="bd1af-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="bd1af-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bd1af-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="bd1af-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bd1af-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bd1af-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="bd1af-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="bd1af-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bd1af-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bd1af-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="bd1af-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bd1af-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bd1af-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bd1af-112">`true` if i tylko wtedy, gdy `a` jest mniejsza lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="bd1af-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd1af-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bd1af-113">Remarks</span></span>

<span data-ttu-id="bd1af-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="bd1af-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```
---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 333b76fc4885104e107dd25003a4e0dd5a9dd4af
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709921"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="bb9ad-102">LessThanOrEqualL, funkcja</span><span class="sxs-lookup"><span data-stu-id="bb9ad-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="bb9ad-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="bb9ad-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="bb9ad-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb9ad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb9ad-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="bb9ad-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bb9ad-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="bb9ad-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bb9ad-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bb9ad-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="bb9ad-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bb9ad-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bb9ad-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bb9ad-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bb9ad-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bb9ad-112">`true` if i tylko wtedy, gdy `a` jest mniejsza lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="bb9ad-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb9ad-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bb9ad-113">Remarks</span></span>

<span data-ttu-id="bb9ad-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="bb9ad-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```
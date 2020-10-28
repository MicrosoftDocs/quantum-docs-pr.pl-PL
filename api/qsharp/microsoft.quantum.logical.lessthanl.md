---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: fde57bcd9960056461bddac54300c298def8f7d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709954"
---
# <a name="lessthanl-function"></a><span data-ttu-id="bb228-102">LessThanL, funkcja</span><span class="sxs-lookup"><span data-stu-id="bb228-102">LessThanL function</span></span>

<span data-ttu-id="bb228-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="bb228-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="bb228-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb228-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb228-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza od innej liczby.</span><span class="sxs-lookup"><span data-stu-id="bb228-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="bb228-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bb228-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="bb228-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bb228-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bb228-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="bb228-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="bb228-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bb228-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bb228-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="bb228-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bb228-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bb228-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bb228-112">`true` if i tylko wtedy, gdy `a` jest ściśle mniejsza niż `b` .</span><span class="sxs-lookup"><span data-stu-id="bb228-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb228-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bb228-113">Remarks</span></span>

<span data-ttu-id="bb228-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="bb228-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```
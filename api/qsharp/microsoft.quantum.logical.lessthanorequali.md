---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: b2974c9bc84d0b4366767f47682ab542f85063e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197570"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="f3b2f-102">LessThanOrEqualI, funkcja</span><span class="sxs-lookup"><span data-stu-id="f3b2f-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="f3b2f-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f3b2f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f3b2f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3b2f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3b2f-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="f3b2f-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="f3b2f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f3b2f-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f3b2f-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f3b2f-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f3b2f-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="f3b2f-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="f3b2f-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f3b2f-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f3b2f-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="f3b2f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f3b2f-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f3b2f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f3b2f-112">`true` if i tylko wtedy, gdy `a` jest mniejsza lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="f3b2f-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f3b2f-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f3b2f-113">Remarks</span></span>

<span data-ttu-id="f3b2f-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="f3b2f-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```
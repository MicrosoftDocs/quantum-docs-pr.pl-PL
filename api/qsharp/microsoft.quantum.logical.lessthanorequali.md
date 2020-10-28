---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709935"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="69509-102">LessThanOrEqualI, funkcja</span><span class="sxs-lookup"><span data-stu-id="69509-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="69509-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="69509-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="69509-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69509-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69509-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="69509-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="69509-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="69509-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="69509-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69509-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69509-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="69509-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="69509-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69509-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69509-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="69509-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="69509-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="69509-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="69509-112">`true` if i tylko wtedy, gdy `a` jest mniejsza lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="69509-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="69509-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="69509-113">Remarks</span></span>

<span data-ttu-id="69509-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="69509-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```
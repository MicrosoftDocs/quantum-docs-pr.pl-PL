---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 204e62a87d2b3d0070946985030d038ead686457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723482"
---
# <a name="lessthani-function"></a><span data-ttu-id="8970a-102">LessThanI, funkcja</span><span class="sxs-lookup"><span data-stu-id="8970a-102">LessThanI function</span></span>

<span data-ttu-id="8970a-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8970a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8970a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8970a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8970a-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza od innej liczby.</span><span class="sxs-lookup"><span data-stu-id="8970a-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="8970a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8970a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="8970a-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8970a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8970a-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="8970a-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="8970a-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8970a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8970a-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="8970a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8970a-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8970a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8970a-112">`true` if i tylko wtedy, gdy `a` jest ściśle mniejsza niż `b` .</span><span class="sxs-lookup"><span data-stu-id="8970a-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8970a-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8970a-113">Remarks</span></span>

<span data-ttu-id="8970a-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="8970a-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```
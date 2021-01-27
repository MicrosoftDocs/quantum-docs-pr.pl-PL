---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: c1a513500c8a70bd7628976974387cba48162e80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849183"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="7dd78-102">GreaterThanOrEqualI, funkcja</span><span class="sxs-lookup"><span data-stu-id="7dd78-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="7dd78-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7dd78-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7dd78-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7dd78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7dd78-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="7dd78-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="7dd78-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7dd78-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="7dd78-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7dd78-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7dd78-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="7dd78-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="7dd78-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7dd78-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7dd78-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="7dd78-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7dd78-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7dd78-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7dd78-112">`true` if i tylko wtedy, gdy `a` jest większa lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="7dd78-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7dd78-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7dd78-113">Remarks</span></span>

<span data-ttu-id="7dd78-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="7dd78-114">The following are equivalent:</span></span>

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```
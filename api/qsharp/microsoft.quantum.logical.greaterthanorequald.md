---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 9d794fa94c1ccbde4030c90198fd7c7654469876
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711377"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="2b2fb-102">GreaterThanOrEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="2b2fb-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="2b2fb-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2b2fb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2b2fb-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b2fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b2fb-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="2b2fb-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="2b2fb-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2b2fb-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="2b2fb-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2b2fb-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2b2fb-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="2b2fb-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="2b2fb-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2b2fb-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2b2fb-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="2b2fb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2b2fb-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2b2fb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2b2fb-112">`true` if i tylko wtedy, gdy `a` jest większa lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="2b2fb-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b2fb-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2b2fb-113">Remarks</span></span>

<span data-ttu-id="2b2fb-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="2b2fb-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```
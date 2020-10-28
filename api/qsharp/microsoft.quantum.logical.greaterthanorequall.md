---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722642"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="c42f7-102">GreaterThanOrEqualL, funkcja</span><span class="sxs-lookup"><span data-stu-id="c42f7-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="c42f7-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c42f7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c42f7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c42f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c42f7-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="c42f7-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="c42f7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c42f7-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c42f7-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c42f7-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c42f7-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c42f7-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="c42f7-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c42f7-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c42f7-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c42f7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c42f7-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c42f7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c42f7-112">`true` if i tylko wtedy, gdy `a` jest większa lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="c42f7-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c42f7-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c42f7-113">Remarks</span></span>

<span data-ttu-id="c42f7-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="c42f7-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```
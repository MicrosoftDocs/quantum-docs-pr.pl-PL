---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711382"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="e0c04-102">GreaterThanL, funkcja</span><span class="sxs-lookup"><span data-stu-id="e0c04-102">GreaterThanL function</span></span>

<span data-ttu-id="e0c04-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e0c04-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e0c04-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0c04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0c04-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa niż inna liczba.</span><span class="sxs-lookup"><span data-stu-id="e0c04-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="e0c04-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e0c04-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e0c04-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e0c04-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e0c04-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="e0c04-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="e0c04-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e0c04-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e0c04-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="e0c04-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e0c04-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e0c04-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e0c04-112">`true` if i tylko wtedy, gdy `a` jest ściśle większa niż `b` .</span><span class="sxs-lookup"><span data-stu-id="e0c04-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0c04-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e0c04-113">Remarks</span></span>

<span data-ttu-id="e0c04-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="e0c04-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```
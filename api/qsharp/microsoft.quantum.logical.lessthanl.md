---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 9a0678569596ac188c87c3944f3759783fcc77ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197725"
---
# <a name="lessthanl-function"></a><span data-ttu-id="42d48-102">LessThanL, funkcja</span><span class="sxs-lookup"><span data-stu-id="42d48-102">LessThanL function</span></span>

<span data-ttu-id="42d48-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="42d48-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="42d48-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42d48-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42d48-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza od innej liczby.</span><span class="sxs-lookup"><span data-stu-id="42d48-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="42d48-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="42d48-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="42d48-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="42d48-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="42d48-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="42d48-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="42d48-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="42d48-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="42d48-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="42d48-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="42d48-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="42d48-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="42d48-112">`true` if i tylko wtedy, gdy `a` jest ściśle mniejsza niż `b` .</span><span class="sxs-lookup"><span data-stu-id="42d48-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="42d48-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="42d48-113">Remarks</span></span>

<span data-ttu-id="42d48-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="42d48-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```
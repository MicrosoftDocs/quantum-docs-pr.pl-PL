---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 5e1b2adab36b7937c83ea912b8a9cb148b626ee5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197980"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="135ae-102">GreaterThanL, funkcja</span><span class="sxs-lookup"><span data-stu-id="135ae-102">GreaterThanL function</span></span>

<span data-ttu-id="135ae-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="135ae-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="135ae-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="135ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="135ae-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa niż inna liczba.</span><span class="sxs-lookup"><span data-stu-id="135ae-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="135ae-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="135ae-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="135ae-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="135ae-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="135ae-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="135ae-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="135ae-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="135ae-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="135ae-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="135ae-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="135ae-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="135ae-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="135ae-112">`true` if i tylko wtedy, gdy `a` jest ściśle większa niż `b` .</span><span class="sxs-lookup"><span data-stu-id="135ae-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="135ae-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="135ae-113">Remarks</span></span>

<span data-ttu-id="135ae-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="135ae-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```
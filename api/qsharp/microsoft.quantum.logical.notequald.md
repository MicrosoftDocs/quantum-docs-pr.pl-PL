---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4599d7125dbc67547af454183f620e8d84f2caf7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197249"
---
# <a name="notequald-function"></a><span data-ttu-id="5cbbd-102">NotEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="5cbbd-102">NotEqualD function</span></span>

<span data-ttu-id="5cbbd-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5cbbd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5cbbd-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5cbbd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5cbbd-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="5cbbd-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="5cbbd-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5cbbd-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="5cbbd-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5cbbd-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5cbbd-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="5cbbd-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="5cbbd-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5cbbd-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5cbbd-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="5cbbd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5cbbd-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5cbbd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5cbbd-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="5cbbd-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cbbd-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5cbbd-113">Remarks</span></span>

<span data-ttu-id="5cbbd-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="5cbbd-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```
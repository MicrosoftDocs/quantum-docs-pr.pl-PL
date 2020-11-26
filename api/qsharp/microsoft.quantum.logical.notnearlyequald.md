---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 23229b1630982eba4485330cc2290aed733c4d86
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197147"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="23b85-102">NotNearlyEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="23b85-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="23b85-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="23b85-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="23b85-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23b85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23b85-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są niemal równe (czyli nie są objęte tolerancją 1e-12).</span><span class="sxs-lookup"><span data-stu-id="23b85-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="23b85-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="23b85-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="23b85-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="23b85-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="23b85-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="23b85-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="23b85-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="23b85-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="23b85-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="23b85-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="23b85-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="23b85-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="23b85-112">`true` if i tylko wtedy, gdy `a` nie jest niemal równe `b` .</span><span class="sxs-lookup"><span data-stu-id="23b85-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="23b85-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="23b85-113">Remarks</span></span>

<span data-ttu-id="23b85-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="23b85-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```
---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720729"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="c7107-102">NotNearlyEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="c7107-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="c7107-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c7107-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c7107-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7107-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7107-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są niemal równe (czyli nie są objęte tolerancją 1e-12).</span><span class="sxs-lookup"><span data-stu-id="c7107-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c7107-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c7107-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c7107-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c7107-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c7107-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c7107-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c7107-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c7107-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c7107-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c7107-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c7107-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c7107-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c7107-112">`true` if i tylko wtedy, gdy `a` nie jest niemal równe `b` .</span><span class="sxs-lookup"><span data-stu-id="c7107-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7107-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c7107-113">Remarks</span></span>

<span data-ttu-id="c7107-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="c7107-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```
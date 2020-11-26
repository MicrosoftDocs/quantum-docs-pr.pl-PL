---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 246fad15c691a53fcc5be10f2c713672e0b54e6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197470"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="e499d-102">NearlyEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="e499d-102">NearlyEqualD function</span></span>

<span data-ttu-id="e499d-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e499d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e499d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e499d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e499d-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są niemal równe (to jest, w ramach tolerancji o wartości 1e-12).</span><span class="sxs-lookup"><span data-stu-id="e499d-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="e499d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e499d-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="e499d-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e499d-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e499d-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="e499d-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="e499d-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e499d-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e499d-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="e499d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e499d-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e499d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e499d-112">`true` if i tylko wtedy, gdy `a` jest niemal równe `b` .</span><span class="sxs-lookup"><span data-stu-id="e499d-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e499d-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e499d-113">Remarks</span></span>

<span data-ttu-id="e499d-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="e499d-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```
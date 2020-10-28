---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709949"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="13a1e-102">LessThanOrEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="13a1e-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="13a1e-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="13a1e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="13a1e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13a1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13a1e-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="13a1e-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="13a1e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="13a1e-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="13a1e-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="13a1e-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="13a1e-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="13a1e-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="13a1e-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="13a1e-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="13a1e-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="13a1e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="13a1e-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="13a1e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="13a1e-112">`true` if i tylko wtedy, gdy `a` jest mniejsza lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="13a1e-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="13a1e-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="13a1e-113">Remarks</span></span>

<span data-ttu-id="13a1e-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="13a1e-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```
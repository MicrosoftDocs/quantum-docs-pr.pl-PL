---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 98fa55c249f2ade414254d1bccda46a8602b828c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815865"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="6422a-102">GreaterThanOrEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="6422a-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="6422a-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6422a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6422a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6422a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6422a-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="6422a-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6422a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6422a-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="6422a-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6422a-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6422a-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="6422a-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="6422a-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6422a-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6422a-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="6422a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6422a-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6422a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6422a-112">`true` if i tylko wtedy, gdy `a` jest większa lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="6422a-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6422a-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6422a-113">Remarks</span></span>

<span data-ttu-id="6422a-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="6422a-114">The following are equivalent:</span></span>

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```
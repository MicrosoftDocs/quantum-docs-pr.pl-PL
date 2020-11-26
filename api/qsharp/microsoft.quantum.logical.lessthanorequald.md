---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 3f4ccb0888e7df7c43ff73be8a3140e3fa84d4dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197640"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="421e9-102">LessThanOrEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="421e9-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="421e9-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="421e9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="421e9-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="421e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="421e9-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="421e9-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="421e9-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="421e9-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="421e9-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="421e9-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="421e9-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="421e9-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="421e9-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="421e9-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="421e9-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="421e9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="421e9-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="421e9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="421e9-112">`true` if i tylko wtedy, gdy `a` jest mniejsza lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="421e9-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="421e9-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="421e9-113">Remarks</span></span>

<span data-ttu-id="421e9-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="421e9-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```
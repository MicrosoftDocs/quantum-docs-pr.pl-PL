---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 40f059e49affbb1b5af7dc349f6ee53dfb357873
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197742"
---
# <a name="lessthand-function"></a><span data-ttu-id="dee49-102">LessThanD, funkcja</span><span class="sxs-lookup"><span data-stu-id="dee49-102">LessThanD function</span></span>

<span data-ttu-id="dee49-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="dee49-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="dee49-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dee49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dee49-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza od innej liczby.</span><span class="sxs-lookup"><span data-stu-id="dee49-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="dee49-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dee49-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="dee49-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dee49-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dee49-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="dee49-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="dee49-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dee49-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dee49-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="dee49-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="dee49-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dee49-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dee49-112">`true` if i tylko wtedy, gdy `a` jest ściśle mniejsza niż `b` .</span><span class="sxs-lookup"><span data-stu-id="dee49-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dee49-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dee49-113">Remarks</span></span>

<span data-ttu-id="dee49-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="dee49-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```
---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 5d5b17c8481ccf58b8e4fc4bb958e0adbf6d8f00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197776"
---
# <a name="lessthani-function"></a><span data-ttu-id="c9c24-102">LessThanI, funkcja</span><span class="sxs-lookup"><span data-stu-id="c9c24-102">LessThanI function</span></span>

<span data-ttu-id="c9c24-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c9c24-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c9c24-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9c24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9c24-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza od innej liczby.</span><span class="sxs-lookup"><span data-stu-id="c9c24-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="c9c24-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c9c24-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c9c24-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9c24-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9c24-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c9c24-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="c9c24-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9c24-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9c24-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c9c24-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c9c24-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c9c24-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c9c24-112">`true` if i tylko wtedy, gdy `a` jest ściśle mniejsza niż `b` .</span><span class="sxs-lookup"><span data-stu-id="c9c24-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9c24-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c9c24-113">Remarks</span></span>

<span data-ttu-id="c9c24-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="c9c24-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```
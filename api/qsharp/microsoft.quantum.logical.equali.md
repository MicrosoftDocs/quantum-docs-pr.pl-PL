---
uid: Microsoft.Quantum.Logical.EqualI
title: EqualI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: be92ef2b63981094e1a95c38e02de95c3c2bbf3a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198167"
---
# <a name="equali-function"></a><span data-ttu-id="caac4-102">EqualI, funkcja</span><span class="sxs-lookup"><span data-stu-id="caac4-102">EqualI function</span></span>

<span data-ttu-id="caac4-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="caac4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="caac4-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="caac4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="caac4-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="caac4-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="caac4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="caac4-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="caac4-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="caac4-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="caac4-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="caac4-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="caac4-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="caac4-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="caac4-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="caac4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="caac4-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="caac4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="caac4-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="caac4-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="caac4-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="caac4-113">Remarks</span></span>

<span data-ttu-id="caac4-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="caac4-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```
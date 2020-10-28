---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723496"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="f9e3c-102">GreaterThanOrEqualI, funkcja</span><span class="sxs-lookup"><span data-stu-id="f9e3c-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="f9e3c-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f9e3c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f9e3c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9e3c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9e3c-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="f9e3c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f9e3c-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f9e3c-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9e3c-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9e3c-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="f9e3c-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9e3c-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9e3c-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f9e3c-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f9e3c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f9e3c-112">`true` if i tylko wtedy, gdy `a` jest większa lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="f9e3c-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9e3c-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f9e3c-113">Remarks</span></span>

<span data-ttu-id="f9e3c-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="f9e3c-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```
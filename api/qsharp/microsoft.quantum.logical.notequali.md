---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709828"
---
# <a name="notequali-function"></a><span data-ttu-id="9fadd-102">NotEqualI, funkcja</span><span class="sxs-lookup"><span data-stu-id="9fadd-102">NotEqualI function</span></span>

<span data-ttu-id="9fadd-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9fadd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9fadd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9fadd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9fadd-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="9fadd-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="9fadd-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9fadd-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="9fadd-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9fadd-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9fadd-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="9fadd-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="9fadd-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9fadd-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9fadd-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="9fadd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9fadd-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9fadd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9fadd-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="9fadd-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9fadd-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9fadd-113">Remarks</span></span>

<span data-ttu-id="9fadd-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="9fadd-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```
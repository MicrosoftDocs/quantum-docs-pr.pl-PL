---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f1d36c284293519e75e6c30ac64679c7bdf4609c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709809"
---
# <a name="notequall-function"></a><span data-ttu-id="52ea2-102">NotEqualL, funkcja</span><span class="sxs-lookup"><span data-stu-id="52ea2-102">NotEqualL function</span></span>

<span data-ttu-id="52ea2-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="52ea2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="52ea2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="52ea2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="52ea2-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="52ea2-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="52ea2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="52ea2-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="52ea2-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="52ea2-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="52ea2-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="52ea2-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="52ea2-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="52ea2-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="52ea2-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="52ea2-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="52ea2-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="52ea2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="52ea2-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="52ea2-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="52ea2-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="52ea2-113">Remarks</span></span>

<span data-ttu-id="52ea2-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="52ea2-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```
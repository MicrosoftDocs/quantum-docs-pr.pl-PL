---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: e138a8def30bc77499662ffa6bc214d0c6a38893
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197232"
---
# <a name="notequall-function"></a><span data-ttu-id="a3589-102">NotEqualL, funkcja</span><span class="sxs-lookup"><span data-stu-id="a3589-102">NotEqualL function</span></span>

<span data-ttu-id="a3589-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a3589-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a3589-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3589-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3589-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="a3589-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="a3589-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a3589-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a3589-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a3589-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a3589-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="a3589-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="a3589-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a3589-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a3589-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="a3589-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a3589-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a3589-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a3589-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="a3589-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3589-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a3589-113">Remarks</span></span>

<span data-ttu-id="a3589-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="a3589-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```
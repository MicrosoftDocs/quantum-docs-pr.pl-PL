---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848497"
---
# <a name="notequalr-function"></a><span data-ttu-id="4c8bc-102">NotEqualR, funkcja</span><span class="sxs-lookup"><span data-stu-id="4c8bc-102">NotEqualR function</span></span>

<span data-ttu-id="4c8bc-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4c8bc-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4c8bc-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4c8bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4c8bc-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="4c8bc-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="4c8bc-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4c8bc-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="4c8bc-107">Odp. __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="4c8bc-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="4c8bc-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="4c8bc-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="4c8bc-109">b: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="4c8bc-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="4c8bc-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="4c8bc-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4c8bc-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4c8bc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4c8bc-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="4c8bc-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c8bc-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4c8bc-113">Remarks</span></span>

<span data-ttu-id="4c8bc-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="4c8bc-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```
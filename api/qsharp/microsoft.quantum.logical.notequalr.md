---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709795"
---
# <a name="notequalr-function"></a><span data-ttu-id="383ad-102">NotEqualR, funkcja</span><span class="sxs-lookup"><span data-stu-id="383ad-102">NotEqualR function</span></span>

<span data-ttu-id="383ad-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="383ad-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="383ad-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="383ad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="383ad-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="383ad-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="383ad-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="383ad-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="383ad-107">Odp. __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="383ad-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="383ad-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="383ad-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="383ad-109">b: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="383ad-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="383ad-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="383ad-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="383ad-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="383ad-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="383ad-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="383ad-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="383ad-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="383ad-113">Remarks</span></span>

<span data-ttu-id="383ad-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="383ad-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```
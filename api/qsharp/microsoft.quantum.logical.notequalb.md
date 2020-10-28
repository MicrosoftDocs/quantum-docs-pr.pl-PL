---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709837"
---
# <a name="notequalb-function"></a><span data-ttu-id="c2dc9-102">NotEqualB, funkcja</span><span class="sxs-lookup"><span data-stu-id="c2dc9-102">NotEqualB function</span></span>

<span data-ttu-id="c2dc9-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c2dc9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c2dc9-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2dc9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2dc9-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="c2dc9-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="c2dc9-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c2dc9-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="c2dc9-107">Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c2dc9-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c2dc9-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c2dc9-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="c2dc9-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c2dc9-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c2dc9-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c2dc9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c2dc9-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c2dc9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c2dc9-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="c2dc9-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2dc9-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c2dc9-113">Remarks</span></span>

<span data-ttu-id="c2dc9-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="c2dc9-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```
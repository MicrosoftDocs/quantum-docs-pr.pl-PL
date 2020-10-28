---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 91ab51180018a9b95a2f9010477c0a24f3a54617
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720780"
---
# <a name="equalb-function"></a><span data-ttu-id="937a8-102">EqualB, funkcja</span><span class="sxs-lookup"><span data-stu-id="937a8-102">EqualB function</span></span>

<span data-ttu-id="937a8-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="937a8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="937a8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="937a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="937a8-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="937a8-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="937a8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="937a8-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="937a8-107">Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="937a8-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="937a8-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="937a8-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="937a8-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="937a8-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="937a8-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="937a8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="937a8-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="937a8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="937a8-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="937a8-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="937a8-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="937a8-113">Remarks</span></span>

<span data-ttu-id="937a8-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="937a8-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```
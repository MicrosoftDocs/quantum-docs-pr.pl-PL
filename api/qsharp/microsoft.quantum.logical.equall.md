---
uid: Microsoft.Quantum.Logical.EqualL
title: Funkcja równa się
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710038"
---
# <a name="equall-function"></a><span data-ttu-id="89e3b-102">Funkcja równa się</span><span class="sxs-lookup"><span data-stu-id="89e3b-102">EqualL function</span></span>

<span data-ttu-id="89e3b-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="89e3b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="89e3b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89e3b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="89e3b-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="89e3b-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="89e3b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="89e3b-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="89e3b-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="89e3b-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="89e3b-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="89e3b-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="89e3b-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="89e3b-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="89e3b-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="89e3b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="89e3b-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="89e3b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="89e3b-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="89e3b-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="89e3b-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="89e3b-113">Remarks</span></span>

<span data-ttu-id="89e3b-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="89e3b-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```
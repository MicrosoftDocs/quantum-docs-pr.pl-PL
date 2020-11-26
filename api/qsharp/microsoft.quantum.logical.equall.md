---
uid: Microsoft.Quantum.Logical.EqualL
title: Funkcja równa się
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198116"
---
# <a name="equall-function"></a><span data-ttu-id="ffb60-102">Funkcja równa się</span><span class="sxs-lookup"><span data-stu-id="ffb60-102">EqualL function</span></span>

<span data-ttu-id="ffb60-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ffb60-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ffb60-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ffb60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ffb60-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="ffb60-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="ffb60-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ffb60-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="ffb60-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ffb60-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ffb60-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="ffb60-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="ffb60-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ffb60-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ffb60-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="ffb60-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ffb60-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ffb60-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ffb60-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="ffb60-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ffb60-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ffb60-113">Remarks</span></span>

<span data-ttu-id="ffb60-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="ffb60-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```
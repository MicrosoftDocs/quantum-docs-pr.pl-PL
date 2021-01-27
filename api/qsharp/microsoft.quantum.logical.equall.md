---
uid: Microsoft.Quantum.Logical.EqualL
title: Funkcja równa się
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 58086f40ea20b6f1a5fa6996e3a6703e2bf66306
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815991"
---
# <a name="equall-function"></a><span data-ttu-id="c8547-102">Funkcja równa się</span><span class="sxs-lookup"><span data-stu-id="c8547-102">EqualL function</span></span>

<span data-ttu-id="c8547-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c8547-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c8547-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8547-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8547-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="c8547-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="c8547-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c8547-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c8547-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8547-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8547-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c8547-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="c8547-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8547-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8547-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c8547-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c8547-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c8547-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c8547-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="c8547-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8547-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c8547-113">Remarks</span></span>

<span data-ttu-id="c8547-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="c8547-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualL(a, b);
```
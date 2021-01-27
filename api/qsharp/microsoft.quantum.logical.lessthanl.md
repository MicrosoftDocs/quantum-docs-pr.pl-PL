---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: d5753f9e1447fc1bd433703037fe44c86aaa659c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849146"
---
# <a name="lessthanl-function"></a><span data-ttu-id="0b942-102">LessThanL, funkcja</span><span class="sxs-lookup"><span data-stu-id="0b942-102">LessThanL function</span></span>

<span data-ttu-id="0b942-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0b942-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0b942-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b942-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b942-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza od innej liczby.</span><span class="sxs-lookup"><span data-stu-id="0b942-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="0b942-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0b942-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="0b942-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0b942-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0b942-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="0b942-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="0b942-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0b942-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0b942-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="0b942-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0b942-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0b942-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0b942-112">`true` if i tylko wtedy, gdy `a` jest ściśle mniejsza niż `b` .</span><span class="sxs-lookup"><span data-stu-id="0b942-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b942-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0b942-113">Remarks</span></span>

<span data-ttu-id="0b942-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="0b942-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanL(a, b);
```
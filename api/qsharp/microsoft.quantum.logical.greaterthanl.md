---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 2247c1c1ae8b37b59e87c0c68b06fd1094c9003b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849197"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="c5dc8-102">GreaterThanL, funkcja</span><span class="sxs-lookup"><span data-stu-id="c5dc8-102">GreaterThanL function</span></span>

<span data-ttu-id="c5dc8-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c5dc8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c5dc8-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5dc8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5dc8-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa niż inna liczba.</span><span class="sxs-lookup"><span data-stu-id="c5dc8-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="c5dc8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c5dc8-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c5dc8-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c5dc8-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c5dc8-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c5dc8-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="c5dc8-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c5dc8-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c5dc8-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="c5dc8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c5dc8-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c5dc8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c5dc8-112">`true` if i tylko wtedy, gdy `a` jest ściśle większa niż `b` .</span><span class="sxs-lookup"><span data-stu-id="c5dc8-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5dc8-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c5dc8-113">Remarks</span></span>

<span data-ttu-id="c5dc8-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="c5dc8-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanL(a, b);
```
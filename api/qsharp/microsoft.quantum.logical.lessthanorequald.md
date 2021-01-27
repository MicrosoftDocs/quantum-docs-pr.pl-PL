---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 703b782efe9daccd4f6a339481d49ae9232123f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849138"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="aa5b8-102">LessThanOrEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="aa5b8-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="aa5b8-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="aa5b8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="aa5b8-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa5b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa5b8-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza lub równa innej liczbie.</span><span class="sxs-lookup"><span data-stu-id="aa5b8-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="aa5b8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aa5b8-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="aa5b8-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aa5b8-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aa5b8-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="aa5b8-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="aa5b8-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aa5b8-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aa5b8-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="aa5b8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="aa5b8-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="aa5b8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="aa5b8-112">`true` if i tylko wtedy, gdy `a` jest mniejsza lub równa `b` .</span><span class="sxs-lookup"><span data-stu-id="aa5b8-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa5b8-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="aa5b8-113">Remarks</span></span>

<span data-ttu-id="aa5b8-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="aa5b8-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```
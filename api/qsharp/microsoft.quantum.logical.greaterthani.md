---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 86fc8e927c292a2ea814ed80a33de42bffdb96b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815952"
---
# <a name="greaterthani-function"></a><span data-ttu-id="6ff83-102">GreaterThanI, funkcja</span><span class="sxs-lookup"><span data-stu-id="6ff83-102">GreaterThanI function</span></span>

<span data-ttu-id="6ff83-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6ff83-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6ff83-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ff83-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ff83-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa niż inna liczba.</span><span class="sxs-lookup"><span data-stu-id="6ff83-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="6ff83-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6ff83-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6ff83-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ff83-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ff83-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="6ff83-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="6ff83-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ff83-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ff83-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="6ff83-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6ff83-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6ff83-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6ff83-112">`true` if i tylko wtedy, gdy `a` jest ściśle większa niż `b` .</span><span class="sxs-lookup"><span data-stu-id="6ff83-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ff83-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6ff83-113">Remarks</span></span>

<span data-ttu-id="6ff83-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="6ff83-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanI(a, b);
```
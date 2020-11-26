---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 06cae04150f9f0164b06a4e3d4bb78242b41dc0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197997"
---
# <a name="greaterthani-function"></a><span data-ttu-id="fcb79-102">GreaterThanI, funkcja</span><span class="sxs-lookup"><span data-stu-id="fcb79-102">GreaterThanI function</span></span>

<span data-ttu-id="fcb79-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fcb79-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fcb79-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fcb79-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fcb79-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa niż inna liczba.</span><span class="sxs-lookup"><span data-stu-id="fcb79-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="fcb79-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fcb79-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="fcb79-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcb79-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcb79-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="fcb79-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="fcb79-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcb79-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcb79-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="fcb79-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fcb79-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fcb79-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fcb79-112">`true` if i tylko wtedy, gdy `a` jest ściśle większa niż `b` .</span><span class="sxs-lookup"><span data-stu-id="fcb79-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcb79-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fcb79-113">Remarks</span></span>

<span data-ttu-id="fcb79-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="fcb79-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```
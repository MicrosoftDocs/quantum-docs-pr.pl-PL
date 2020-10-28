---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709982"
---
# <a name="greaterthani-function"></a><span data-ttu-id="5c08e-102">GreaterThanI, funkcja</span><span class="sxs-lookup"><span data-stu-id="5c08e-102">GreaterThanI function</span></span>

<span data-ttu-id="5c08e-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5c08e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5c08e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c08e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c08e-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa niż inna liczba.</span><span class="sxs-lookup"><span data-stu-id="5c08e-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="5c08e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5c08e-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5c08e-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c08e-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c08e-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="5c08e-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="5c08e-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c08e-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c08e-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="5c08e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5c08e-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5c08e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c08e-112">`true` if i tylko wtedy, gdy `a` jest ściśle większa niż `b` .</span><span class="sxs-lookup"><span data-stu-id="5c08e-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c08e-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5c08e-113">Remarks</span></span>

<span data-ttu-id="5c08e-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="5c08e-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```
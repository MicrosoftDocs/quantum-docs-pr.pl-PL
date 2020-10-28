---
uid: Microsoft.Quantum.Logical.EqualI
title: EqualI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 6b805e76217e033cb0135cf85bd8f37a3eb8636a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710052"
---
# <a name="equali-function"></a><span data-ttu-id="429c1-102">EqualI, funkcja</span><span class="sxs-lookup"><span data-stu-id="429c1-102">EqualI function</span></span>

<span data-ttu-id="429c1-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="429c1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="429c1-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="429c1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="429c1-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="429c1-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="429c1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="429c1-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="429c1-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="429c1-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="429c1-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="429c1-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="429c1-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="429c1-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="429c1-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="429c1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="429c1-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="429c1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="429c1-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="429c1-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="429c1-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="429c1-113">Remarks</span></span>

<span data-ttu-id="429c1-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="429c1-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```
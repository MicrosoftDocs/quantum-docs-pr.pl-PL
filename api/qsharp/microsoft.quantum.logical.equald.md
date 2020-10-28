---
uid: Microsoft.Quantum.Logical.EqualD
title: Funkcja równa się
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 024ddee785a6a907b4a39d0eccc5990b4c5d5d83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711396"
---
# <a name="equald-function"></a><span data-ttu-id="655f4-102">Funkcja równa się</span><span class="sxs-lookup"><span data-stu-id="655f4-102">EqualD function</span></span>

<span data-ttu-id="655f4-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="655f4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="655f4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="655f4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="655f4-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="655f4-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="655f4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="655f4-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="655f4-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="655f4-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="655f4-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="655f4-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="655f4-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="655f4-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="655f4-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="655f4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="655f4-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="655f4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="655f4-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="655f4-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="655f4-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="655f4-113">Remarks</span></span>

<span data-ttu-id="655f4-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="655f4-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```
---
uid: Microsoft.Quantum.Logical.EqualD
title: Funkcja równa się
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d6731b293ba402f5cd43591d3c2bcd258e8ebe32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198150"
---
# <a name="equald-function"></a><span data-ttu-id="957d3-102">Funkcja równa się</span><span class="sxs-lookup"><span data-stu-id="957d3-102">EqualD function</span></span>

<span data-ttu-id="957d3-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="957d3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="957d3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="957d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="957d3-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="957d3-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="957d3-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="957d3-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="957d3-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="957d3-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="957d3-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="957d3-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="957d3-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="957d3-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="957d3-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="957d3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="957d3-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="957d3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="957d3-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="957d3-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="957d3-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="957d3-113">Remarks</span></span>

<span data-ttu-id="957d3-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="957d3-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```
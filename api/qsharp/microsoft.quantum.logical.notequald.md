---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723477"
---
# <a name="notequald-function"></a><span data-ttu-id="b114a-102">NotEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="b114a-102">NotEqualD function</span></span>

<span data-ttu-id="b114a-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b114a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b114a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b114a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b114a-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="b114a-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b114a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b114a-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="b114a-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b114a-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b114a-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="b114a-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="b114a-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b114a-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b114a-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="b114a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b114a-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b114a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b114a-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="b114a-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b114a-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b114a-113">Remarks</span></span>

<span data-ttu-id="b114a-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="b114a-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```
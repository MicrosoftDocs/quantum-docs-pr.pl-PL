---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849172"
---
# <a name="lessthand-function"></a><span data-ttu-id="2bb34-102">LessThanD, funkcja</span><span class="sxs-lookup"><span data-stu-id="2bb34-102">LessThanD function</span></span>

<span data-ttu-id="2bb34-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2bb34-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2bb34-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2bb34-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2bb34-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest mniejsza od innej liczby.</span><span class="sxs-lookup"><span data-stu-id="2bb34-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="2bb34-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2bb34-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="2bb34-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2bb34-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2bb34-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="2bb34-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="2bb34-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2bb34-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2bb34-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="2bb34-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2bb34-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2bb34-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2bb34-112">`true` if i tylko wtedy, gdy `a` jest ściśle mniejsza niż `b` .</span><span class="sxs-lookup"><span data-stu-id="2bb34-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2bb34-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2bb34-113">Remarks</span></span>

<span data-ttu-id="2bb34-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="2bb34-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```
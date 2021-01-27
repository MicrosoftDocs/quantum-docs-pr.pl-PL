---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 38f30309a4c27a5ef7e112a09a0efe3b5512d4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849046"
---
# <a name="notequald-function"></a><span data-ttu-id="28404-102">NotEqualD, funkcja</span><span class="sxs-lookup"><span data-stu-id="28404-102">NotEqualD function</span></span>

<span data-ttu-id="28404-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="28404-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="28404-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28404-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28404-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="28404-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="28404-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="28404-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="28404-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="28404-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="28404-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="28404-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="28404-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="28404-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="28404-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="28404-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="28404-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="28404-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="28404-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="28404-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="28404-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="28404-113">Remarks</span></span>

<span data-ttu-id="28404-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="28404-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualD(a, b);
```
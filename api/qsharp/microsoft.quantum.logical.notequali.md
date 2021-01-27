---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814501"
---
# <a name="notequali-function"></a><span data-ttu-id="a61f5-102">NotEqualI, funkcja</span><span class="sxs-lookup"><span data-stu-id="a61f5-102">NotEqualI function</span></span>

<span data-ttu-id="a61f5-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a61f5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a61f5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a61f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a61f5-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="a61f5-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="a61f5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a61f5-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a61f5-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a61f5-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a61f5-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="a61f5-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="a61f5-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a61f5-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a61f5-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="a61f5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a61f5-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a61f5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a61f5-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="a61f5-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a61f5-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a61f5-113">Remarks</span></span>

<span data-ttu-id="a61f5-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="a61f5-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```
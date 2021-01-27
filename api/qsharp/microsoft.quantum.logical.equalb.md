---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 2a15a749f52fe814db4fa57118f69c80fa22158a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817254"
---
# <a name="equalb-function"></a><span data-ttu-id="30203-102">EqualB, funkcja</span><span class="sxs-lookup"><span data-stu-id="30203-102">EqualB function</span></span>

<span data-ttu-id="30203-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="30203-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="30203-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30203-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30203-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="30203-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="30203-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="30203-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="30203-107">Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="30203-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="30203-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="30203-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="30203-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="30203-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="30203-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="30203-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="30203-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="30203-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="30203-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="30203-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="30203-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="30203-113">Remarks</span></span>

<span data-ttu-id="30203-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="30203-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualB(a, b);
```
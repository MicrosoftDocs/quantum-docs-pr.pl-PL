---
uid: Microsoft.Quantum.Logical.EqualD
title: Funkcja równa się
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816866"
---
# <a name="equald-function"></a><span data-ttu-id="46b13-102">Funkcja równa się</span><span class="sxs-lookup"><span data-stu-id="46b13-102">EqualD function</span></span>

<span data-ttu-id="46b13-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="46b13-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="46b13-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46b13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46b13-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="46b13-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="46b13-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="46b13-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="46b13-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="46b13-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="46b13-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="46b13-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="46b13-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="46b13-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="46b13-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="46b13-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="46b13-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="46b13-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="46b13-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="46b13-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="46b13-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="46b13-113">Remarks</span></span>

<span data-ttu-id="46b13-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="46b13-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```
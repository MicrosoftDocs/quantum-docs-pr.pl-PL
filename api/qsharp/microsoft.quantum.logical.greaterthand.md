---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 26a963645758b6de83654304c38830af5c561b3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849215"
---
# <a name="greaterthand-function"></a><span data-ttu-id="d3bae-102">GreaterThanD, funkcja</span><span class="sxs-lookup"><span data-stu-id="d3bae-102">GreaterThanD function</span></span>

<span data-ttu-id="d3bae-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d3bae-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d3bae-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3bae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3bae-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa niż inna liczba.</span><span class="sxs-lookup"><span data-stu-id="d3bae-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="d3bae-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d3bae-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="d3bae-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3bae-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d3bae-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="d3bae-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="d3bae-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3bae-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d3bae-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="d3bae-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d3bae-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d3bae-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d3bae-112">`true` if i tylko wtedy, gdy `a` jest ściśle większa niż `b` .</span><span class="sxs-lookup"><span data-stu-id="d3bae-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3bae-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d3bae-113">Remarks</span></span>

<span data-ttu-id="d3bae-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="d3bae-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanD(a, b);
```
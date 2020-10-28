---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710005"
---
# <a name="greaterthand-function"></a><span data-ttu-id="ee59c-102">GreaterThanD, funkcja</span><span class="sxs-lookup"><span data-stu-id="ee59c-102">GreaterThanD function</span></span>

<span data-ttu-id="ee59c-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ee59c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ee59c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee59c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee59c-105">Zwraca wartość true, jeśli i tylko wtedy, gdy liczba jest większa niż inna liczba.</span><span class="sxs-lookup"><span data-stu-id="ee59c-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="ee59c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ee59c-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="ee59c-107">Odp.: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee59c-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ee59c-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="ee59c-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="ee59c-109">b: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee59c-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ee59c-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="ee59c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ee59c-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ee59c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ee59c-112">`true` if i tylko wtedy, gdy `a` jest ściśle większa niż `b` .</span><span class="sxs-lookup"><span data-stu-id="ee59c-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee59c-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ee59c-113">Remarks</span></span>

<span data-ttu-id="ee59c-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="ee59c-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```
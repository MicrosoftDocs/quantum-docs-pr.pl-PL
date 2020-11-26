---
uid: Microsoft.Quantum.Logical.Or
title: Or — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197130"
---
# <a name="or-function"></a><span data-ttu-id="e470d-102">Or — funkcja</span><span class="sxs-lookup"><span data-stu-id="e470d-102">Or function</span></span>

<span data-ttu-id="e470d-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e470d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e470d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e470d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e470d-105">Zwraca wartość logiczną, która powoduje odłączenie dwóch wartości.</span><span class="sxs-lookup"><span data-stu-id="e470d-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="e470d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e470d-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="e470d-107">Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e470d-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e470d-108">Pierwsza wartość do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="e470d-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="e470d-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e470d-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e470d-110">Druga wartość do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="e470d-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e470d-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e470d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e470d-112">`true` if i tylko wtedy, gdy `a` lub `b` są `true` .</span><span class="sxs-lookup"><span data-stu-id="e470d-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e470d-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e470d-113">Remarks</span></span>

<span data-ttu-id="e470d-114">W przeciwieństwie do `or` operatora, ta funkcja nie jest krótka obwód, tak że oba dane wejściowe są w pełni oceniane.</span><span class="sxs-lookup"><span data-stu-id="e470d-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="e470d-115">W przypadku zachowania do krótkiego obwodu następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="e470d-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```
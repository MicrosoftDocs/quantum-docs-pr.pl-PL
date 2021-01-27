---
uid: Microsoft.Quantum.Logical.Or
title: Or — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848462"
---
# <a name="or-function"></a><span data-ttu-id="23d7e-102">Or — funkcja</span><span class="sxs-lookup"><span data-stu-id="23d7e-102">Or function</span></span>

<span data-ttu-id="23d7e-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="23d7e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="23d7e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23d7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23d7e-105">Zwraca wartość logiczną, która powoduje odłączenie dwóch wartości.</span><span class="sxs-lookup"><span data-stu-id="23d7e-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="23d7e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="23d7e-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="23d7e-107">Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="23d7e-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="23d7e-108">Pierwsza wartość do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="23d7e-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="23d7e-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="23d7e-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="23d7e-110">Druga wartość do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="23d7e-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="23d7e-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="23d7e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="23d7e-112">`true` if i tylko wtedy, gdy `a` lub `b` są `true` .</span><span class="sxs-lookup"><span data-stu-id="23d7e-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="23d7e-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="23d7e-113">Remarks</span></span>

<span data-ttu-id="23d7e-114">W przeciwieństwie do `or` operatora, ta funkcja nie jest krótka obwód, tak że oba dane wejściowe są w pełni oceniane.</span><span class="sxs-lookup"><span data-stu-id="23d7e-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="23d7e-115">W przypadku zachowania do krótkiego obwodu następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="23d7e-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a or b;
let x = Or(a, b);
```
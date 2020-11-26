---
uid: Microsoft.Quantum.Logical.And
title: And — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 279221ed785dd76e28146e4c22e70290936bf529
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198575"
---
# <a name="and-function"></a><span data-ttu-id="fa878-102">And — funkcja</span><span class="sxs-lookup"><span data-stu-id="fa878-102">And function</span></span>

<span data-ttu-id="fa878-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fa878-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fa878-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa878-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa878-105">Zwraca wartość logiczną koniunkcji dwóch wartości.</span><span class="sxs-lookup"><span data-stu-id="fa878-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="fa878-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fa878-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="fa878-107">Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fa878-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fa878-108">Pierwsza wartość do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="fa878-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="fa878-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fa878-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fa878-110">Druga wartość do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="fa878-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fa878-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fa878-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fa878-112">`true` if i tylko wtedy `a` , gdy i `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="fa878-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa878-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fa878-113">Remarks</span></span>

<span data-ttu-id="fa878-114">W przeciwieństwie do `and` operatora, ta funkcja nie jest krótka obwód, tak że oba dane wejściowe są w pełni oceniane.</span><span class="sxs-lookup"><span data-stu-id="fa878-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="fa878-115">W przypadku zachowania do krótkiego obwodu następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="fa878-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```
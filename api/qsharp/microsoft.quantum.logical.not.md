---
uid: Microsoft.Quantum.Logical.Not
title: Not — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197453"
---
# <a name="not-function"></a><span data-ttu-id="31e2f-102">Not — funkcja</span><span class="sxs-lookup"><span data-stu-id="31e2f-102">Not function</span></span>

<span data-ttu-id="31e2f-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="31e2f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="31e2f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31e2f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31e2f-105">Zwraca wartość logiczną negacji wartości.</span><span class="sxs-lookup"><span data-stu-id="31e2f-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="31e2f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="31e2f-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="31e2f-107">wartość: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="31e2f-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="31e2f-108">Wartość, która ma być Negacja.</span><span class="sxs-lookup"><span data-stu-id="31e2f-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="31e2f-109">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="31e2f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="31e2f-110">`true` if i tylko wtedy, gdy `value` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="31e2f-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="31e2f-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="31e2f-111">Remarks</span></span>

<span data-ttu-id="31e2f-112">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="31e2f-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```
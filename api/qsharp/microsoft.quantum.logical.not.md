---
uid: Microsoft.Quantum.Logical.Not
title: Not — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709865"
---
# <a name="not-function"></a><span data-ttu-id="e3bf2-102">Not — funkcja</span><span class="sxs-lookup"><span data-stu-id="e3bf2-102">Not function</span></span>

<span data-ttu-id="e3bf2-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e3bf2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3bf2-105">Zwraca wartość logiczną negacji wartości.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="e3bf2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e3bf2-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="e3bf2-107">wartość: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e3bf2-108">Wartość, która ma być Negacja.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e3bf2-109">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e3bf2-110">`true` if i tylko wtedy, gdy `value` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="e3bf2-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3bf2-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e3bf2-111">Remarks</span></span>

<span data-ttu-id="e3bf2-112">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="e3bf2-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```
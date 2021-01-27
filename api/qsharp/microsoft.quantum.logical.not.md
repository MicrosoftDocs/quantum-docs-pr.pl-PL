---
uid: Microsoft.Quantum.Logical.Not
title: Not — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849086"
---
# <a name="not-function"></a><span data-ttu-id="c5505-102">Not — funkcja</span><span class="sxs-lookup"><span data-stu-id="c5505-102">Not function</span></span>

<span data-ttu-id="c5505-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c5505-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c5505-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5505-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5505-105">Zwraca wartość logiczną negacji wartości.</span><span class="sxs-lookup"><span data-stu-id="c5505-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="c5505-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c5505-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="c5505-107">wartość: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c5505-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c5505-108">Wartość, która ma być Negacja.</span><span class="sxs-lookup"><span data-stu-id="c5505-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c5505-109">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c5505-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c5505-110">`true` if i tylko wtedy, gdy `value` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="c5505-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5505-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c5505-111">Remarks</span></span>

<span data-ttu-id="c5505-112">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="c5505-112">The following are equivalent:</span></span>

```qsharp
let x = not value;
let x = Not(value);
```
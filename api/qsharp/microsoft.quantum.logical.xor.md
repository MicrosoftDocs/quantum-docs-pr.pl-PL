---
uid: Microsoft.Quantum.Logical.Xor
title: XOR — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723295"
---
# <a name="xor-function"></a><span data-ttu-id="6ece7-102">XOR — funkcja</span><span class="sxs-lookup"><span data-stu-id="6ece7-102">Xor function</span></span>

<span data-ttu-id="6ece7-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6ece7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6ece7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ece7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ece7-105">Zwraca wartość logiczną bez odłączenia dwóch wartości.</span><span class="sxs-lookup"><span data-stu-id="6ece7-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="6ece7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6ece7-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="6ece7-107">Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6ece7-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6ece7-108">Pierwsza wartość do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="6ece7-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="6ece7-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6ece7-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6ece7-110">Druga wartość do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="6ece7-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6ece7-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6ece7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6ece7-112">`true` if i tylko wtedy, gdy dokładnie jeden z `a` i `b` jest `true` .</span><span class="sxs-lookup"><span data-stu-id="6ece7-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>
---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 7943411b662683df058213a9e4b8eb7c9329ff07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197385"
---
# <a name="notequalb-function"></a><span data-ttu-id="984ca-102">NotEqualB, funkcja</span><span class="sxs-lookup"><span data-stu-id="984ca-102">NotEqualB function</span></span>

<span data-ttu-id="984ca-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="984ca-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="984ca-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="984ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="984ca-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="984ca-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="984ca-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="984ca-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="984ca-107">Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="984ca-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="984ca-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="984ca-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="984ca-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="984ca-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="984ca-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="984ca-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="984ca-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="984ca-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="984ca-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="984ca-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="984ca-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="984ca-113">Remarks</span></span>

<span data-ttu-id="984ca-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="984ca-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```
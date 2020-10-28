---
uid: Microsoft.Quantum.Logical.EqualR
title: Funkcja równości
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710033"
---
# <a name="equalr-function"></a><span data-ttu-id="8f59a-102">Funkcja równości</span><span class="sxs-lookup"><span data-stu-id="8f59a-102">EqualR function</span></span>

<span data-ttu-id="8f59a-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8f59a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8f59a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8f59a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8f59a-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe są równe.</span><span class="sxs-lookup"><span data-stu-id="8f59a-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="8f59a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8f59a-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="8f59a-107">Odp. __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="8f59a-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="8f59a-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="8f59a-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="8f59a-109">b: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="8f59a-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="8f59a-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="8f59a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8f59a-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8f59a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8f59a-112">`true` if i tylko wtedy, gdy `a` jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="8f59a-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f59a-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8f59a-113">Remarks</span></span>

<span data-ttu-id="8f59a-114">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="8f59a-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```
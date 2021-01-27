---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 33049b09405529bd418ff8652b6cb0f11bf734f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849071"
---
# <a name="notequalc-function"></a><span data-ttu-id="a034c-102">NotEqualC, funkcja</span><span class="sxs-lookup"><span data-stu-id="a034c-102">NotEqualC function</span></span>

<span data-ttu-id="a034c-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a034c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a034c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a034c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a034c-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="a034c-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="a034c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a034c-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="a034c-107">Odp.: [złożona](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="a034c-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="a034c-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="a034c-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="a034c-109">b: [złożone](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="a034c-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="a034c-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="a034c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a034c-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a034c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a034c-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="a034c-112">`true` if and only if `a` is not equal to `b`.</span></span>
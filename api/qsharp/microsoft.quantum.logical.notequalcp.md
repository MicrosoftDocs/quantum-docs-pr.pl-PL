---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 81dd998353f674d55afe85dd20904047391bdb40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720741"
---
# <a name="notequalcp-function"></a><span data-ttu-id="40c85-102">NotEqualCP, funkcja</span><span class="sxs-lookup"><span data-stu-id="40c85-102">NotEqualCP function</span></span>

<span data-ttu-id="40c85-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="40c85-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="40c85-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="40c85-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="40c85-105">Zwraca wartość true, jeśli i tylko wtedy, gdy dwa dane wejściowe nie są równe.</span><span class="sxs-lookup"><span data-stu-id="40c85-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="40c85-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="40c85-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="40c85-107">Odp.: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="40c85-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="40c85-108">Pierwsza wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="40c85-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="40c85-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="40c85-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="40c85-110">Druga wartość do porównania.</span><span class="sxs-lookup"><span data-stu-id="40c85-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="40c85-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="40c85-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="40c85-112">`true` if i tylko wtedy, gdy `a` nie jest równa `b` .</span><span class="sxs-lookup"><span data-stu-id="40c85-112">`true` if and only if `a` is not equal to `b`.</span></span>
---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211104"
---
# <a name="argcomplex-function"></a><span data-ttu-id="50c4e-102">ArgComplex, funkcja</span><span class="sxs-lookup"><span data-stu-id="50c4e-102">ArgComplex function</span></span>

<span data-ttu-id="50c4e-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="50c4e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="50c4e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50c4e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="50c4e-105">Zwraca fazę złożonej liczby typów `Complex` .</span><span class="sxs-lookup"><span data-stu-id="50c4e-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="50c4e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="50c4e-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="50c4e-107">dane wejściowe: [złożone](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="50c4e-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="50c4e-108">Liczba złożona $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="50c4e-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="50c4e-109">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50c4e-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="50c4e-110">Faza $ \text{Arg} [c] = \text{ArcTan} (y, x) \In (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="50c4e-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>
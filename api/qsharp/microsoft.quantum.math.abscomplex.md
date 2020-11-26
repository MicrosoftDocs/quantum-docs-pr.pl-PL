---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d9afb4b9b37b6cdd83bfd3829d3174d769c5f41b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211393"
---
# <a name="abscomplex-function"></a><span data-ttu-id="cfbb4-102">AbsComplex, funkcja</span><span class="sxs-lookup"><span data-stu-id="cfbb4-102">AbsComplex function</span></span>

<span data-ttu-id="cfbb4-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cfbb4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cfbb4-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfbb4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfbb4-105">Zwraca wartość bezwzględną złożonej liczby typu `Complex` .</span><span class="sxs-lookup"><span data-stu-id="cfbb4-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="cfbb4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cfbb4-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="cfbb4-107">dane wejściowe: [złożone](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="cfbb4-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="cfbb4-108">Liczba złożona $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="cfbb4-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="cfbb4-109">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cfbb4-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cfbb4-110">Wartość bezwzględna $ | c | = \sqrt{x ^ 2 + y ^ 2} $.</span><span class="sxs-lookup"><span data-stu-id="cfbb4-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>
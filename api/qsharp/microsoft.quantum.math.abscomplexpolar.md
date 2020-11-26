---
uid: Microsoft.Quantum.Math.AbsComplexPolar
title: AbsComplexPolar, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplexPolar
qsharp.summary: Returns the absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 01845556cbabde768f9c7c47c733453048df9416
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195991"
---
# <a name="abscomplexpolar-function"></a><span data-ttu-id="ceab5-102">AbsComplexPolar, funkcja</span><span class="sxs-lookup"><span data-stu-id="ceab5-102">AbsComplexPolar function</span></span>

<span data-ttu-id="ceab5-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ceab5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ceab5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ceab5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ceab5-105">Zwraca wartość bezwzględną złożonej liczby typu `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="ceab5-105">Returns the absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="ceab5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ceab5-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="ceab5-107">dane wejściowe: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="ceab5-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="ceab5-108">Liczba złożona $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="ceab5-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="ceab5-109">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ceab5-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ceab5-110">Wartość bezwzględna $ | c | = r $.</span><span class="sxs-lookup"><span data-stu-id="ceab5-110">Absolute value $|c| = r$.</span></span>
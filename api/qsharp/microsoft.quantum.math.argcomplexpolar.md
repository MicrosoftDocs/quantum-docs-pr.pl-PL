---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 7088397bd60e2779ef60afc1bb7108d937a62c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195770"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="510a0-102">ArgComplexPolar, funkcja</span><span class="sxs-lookup"><span data-stu-id="510a0-102">ArgComplexPolar function</span></span>

<span data-ttu-id="510a0-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="510a0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="510a0-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="510a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="510a0-105">Zwraca fazę złożonej liczby typów `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="510a0-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="510a0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="510a0-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="510a0-107">dane wejściowe: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="510a0-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="510a0-108">Liczba złożona $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="510a0-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="510a0-109">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="510a0-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="510a0-110">Faza $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="510a0-110">Phase $\text{Arg}[c] = t$.</span></span>
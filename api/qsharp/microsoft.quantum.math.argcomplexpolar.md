---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: b4f2b9a192770f453302b469c80f03a9e57cf891
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723216"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="a542a-102">ArgComplexPolar, funkcja</span><span class="sxs-lookup"><span data-stu-id="a542a-102">ArgComplexPolar function</span></span>

<span data-ttu-id="a542a-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a542a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a542a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a542a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a542a-105">Zwraca fazę złożonej liczby typów `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="a542a-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="a542a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a542a-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="a542a-107">dane wejściowe: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="a542a-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="a542a-108">Liczba złożona $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="a542a-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="a542a-109">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a542a-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a542a-110">Faza $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="a542a-110">Phase $\text{Arg}[c] = t$.</span></span>
---
uid: Microsoft.Quantum.Simulation._MultiplyGeneratorSystem
title: Funkcja _MultiplyGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 9fdc52bdea69e9507510a51be258eaba8e61f673
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229685"
---
# <a name="_multiplygeneratorsystem-function"></a><span data-ttu-id="22e28-102">Funkcja _MultiplyGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="22e28-102">_MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="22e28-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="22e28-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="22e28-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22e28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22e28-105">Mnoży współczynnik wszystkich warunków w `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="22e28-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function _MultiplyGeneratorSystem (multiplier : Double, idxTerm : Int, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="22e28-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="22e28-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="22e28-107">mnożnik: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="22e28-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="idxterm--int"></a><span data-ttu-id="22e28-108">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22e28-108">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="22e28-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="22e28-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>





## <a name="output--generatorindex"></a><span data-ttu-id="22e28-110">Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="22e28-110">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>



## <a name="remarks"></a><span data-ttu-id="22e28-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="22e28-111">Remarks</span></span>

<span data-ttu-id="22e28-112">Jest to krok pośredni i nie należy go wywoływać.</span><span class="sxs-lookup"><span data-stu-id="22e28-112">This is an intermediate step and should not be called.</span></span>
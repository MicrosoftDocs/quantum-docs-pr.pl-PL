---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: InterpolateGeneratorSystems, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: ee47637996313fe1b77c76f00b08417dac956247
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230586"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="57915-102">InterpolateGeneratorSystems, funkcja</span><span class="sxs-lookup"><span data-stu-id="57915-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="57915-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="57915-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="57915-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57915-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57915-105">Zwraca wartość `TimeDependentGeneratorSystem` reprezentującą interpolację liniową między dwoma `GeneratorSystem` s.</span><span class="sxs-lookup"><span data-stu-id="57915-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="57915-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="57915-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="57915-107">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="57915-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="57915-108">Rozpoczęcie `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="57915-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="57915-109">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="57915-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="57915-110">Koniec `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="57915-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="57915-111">Wynik: [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="57915-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="57915-112">`TimeDependentGeneratorSystem`Reprezentuje system, który jest sumą systemów generatora danych wejściowych, z wagami $ (1-s) $ on `generatorSystemStart` i wag $s $ on `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="57915-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="57915-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="57915-113">See Also</span></span>

- [<span data-ttu-id="57915-114">Microsoft. Quantum. Symulacja. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="57915-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="57915-115">Microsoft. Quantum. Symulacja. TimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="57915-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)
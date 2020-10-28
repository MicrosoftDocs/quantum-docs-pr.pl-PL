---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 212ed4c473fab3572f73ea250061057ad13e393f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709436"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="928e5-102">InterpolateGeneratorSystemsImpl, funkcja</span><span class="sxs-lookup"><span data-stu-id="928e5-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="928e5-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="928e5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="928e5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="928e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="928e5-105">Liniowie interpoluje między dwoma `GeneratorSystems` zgodnie z parametrem harmonogramu z `s` przedziału od 0 do 1 (włącznie).</span><span class="sxs-lookup"><span data-stu-id="928e5-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="928e5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="928e5-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="928e5-107">Harmonogram: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="928e5-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="928e5-108">Parametr harmonogramu $s \In [0, 1] $.</span><span class="sxs-lookup"><span data-stu-id="928e5-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="928e5-109">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="928e5-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="928e5-110">Rozpoczęcie `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="928e5-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="928e5-111">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="928e5-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="928e5-112">Koniec `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="928e5-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="928e5-113">Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="928e5-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="928e5-114">`GeneratorSystem`Reprezentuje system, który jest sumą systemów generatora danych wejściowych, z wagami $ (1-s) $ on `generatorSystemStart` i wag $s $ on `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="928e5-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="928e5-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="928e5-115">See Also</span></span>

- [<span data-ttu-id="928e5-116">Microsoft. Quantum. Symulacja. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="928e5-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
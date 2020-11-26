---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229158"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="eeb25-102">MultiplyGeneratorSystem, funkcja</span><span class="sxs-lookup"><span data-stu-id="eeb25-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="eeb25-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="eeb25-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="eeb25-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eeb25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eeb25-105">Mnoży współczynnik wszystkich warunków w `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="eeb25-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="eeb25-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="eeb25-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="eeb25-107">mnożnik: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eeb25-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eeb25-108">Mnożnik na współczynniku.</span><span class="sxs-lookup"><span data-stu-id="eeb25-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="eeb25-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="eeb25-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="eeb25-110">`GeneratorSystem`Do pomnożenia.</span><span class="sxs-lookup"><span data-stu-id="eeb25-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="eeb25-111">Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="eeb25-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="eeb25-112">`GeneratorSystem`Reprezentuje system z współczynnikiem większego współczynnika `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="eeb25-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="eeb25-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eeb25-113">See Also</span></span>

- [<span data-ttu-id="eeb25-114">Microsoft. Quantum. Symulacja. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="eeb25-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: AddGeneratorSystems, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: d6e8f7085cf0558960d055dbeeb08740c3fab049
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229668"
---
# <a name="addgeneratorsystems-function"></a><span data-ttu-id="a7634-102">AddGeneratorSystems, funkcja</span><span class="sxs-lookup"><span data-stu-id="a7634-102">AddGeneratorSystems function</span></span>

<span data-ttu-id="a7634-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a7634-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a7634-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7634-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7634-105">Dodaje dwa `GeneratorSystem` s, aby utworzyć nowy `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="a7634-105">Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.</span></span>

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="a7634-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a7634-106">Input</span></span>

### <a name="generatorsystema--generatorsystem"></a><span data-ttu-id="a7634-107">generatorSystemA: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a7634-107">generatorSystemA : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a7634-108">Pierwszy element `GeneratorSystem`.</span><span class="sxs-lookup"><span data-stu-id="a7634-108">The first `GeneratorSystem`.</span></span>


### <a name="generatorsystemb--generatorsystem"></a><span data-ttu-id="a7634-109">generatorSystemB: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a7634-109">generatorSystemB : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a7634-110">Drugi element `GeneratorSystem`.</span><span class="sxs-lookup"><span data-stu-id="a7634-110">The second `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="a7634-111">Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a7634-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a7634-112">`GeneratorSystem`Reprezentuje system, który jest sumą systemów generatora danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="a7634-112">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7634-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a7634-113">See Also</span></span>

- [<span data-ttu-id="a7634-114">Microsoft. Quantum. Symulacja. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="a7634-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
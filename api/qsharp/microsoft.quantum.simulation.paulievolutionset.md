---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722049"
---
# <a name="paulievolutionset-function"></a><span data-ttu-id="91652-102">PauliEvolutionSet, funkcja</span><span class="sxs-lookup"><span data-stu-id="91652-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="91652-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="91652-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="91652-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="91652-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="91652-105">Reprezentuje Generator dynamiczny jako zestaw bram, które są symulowane i rozszerzanie w Pauli.</span><span class="sxs-lookup"><span data-stu-id="91652-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="91652-106">Wynik: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="91652-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="91652-107">`EvolutionSet`Mapowanie a `GeneratorIndex` dla podstawy Pauli na element "EvolutionUnitary".</span><span class="sxs-lookup"><span data-stu-id="91652-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="91652-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="91652-108">Remarks</span></span>

<span data-ttu-id="91652-109">Jest to uzyskiwane w częściowej aplikacji <xref:microsoft.quantum.simulation.paulievolutionfunction> .</span><span class="sxs-lookup"><span data-stu-id="91652-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>
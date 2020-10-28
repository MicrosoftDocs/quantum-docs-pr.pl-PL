---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: SimulationAlgorithm typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 9127a936bbf7a212e712645eabdf49fefc7a97d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725568"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="ad0b6-102">SimulationAlgorithm typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="ad0b6-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="ad0b6-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ad0b6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ad0b6-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad0b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad0b6-105">Reprezentuje algorytm symulacji niezależny od czasu.</span><span class="sxs-lookup"><span data-stu-id="ad0b6-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="ad0b6-106">Technika symulacji niezależna od czasu konwertuje <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="ad0b6-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="ad0b6-107">do przydzielenia czasu jednostkowego dla pewnego interwału czasu.</span><span class="sxs-lookup"><span data-stu-id="ad0b6-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```


---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TimeDependentSimulationAlgorithm typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: b495a9fd96c78872f84e8f8183105f6290f70655
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192523"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="8f457-102">TimeDependentSimulationAlgorithm typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="8f457-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="8f457-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8f457-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8f457-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f457-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f457-105">Reprezentuje algorytm symulacji zależny od czasu.</span><span class="sxs-lookup"><span data-stu-id="8f457-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="8f457-106">Technika symulacji zależna od czasu konwertuje <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="8f457-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="8f457-107">na czas jednostkowy — ewolucję dla pewnego interwału czasu.</span><span class="sxs-lookup"><span data-stu-id="8f457-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```


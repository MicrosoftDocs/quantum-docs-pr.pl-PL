---
uid: Microsoft.Quantum.Simulation.EvolutionSchedule
title: EvolutionSchedule typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSchedule
qsharp.summary: >-
  Represents a time-dependent dynamical generator.

  The `Double` parameter is a schedule in $[0, 1]$.
ms.openlocfilehash: f99c72a44acc3fdcd9c0f182b51d9437b5e6606d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225299"
---
# <a name="evolutionschedule-user-defined-type"></a><span data-ttu-id="b7392-102">EvolutionSchedule typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="b7392-102">EvolutionSchedule user defined type</span></span>

<span data-ttu-id="b7392-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b7392-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b7392-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7392-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7392-105">Reprezentuje Generator dynamiczny zależny od czasu.</span><span class="sxs-lookup"><span data-stu-id="b7392-105">Represents a time-dependent dynamical generator.</span></span>

<span data-ttu-id="b7392-106">`Double`Parametr jest harmonogramem w $ [0, 1] $.</span><span class="sxs-lookup"><span data-stu-id="b7392-106">The `Double` parameter is a schedule in $[0, 1]$.</span></span>

```qsharp

newtype EvolutionSchedule = (Microsoft.Quantum.Simulation.EvolutionSet, (Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```


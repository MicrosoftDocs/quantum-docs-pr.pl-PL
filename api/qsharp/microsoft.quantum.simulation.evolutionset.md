---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710612"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="a8ee3-102">EvolutionSet typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="a8ee3-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="a8ee3-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a8ee3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a8ee3-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8ee3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8ee3-105">Reprezentuje zestaw bram, które mogą być łatwo zaimplementowane i używane do implementowania algorytmów symulacji.</span><span class="sxs-lookup"><span data-stu-id="a8ee3-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="a8ee3-106">Elementy w zestawie są indeksowane przez  <xref:microsoft.quantum.simulation.generatorindex> , a każdy zestaw jest opisany przez funkcję z `GeneratorIndex` do  <xref:microsoft.quantum.simulation.evolutionunitary> , które są operacjami sparametryzowanymi przez wartość rzeczywistą reprezentującą czas</span><span class="sxs-lookup"><span data-stu-id="a8ee3-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```


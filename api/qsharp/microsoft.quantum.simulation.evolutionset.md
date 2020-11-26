---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: ee8f3c0716f035dcb0c4fad557092fbf8dd3c356
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229413"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="8101a-102">EvolutionSet typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="8101a-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="8101a-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8101a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8101a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8101a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8101a-105">Reprezentuje zestaw bram, które mogą być łatwo zaimplementowane i używane do implementowania algorytmów symulacji.</span><span class="sxs-lookup"><span data-stu-id="8101a-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="8101a-106">Elementy w zestawie są indeksowane przez  <xref:microsoft.quantum.simulation.generatorindex> , a każdy zestaw jest opisany przez funkcję z `GeneratorIndex` do  <xref:microsoft.quantum.simulation.evolutionunitary> , które są operacjami sparametryzowanymi przez wartość rzeczywistą reprezentującą czas</span><span class="sxs-lookup"><span data-stu-id="8101a-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```


---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: EvolutionSet typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 35c0b24da284a5871fd11b6d624102b853b89d19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856070"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="d67f3-102">EvolutionSet typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="d67f3-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="d67f3-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d67f3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d67f3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d67f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d67f3-105">Reprezentuje zestaw bram, które mogą być łatwo zaimplementowane i używane do implementowania algorytmów symulacji.</span><span class="sxs-lookup"><span data-stu-id="d67f3-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="d67f3-106">Elementy w zestawie są indeksowane przez  <xref:microsoft.quantum.simulation.generatorindex> , a każdy zestaw jest opisany przez funkcję z `GeneratorIndex` do  <xref:microsoft.quantum.simulation.evolutionunitary> , które są operacjami sparametryzowanymi przez wartość rzeczywistą reprezentującą czas</span><span class="sxs-lookup"><span data-stu-id="d67f3-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```


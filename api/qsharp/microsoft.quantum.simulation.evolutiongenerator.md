---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: EvolutionGenerator typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: 98241f77bfbd73929896bb114fad060001016a86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856085"
---
# <a name="evolutiongenerator-user-defined-type"></a><span data-ttu-id="2110a-102">EvolutionGenerator typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="2110a-102">EvolutionGenerator user defined type</span></span>

<span data-ttu-id="2110a-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2110a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2110a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2110a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2110a-105">Reprezentuje Generator dynamiczny jako zbiór bram, które są symulowane i rozwinięcie w tym zakresie.</span><span class="sxs-lookup"><span data-stu-id="2110a-105">Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.</span></span>

<span data-ttu-id="2110a-106">Ostatni parametr dla liczby warunków.</span><span class="sxs-lookup"><span data-stu-id="2110a-106">Last parameter for number of terms.</span></span>

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```


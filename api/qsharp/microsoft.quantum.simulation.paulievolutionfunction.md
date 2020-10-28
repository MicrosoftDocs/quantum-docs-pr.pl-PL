---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: PauliEvolutionFunction, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 060f4e4f23bb8b47518a3a22bbca8ab0be6e13b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720201"
---
# <a name="paulievolutionfunction-function"></a><span data-ttu-id="b0aa2-102">PauliEvolutionFunction, funkcja</span><span class="sxs-lookup"><span data-stu-id="b0aa2-102">PauliEvolutionFunction function</span></span>

<span data-ttu-id="b0aa2-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b0aa2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b0aa2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b0aa2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b0aa2-105">Reprezentuje Generator dynamiczny jako zestaw bram, które są symulowane i rozszerzanie w Pauli.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="b0aa2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b0aa2-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="b0aa2-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b0aa2-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b0aa2-108">Indeks generatora, który ma być reprezentowany jako ewolucja jednostkowa na podstawie Pauli.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-108">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="b0aa2-109">Wynik: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="b0aa2-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="b0aa2-110">`EvolutionUnitary`Przedstawiający ewolucję czasu przez termin przywoływany w elemencie "generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="b0aa2-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>
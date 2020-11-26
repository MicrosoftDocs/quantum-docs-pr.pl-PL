---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: JWOptimizedFermionEvolutionFunction, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 40a4bccc6cf74a63c354bfd628baa45768916fe2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229923"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a><span data-ttu-id="4fa56-102">JWOptimizedFermionEvolutionFunction, funkcja</span><span class="sxs-lookup"><span data-stu-id="4fa56-102">JWOptimizedFermionEvolutionFunction function</span></span>

<span data-ttu-id="4fa56-103">Przestrzeń nazw: [Microsoft. Quantum. Research. Chemia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4fa56-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="4fa56-104">Pakiet: [Microsoft. Quantum. Research. Chemia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4fa56-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="4fa56-105">Reprezentuje Generator dynamiczny jako zestaw bram, które są symulowane i rozszerzanie w JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="4fa56-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="4fa56-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4fa56-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="4fa56-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4fa56-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4fa56-108">Indeks generatora, który ma być reprezentowany jako ewolucja jednostkowa na podstawie JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="4fa56-108">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="4fa56-109">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4fa56-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4fa56-110">Qubit, który określa znak ewolucji czasu.</span><span class="sxs-lookup"><span data-stu-id="4fa56-110">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="4fa56-111">Wynik: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="4fa56-111">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="4fa56-112">`EvolutionUnitary`Przedstawiający ewolucję czasu przez termin przywoływany w elemencie "generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="4fa56-112">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>
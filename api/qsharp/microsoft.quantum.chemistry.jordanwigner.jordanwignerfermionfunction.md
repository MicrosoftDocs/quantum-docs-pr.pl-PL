---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: e1eeed0dcd4084401e2680ff1188db4225ee85ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214759"
---
# <a name="jordanwignerfermionfunction-function"></a><span data-ttu-id="1b20f-102">JordanWignerFermionFunction, funkcja</span><span class="sxs-lookup"><span data-stu-id="1b20f-102">JordanWignerFermionFunction function</span></span>

<span data-ttu-id="1b20f-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1b20f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1b20f-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1b20f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="1b20f-105">Reprezentuje Generator dynamiczny jako zestaw bram, które są symulowane i rozszerzanie w JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="1b20f-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="1b20f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1b20f-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="1b20f-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="1b20f-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="1b20f-108">Indeks generatora, który ma być reprezentowany jako ewolucja jednostkowa w JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="1b20f-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="1b20f-109">Wynik: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="1b20f-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="1b20f-110">`EvolutionUnitary`Przedstawiający ewolucję czasu przez termin przywoływany w elemencie "generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="1b20f-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>
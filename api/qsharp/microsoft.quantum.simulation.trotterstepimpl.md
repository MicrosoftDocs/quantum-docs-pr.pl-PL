---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: TrotterStepImpl, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725325"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="3f96d-102">TrotterStepImpl, operacja</span><span class="sxs-lookup"><span data-stu-id="3f96d-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="3f96d-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3f96d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3f96d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f96d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f96d-105">Implementuje ewolucję czasową przez termin zawarty w `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="3f96d-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3f96d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3f96d-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="3f96d-107">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="3f96d-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="3f96d-108">Pełny opis systemu, który ma zostać symulowany.</span><span class="sxs-lookup"><span data-stu-id="3f96d-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="3f96d-109">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3f96d-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3f96d-110">Indeks liczby całkowitej na termin w opisanym systemie.</span><span class="sxs-lookup"><span data-stu-id="3f96d-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="3f96d-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3f96d-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3f96d-112">Mnożnik dotyczący czasu trwania ewolucji według terminu indeksowanego przez `idx` .</span><span class="sxs-lookup"><span data-stu-id="3f96d-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="3f96d-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3f96d-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3f96d-114">Qubits działały na podstawie symulacji.</span><span class="sxs-lookup"><span data-stu-id="3f96d-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f96d-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f96d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

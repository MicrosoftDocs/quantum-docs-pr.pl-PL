---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: PauliEvolutionImpl, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 868f3eef187e8e993127cfcab21e1574583ac845
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229141"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="016aa-102">PauliEvolutionImpl, operacja</span><span class="sxs-lookup"><span data-stu-id="016aa-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="016aa-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="016aa-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="016aa-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="016aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="016aa-105">Reprezentuje Generator dynamiczny jako zestaw bram, które są symulowane i rozszerzanie w Pauli.</span><span class="sxs-lookup"><span data-stu-id="016aa-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="016aa-106">Zobacz [dynamiczne modelowanie generatora](/quantum/libraries/data-structures#dynamical-generator-modeling) , aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="016aa-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="016aa-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="016aa-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="016aa-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="016aa-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="016aa-109">Indeks generatora, który ma być reprezentowany jako ewolucja jednostkowa na podstawie Pauli.</span><span class="sxs-lookup"><span data-stu-id="016aa-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="016aa-110">Delta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="016aa-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="016aa-111">Mnożnik dotyczący czasu trwania ewolucji przez termin przywoływany w `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="016aa-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="016aa-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="016aa-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="016aa-113">Zarejestruj działania podejmowane przez operator zmiany czasu.</span><span class="sxs-lookup"><span data-stu-id="016aa-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="016aa-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="016aa-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


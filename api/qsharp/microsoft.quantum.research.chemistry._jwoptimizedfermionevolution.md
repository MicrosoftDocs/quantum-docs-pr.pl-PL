---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: Operacja _JWOptimizedFermionEvolution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 5976b65d44c0e8597088dbaa6b85ffde634edcdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722796"
---
# <a name="_jwoptimizedfermionevolution-operation"></a><span data-ttu-id="2fb30-102">Operacja _JWOptimizedFermionEvolution</span><span class="sxs-lookup"><span data-stu-id="2fb30-102">_JWOptimizedFermionEvolution operation</span></span>

<span data-ttu-id="2fb30-103">Przestrzeń nazw: [Microsoft. Quantum. Research. Chemia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2fb30-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="2fb30-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2fb30-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2fb30-105">Reprezentuje Generator dynamiczny jako zestaw bram, które są symulowane i rozszerzanie w JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="2fb30-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

<span data-ttu-id="2fb30-106">Zobacz [dynamiczne modelowanie generatora](../libraries/data-structures#dynamical-generator-modeling) , aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="2fb30-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2fb30-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2fb30-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="2fb30-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2fb30-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2fb30-109">Indeks generatora, który ma być reprezentowany jako ewolucja jednostkowa na podstawie JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="2fb30-109">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="2fb30-110">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2fb30-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2fb30-111">Mnożnik dotyczący czasu trwania ewolucji przez termin przywoływany w `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="2fb30-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="2fb30-112">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2fb30-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2fb30-113">Qubit, który określa znak ewolucji czasu.</span><span class="sxs-lookup"><span data-stu-id="2fb30-113">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2fb30-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2fb30-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2fb30-115">Zarejestruj działania podejmowane przez operator zmiany czasu.</span><span class="sxs-lookup"><span data-stu-id="2fb30-115">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fb30-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fb30-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


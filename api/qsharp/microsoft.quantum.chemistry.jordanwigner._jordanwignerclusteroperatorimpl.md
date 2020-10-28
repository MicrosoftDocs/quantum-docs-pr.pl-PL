---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorImpl
title: Operacja _JordanWignerClusterOperatorImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 9507558ebe73bce87d9089aad22b94c1d9d579d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714602"
---
# <a name="_jordanwignerclusteroperatorimpl-operation"></a><span data-ttu-id="106d3-102">Operacja _JordanWignerClusterOperatorImpl</span><span class="sxs-lookup"><span data-stu-id="106d3-102">_JordanWignerClusterOperatorImpl operation</span></span>

<span data-ttu-id="106d3-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="106d3-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="106d3-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="106d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="106d3-105">Reprezentuje Generator dynamiczny jako zestaw bram, które są symulowane i rozszerzanie w JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="106d3-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="106d3-106">Zobacz [dynamiczne modelowanie generatora](../libraries/data-structures#dynamical-generator-modeling) , aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="106d3-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JordanWignerClusterOperatorImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="106d3-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="106d3-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="106d3-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="106d3-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="106d3-109">Indeks generatora, który ma być reprezentowany jako ewolucja jednostkowa w JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="106d3-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="106d3-110">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="106d3-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="106d3-111">Zmienna fikcyjna, aby dopasować sygnaturę algorytmów symulacji.</span><span class="sxs-lookup"><span data-stu-id="106d3-111">Dummy variable to match signature of simulation algorithms.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="106d3-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="106d3-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="106d3-113">Zarejestruj działania podejmowane przez operator zmiany czasu.</span><span class="sxs-lookup"><span data-stu-id="106d3-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="106d3-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="106d3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


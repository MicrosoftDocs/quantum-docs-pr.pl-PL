---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionImpl
title: JordanWignerFermionImpl, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 616174d4d7f5ac8f4cea9454098d819468076648
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714009"
---
# <a name="jordanwignerfermionimpl-operation"></a><span data-ttu-id="e4792-102">JordanWignerFermionImpl, operacja</span><span class="sxs-lookup"><span data-stu-id="e4792-102">JordanWignerFermionImpl operation</span></span>

<span data-ttu-id="e4792-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e4792-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e4792-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4792-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4792-105">Reprezentuje Generator dynamiczny jako zestaw bram, które są symulowane i rozszerzanie w JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="e4792-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="e4792-106">Zobacz [dynamiczne modelowanie generatora](../libraries/data-structures#dynamical-generator-modeling) , aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="e4792-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation JordanWignerFermionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e4792-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e4792-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="e4792-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e4792-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e4792-109">Indeks generatora, który ma być reprezentowany jako ewolucja jednostkowa w JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="e4792-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="e4792-110">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e4792-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e4792-111">Mnożnik dotyczący czasu trwania ewolucji przez termin przywoływany w `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e4792-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e4792-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e4792-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e4792-113">Zarejestruj działania podejmowane przez operator zmiany czasu.</span><span class="sxs-lookup"><span data-stu-id="e4792-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e4792-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4792-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


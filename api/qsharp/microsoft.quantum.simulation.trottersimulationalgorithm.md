---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: aa8338ab359441765db72a12f84a3a51e5bee3ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192540"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="5ff38-102">TrotterSimulationAlgorithm, funkcja</span><span class="sxs-lookup"><span data-stu-id="5ff38-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="5ff38-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5ff38-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5ff38-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ff38-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5ff38-105">`SimulationAlgorithm` Funkcja, która korzysta z dekompozycji Trotter – Suzuki, aby przybliżyć czas trwania operacji _(-iHt)_.</span><span class="sxs-lookup"><span data-stu-id="5ff38-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="5ff38-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5ff38-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="5ff38-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5ff38-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5ff38-108">Czas trwania symulowanego czasu rozwoju w jednym kroku Trotter.</span><span class="sxs-lookup"><span data-stu-id="5ff38-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="5ff38-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ff38-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ff38-110">Kolejność integratora Trotter.</span><span class="sxs-lookup"><span data-stu-id="5ff38-110">Order of Trotter integrator.</span></span> <span data-ttu-id="5ff38-111">Ta wartość musi być równa 1 lub parzysta.</span><span class="sxs-lookup"><span data-stu-id="5ff38-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="5ff38-112">Wynik: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="5ff38-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="5ff38-113">`SimulationAlgorithm`Typ.</span><span class="sxs-lookup"><span data-stu-id="5ff38-113">A `SimulationAlgorithm` type.</span></span>
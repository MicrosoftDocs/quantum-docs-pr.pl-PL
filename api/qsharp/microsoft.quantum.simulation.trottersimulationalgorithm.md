---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719865"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="25cd1-102">TrotterSimulationAlgorithm, funkcja</span><span class="sxs-lookup"><span data-stu-id="25cd1-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="25cd1-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="25cd1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="25cd1-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25cd1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25cd1-105">`SimulationAlgorithm` Funkcja, która korzysta z dekompozycji Trotter – Suzuki, aby przybliżyć czas trwania operacji _(-iHt)_ .</span><span class="sxs-lookup"><span data-stu-id="25cd1-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_ .</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="25cd1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="25cd1-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="25cd1-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25cd1-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25cd1-108">Czas trwania symulowanego czasu rozwoju w jednym kroku Trotter.</span><span class="sxs-lookup"><span data-stu-id="25cd1-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="25cd1-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25cd1-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25cd1-110">Kolejność integratora Trotter.</span><span class="sxs-lookup"><span data-stu-id="25cd1-110">Order of Trotter integrator.</span></span> <span data-ttu-id="25cd1-111">Ta wartość musi być równa 1 lub parzysta.</span><span class="sxs-lookup"><span data-stu-id="25cd1-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="25cd1-112">Wynik: [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="25cd1-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="25cd1-113">`SimulationAlgorithm`Typ.</span><span class="sxs-lookup"><span data-stu-id="25cd1-113">A `SimulationAlgorithm` type.</span></span>
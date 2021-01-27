---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: c827dd79af6f4b745adf8903ed2664d9e8255785
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858370"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="605d6-102">TimeDependentTrotterSimulationAlgorithm, funkcja</span><span class="sxs-lookup"><span data-stu-id="605d6-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="605d6-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="605d6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="605d6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="605d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="605d6-105">`TimeDependentSimulationAlgorithm` Funkcja, która używa dekompozycji Trotter – Suzuki do przybliżonego operatora jednostki, który rozwiązuje zależne od czasu równanie Schrodinger.</span><span class="sxs-lookup"><span data-stu-id="605d6-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="605d6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="605d6-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="605d6-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="605d6-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="605d6-108">Czas trwania symulowanego czasu rozwoju w jednym kroku Trotter.</span><span class="sxs-lookup"><span data-stu-id="605d6-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="605d6-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="605d6-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="605d6-110">Kolejność integratora Trotter.</span><span class="sxs-lookup"><span data-stu-id="605d6-110">Order of Trotter integrator.</span></span> <span data-ttu-id="605d6-111">Ta wartość musi być równa 1 lub parzysta.</span><span class="sxs-lookup"><span data-stu-id="605d6-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="605d6-112">Wynik: [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="605d6-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="605d6-113">`TimeDependentSimulationAlgorithm`Typ.</span><span class="sxs-lookup"><span data-stu-id="605d6-113">A `TimeDependentSimulationAlgorithm` type.</span></span>
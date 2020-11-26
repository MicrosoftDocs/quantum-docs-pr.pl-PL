---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: EstimateEnergy, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 0a02a8aad891c45b184b9b18d4e9383236485940
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229498"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="c8167-102">EstimateEnergy, operacja</span><span class="sxs-lookup"><span data-stu-id="c8167-102">EstimateEnergy operation</span></span>

<span data-ttu-id="c8167-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c8167-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c8167-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8167-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8167-105">Wykonuje przygotowywanie stanu przez zastosowanie `statePrepUnitary` na podstawie do automatycznie przydzielonej oceny fazy stanu danych wejściowych w odniesieniu do `qpeUnitary` stanu otrzymanego przy użyciu `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="c8167-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="c8167-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c8167-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="c8167-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8167-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8167-108">Liczba qubits używanych do przeprowadzenia symulacji.</span><span class="sxs-lookup"><span data-stu-id="c8167-108">Number of qubits used to perform simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="c8167-109">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="c8167-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c8167-110">Oprogramowanie Oracle reprezentujące przygotowanie stanu dla początkowego generatora dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="c8167-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="c8167-111">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="c8167-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c8167-112">Firma Oracle reprezentująca operator jednostkowy $U $ reprezentujący ewolucję czasu $ \delta t $ w generatorze dynamicznym ze stanem ziemi $ \ket{\phi} $ i energią stanu ziemi $E = \phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="c8167-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="c8167-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8167-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="c8167-114">Operacja, która wykonuje oszacowanie fazy dla danej operacji jednostkowej.</span><span class="sxs-lookup"><span data-stu-id="c8167-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="c8167-115">Zobacz [szacowanie fazy iteracji](/quantum/libraries/characterization#iterative-phase-estimation) , aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="c8167-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="c8167-116">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8167-116">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c8167-117">Oszacowanie $ \hat{\phi} $ energii stanu ziemi $ \phi $ energii stanu ziemi generatora reprezentowanej przez $U $.</span><span class="sxs-lookup"><span data-stu-id="c8167-117">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the ground state energy of the generator represented by $U$.</span></span>
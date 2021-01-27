---
uid: Microsoft.Quantum.Simulation.EstimateEnergyWithAdiabaticEvolution
title: EstimateEnergyWithAdiabaticEvolution, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergyWithAdiabaticEvolution
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 498955a712db61952d69f28cbbb4715a3efe4c5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858292"
---
# <a name="estimateenergywithadiabaticevolution-operation"></a><span data-ttu-id="937d6-102">EstimateEnergyWithAdiabaticEvolution, operacja</span><span class="sxs-lookup"><span data-stu-id="937d6-102">EstimateEnergyWithAdiabaticEvolution operation</span></span>

<span data-ttu-id="937d6-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="937d6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="937d6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="937d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="937d6-105">Wykonuje przygotowanie stanu przez zastosowanie `statePrepUnitary` na podstawie automatycznie przydzielonego stanu danych wejściowych, a następnie przygotowania stanu adiabatic przy użyciu `adiabaticUnitary` , i wreszcie szacowania fazy, w odniesieniu do `qpeUnitary` stanu uzyskanego przy użyciu `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="937d6-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="937d6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="937d6-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="937d6-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="937d6-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="937d6-108">Liczba qubits użyta do symulacji.</span><span class="sxs-lookup"><span data-stu-id="937d6-108">Number of qubits used for the simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="937d6-109">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="937d6-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="937d6-110">Oprogramowanie Oracle reprezentujące przygotowanie stanu dla początkowego generatora dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="937d6-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="937d6-111">adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="937d6-111">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="937d6-112">Firma Oracle reprezentująca algorytm ewolucji adiabatic, który będzie używany do implementacji odchylenia do końcowego stanu algorytmu.</span><span class="sxs-lookup"><span data-stu-id="937d6-112">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="937d6-113">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="937d6-113">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="937d6-114">Firma Oracle reprezentująca operator jednostkowy $U $ reprezentujący ewolucję czasu $ \delta t $ w generatorze dynamicznym ze stanem ziemi $ \ket{\phi} $ i energią stanu ziemi $E = \phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="937d6-114">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="937d6-115">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="937d6-115">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="937d6-116">Operacja, która wykonuje oszacowanie fazy dla danej operacji jednostkowej.</span><span class="sxs-lookup"><span data-stu-id="937d6-116">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="937d6-117">Zobacz [szacowanie fazy iteracji](/quantum/libraries/characterization#iterative-phase-estimation) , aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="937d6-117">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="937d6-118">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="937d6-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="937d6-119">Oszacowanie $ \hat{\phi} $ energii stanu ziemi $ \phi $ generatora reprezentowanego przez $U $.</span><span class="sxs-lookup"><span data-stu-id="937d6-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>
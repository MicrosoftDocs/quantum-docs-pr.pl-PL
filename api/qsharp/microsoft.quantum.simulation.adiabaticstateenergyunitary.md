---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: AdiabaticStateEnergyUnitary, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: d154f9f1f674dc7cf7af9807922b0897540087b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857956"
---
# <a name="adiabaticstateenergyunitary-operation"></a><span data-ttu-id="179d4-102">AdiabaticStateEnergyUnitary, operacja</span><span class="sxs-lookup"><span data-stu-id="179d4-102">AdiabaticStateEnergyUnitary operation</span></span>

<span data-ttu-id="179d4-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="179d4-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="179d4-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="179d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="179d4-105">Wykonuje przygotowanie stanu `statePrepUnitary` , stosując na stanie dane wejściowe, po którym następuje przygotowanie stanu adiabatic przy użyciu `adiabaticUnitary` , i wreszcie oszacowania fazy w odniesieniu do `qpeUnitary` stanu uzyskanego przy użyciu `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="179d4-105">Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="179d4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="179d4-106">Input</span></span>

### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="179d4-107">statePrepUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="179d4-107">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="179d4-108">Oprogramowanie Oracle reprezentujące przygotowanie stanu dla początkowego generatora dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="179d4-108">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="179d4-109">adiabaticUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="179d4-109">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="179d4-110">Firma Oracle reprezentująca algorytm ewolucji adiabatic, który będzie używany do implementacji odchylenia do końcowego stanu algorytmu.</span><span class="sxs-lookup"><span data-stu-id="179d4-110">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="179d4-111">qpeUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="179d4-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="179d4-112">Firma Oracle reprezentująca operator jednostkowy $U $ reprezentujący ewolucję czasu $ \delta t $ w generatorze dynamicznym ze stanem ziemi $ \ket{\phi} $ i energią stanu ziemi $E = \phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="179d4-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="179d4-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="179d4-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="179d4-114">Operacja, która wykonuje oszacowanie fazy dla danej operacji jednostkowej.</span><span class="sxs-lookup"><span data-stu-id="179d4-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="179d4-115">Zobacz [szacowanie fazy iteracji](/quantum/libraries/characterization#iterative-phase-estimation) , aby uzyskać więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="179d4-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="179d4-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="179d4-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="179d4-117">Rejestr qubits do użycia w celu przeprowadzenia symulacji.</span><span class="sxs-lookup"><span data-stu-id="179d4-117">A register of qubits to be used to perform the simulation.</span></span>



## <a name="output--double"></a><span data-ttu-id="179d4-118">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="179d4-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="179d4-119">Oszacowanie $ \hat{\phi} $ energii stanu ziemi $ \phi $ generatora reprezentowanego przez $U $.</span><span class="sxs-lookup"><span data-stu-id="179d4-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>
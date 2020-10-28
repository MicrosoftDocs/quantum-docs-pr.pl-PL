---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715073"
---
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="71daa-102">DiscretePhaseEstimationIteration, operacja</span><span class="sxs-lookup"><span data-stu-id="71daa-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="71daa-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="71daa-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="71daa-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71daa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71daa-105">Wykonuje pojedynczą iterację algorytmu szacowania fazy iteracyjnej (kontrolowanej w sposób klasyczny) przy użyciu wartości całkowitych dla jednostki firmy Oracle.</span><span class="sxs-lookup"><span data-stu-id="71daa-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="71daa-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="71daa-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="71daa-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="71daa-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="71daa-108">Operacja działająca na liczbie całkowitej i rejestrze, taka jak $U ^ m $, jest zastosowana do danego rejestru, gdzie $U $ jest jednostką, której fazę należy oszacować i gdzie $m $ jest potęgą całkowitą nadaną dla firmy Oracle</span><span class="sxs-lookup"><span data-stu-id="71daa-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="71daa-109">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71daa-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71daa-110">Ile razy zastosować daną jednostkową firmę Oracle.</span><span class="sxs-lookup"><span data-stu-id="71daa-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="71daa-111">teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="71daa-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="71daa-112">Kąt, przez który należy odwrócić fazę qubit formantu przed rozpoczęciem działania na stanie docelowym.</span><span class="sxs-lookup"><span data-stu-id="71daa-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="71daa-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="71daa-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="71daa-114">Rejestr stanu działań podejmowanych przez daną jednostkową firmę Oracle.</span><span class="sxs-lookup"><span data-stu-id="71daa-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="71daa-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="71daa-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="71daa-116">Pomocniczy qubit służący do kontrolowania aplikacji danego programu Oracle.</span><span class="sxs-lookup"><span data-stu-id="71daa-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71daa-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71daa-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


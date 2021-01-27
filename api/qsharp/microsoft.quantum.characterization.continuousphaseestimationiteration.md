---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851904"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="27f27-102">ContinuousPhaseEstimationIteration, operacja</span><span class="sxs-lookup"><span data-stu-id="27f27-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="27f27-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="27f27-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="27f27-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27f27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27f27-105">Wykonuje pojedynczą iterację algorytmu szacowania fazy iteracyjnej (kontrolowanej w trybie klasycznym) przy użyciu dowolnych rzeczywistych uprawnień dla jednostki firmy Oracle.</span><span class="sxs-lookup"><span data-stu-id="27f27-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="27f27-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="27f27-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="27f27-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="27f27-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="27f27-108">Operacja działająca na podwójnym $t $ i rejestrze, takim jak $U ^ t $, jest zastosowana do danego rejestru, gdzie $U $ jest jednostką, której fazę należy oszacować i gdzie $t $ jest potęgą całkowitą nadaną dla firmy Oracle</span><span class="sxs-lookup"><span data-stu-id="27f27-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="27f27-109">czas: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27f27-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="27f27-110">Ile razy zastosować daną jednostkową firmę Oracle.</span><span class="sxs-lookup"><span data-stu-id="27f27-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="27f27-111">teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27f27-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="27f27-112">Kąt, przez który należy odwrócić fazę qubit formantu przed rozpoczęciem działania na stanie docelowym.</span><span class="sxs-lookup"><span data-stu-id="27f27-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="27f27-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="27f27-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="27f27-114">Rejestr stanu działań podejmowanych przez daną jednostkową firmę Oracle.</span><span class="sxs-lookup"><span data-stu-id="27f27-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="27f27-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27f27-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="27f27-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27f27-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


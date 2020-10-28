---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715078"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="ed889-102">ContinuousPhaseEstimationIteration, operacja</span><span class="sxs-lookup"><span data-stu-id="ed889-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="ed889-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="ed889-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="ed889-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed889-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed889-105">Wykonuje pojedynczą iterację algorytmu szacowania fazy iteracyjnej (kontrolowanej w trybie klasycznym) przy użyciu dowolnych rzeczywistych uprawnień dla jednostki firmy Oracle.</span><span class="sxs-lookup"><span data-stu-id="ed889-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ed889-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ed889-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="ed889-107">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="ed889-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="ed889-108">Operacja działająca na podwójnym $t $ i rejestrze, takim jak $U ^ t $, jest zastosowana do danego rejestru, gdzie $U $ jest jednostką, której fazę należy oszacować i gdzie $t $ jest potęgą całkowitą nadaną dla firmy Oracle</span><span class="sxs-lookup"><span data-stu-id="ed889-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="ed889-109">czas: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ed889-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ed889-110">Ile razy zastosować daną jednostkową firmę Oracle.</span><span class="sxs-lookup"><span data-stu-id="ed889-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="ed889-111">teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ed889-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ed889-112">Kąt, przez który należy odwrócić fazę qubit formantu przed rozpoczęciem działania na stanie docelowym.</span><span class="sxs-lookup"><span data-stu-id="ed889-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="ed889-113">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ed889-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ed889-114">Rejestr stanu działań podejmowanych przez daną jednostkową firmę Oracle.</span><span class="sxs-lookup"><span data-stu-id="ed889-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="ed889-115">controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ed889-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="ed889-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ed889-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>


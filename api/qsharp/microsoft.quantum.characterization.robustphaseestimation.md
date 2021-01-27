---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851798"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="89e0f-102">RobustPhaseEstimation, operacja</span><span class="sxs-lookup"><span data-stu-id="89e0f-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="89e0f-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="89e0f-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="89e0f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89e0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89e0f-105">Wykonuje niezawodny nieiteracyjny algorytm szacowania fazy Quantum dla danego oprogramowania Oracle `U` i eigenstate, a następnie dostarcza jeden szacunkowy szacunek fazy z skalowaniem wariancji przy limicie Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="89e0f-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="89e0f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="89e0f-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="89e0f-107">bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89e0f-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89e0f-108">Zapewnia to oszacowanie wartości $ \phi $ z odchylenia standardowego $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ przy użyciu wielu zapytań, takich jak $ \sigma \le 10,7 \pi/\Text{# zapytań} $.</span><span class="sxs-lookup"><span data-stu-id="89e0f-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="89e0f-109">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="89e0f-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="89e0f-110">Operacja implementująca $U ^ m $ dla danej liczby całkowitej $m $.</span><span class="sxs-lookup"><span data-stu-id="89e0f-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="89e0f-111">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="89e0f-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="89e0f-112">Rejestr Quantum, który $U $ działa na.</span><span class="sxs-lookup"><span data-stu-id="89e0f-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="89e0f-113">Jeśli przechowuje eigenstate $ \ket{\phi} $ $U $, a następnie $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ dla $ \phi\in (-\pi, \pi] $ nieznana faza).</span><span class="sxs-lookup"><span data-stu-id="89e0f-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="89e0f-114">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="89e0f-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="89e0f-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="89e0f-115">Remarks</span></span>

<span data-ttu-id="89e0f-116">W limicie dużej liczby zapytań Cramer-Rao dolne granice dla odchylenia standardowego oszacowania $ \phi $ spełniają $ \sigma \ge 2 \pi/\Text{# z zapytań} $.</span><span class="sxs-lookup"><span data-stu-id="89e0f-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="89e0f-117">Odwołania</span><span class="sxs-lookup"><span data-stu-id="89e0f-117">References</span></span>

- <span data-ttu-id="89e0f-118">Niezawodna Kalibracja uniwersalnego Single-Qubit Gate-Set za pośrednictwem solidnej oceny fazy Shelby Kimmel, Guang przerywają Hao Low, powieści Theodore'a dreisera J. Yoder https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="89e0f-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>
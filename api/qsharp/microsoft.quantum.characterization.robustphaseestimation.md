---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: d04ee578c0e6f916e9a4da451075b79e0630c70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714938"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="1a16b-102">RobustPhaseEstimation, operacja</span><span class="sxs-lookup"><span data-stu-id="1a16b-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="1a16b-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="1a16b-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="1a16b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1a16b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1a16b-105">Wykonuje niezawodny nieiteracyjny algorytm szacowania fazy Quantum dla danego oprogramowania Oracle `U` i eigenstate, a następnie dostarcza jeden szacunkowy szacunek fazy z skalowaniem wariancji przy limicie Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="1a16b-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="1a16b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1a16b-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="1a16b-107">bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1a16b-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1a16b-108">Zapewnia to oszacowanie wartości $ \phi $ z odchylenia standardowego $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ przy użyciu wielu zapytań, takich jak $ \sigma \le 10,7 \pi/\Text{# zapytań} $.</span><span class="sxs-lookup"><span data-stu-id="1a16b-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="1a16b-109">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="1a16b-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="1a16b-110">Operacja implementująca $U ^ m $ dla danej liczby całkowitej $m $.</span><span class="sxs-lookup"><span data-stu-id="1a16b-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="1a16b-111">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1a16b-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1a16b-112">Rejestr Quantum, który $U $ działa na.</span><span class="sxs-lookup"><span data-stu-id="1a16b-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="1a16b-113">Jeśli przechowuje eigenstate $ \ket{\phi} $ $U $, a następnie $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ dla $ \phi\in (-\pi, \pi] $ nieznana faza).</span><span class="sxs-lookup"><span data-stu-id="1a16b-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="1a16b-114">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a16b-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="1a16b-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1a16b-115">Remarks</span></span>

<span data-ttu-id="1a16b-116">W limicie dużej liczby zapytań Cramer-Rao dolne granice dla odchylenia standardowego oszacowania $ \phi $ spełniają $ \sigma \ge 2 \pi/\Text{# z zapytań} $.</span><span class="sxs-lookup"><span data-stu-id="1a16b-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="1a16b-117">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="1a16b-117">References</span></span>

- <span data-ttu-id="1a16b-118">Niezawodna Kalibracja uniwersalnego Single-Qubit Gate-Set za pośrednictwem solidnej oceny fazy Shelby Kimmel, Guang przerywają Hao Low, powieści Theodore'a dreisera J. Yoder https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="1a16b-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>
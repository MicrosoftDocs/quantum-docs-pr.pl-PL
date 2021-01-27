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
# <a name="robustphaseestimation-operation"></a>RobustPhaseEstimation, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wykonuje niezawodny nieiteracyjny algorytm szacowania fazy Quantum dla danego oprogramowania Oracle `U` i eigenstate, a następnie dostarcza jeden szacunkowy szacunek fazy z skalowaniem wariancji przy limicie Heisenberg.

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="bitsprecision--int"></a>bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)

Zapewnia to oszacowanie wartości $ \phi $ z odchylenia standardowego $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ przy użyciu wielu zapytań, takich jak $ \sigma \le 10,7 \pi/\Text{# zapytań} $.


### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operacja implementująca $U ^ m $ dla danej liczby całkowitej $m $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr Quantum, który $U $ działa na. Jeśli przechowuje eigenstate $ \ket{\phi} $ $U $, a następnie $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ dla $ \phi\in (-\pi, \pi] $ nieznana faza).



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Uwagi

W limicie dużej liczby zapytań Cramer-Rao dolne granice dla odchylenia standardowego oszacowania $ \phi $ spełniają $ \sigma \ge 2 \pi/\Text{# z zapytań} $.

## <a name="references"></a>Odwołania

- Niezawodna Kalibracja uniwersalnego Single-Qubit Gate-Set za pośrednictwem solidnej oceny fazy Shelby Kimmel, Guang przerywają Hao Low, powieści Theodore'a dreisera J. Yoder https://arxiv.org/abs/1502.02677
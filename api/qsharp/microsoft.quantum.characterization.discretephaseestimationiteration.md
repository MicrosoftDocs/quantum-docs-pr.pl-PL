---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 8ce1e1a2bda6507285f055c87619a8760c891082
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204389"
---
# <a name="discretephaseestimationiteration-operation"></a>DiscretePhaseEstimationIteration, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wykonuje pojedynczą iterację algorytmu szacowania fazy iteracyjnej (kontrolowanej w sposób klasyczny) przy użyciu wartości całkowitych dla jednostki firmy Oracle.

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operacja działająca na liczbie całkowitej i rejestrze, taka jak $U ^ m $, jest zastosowana do danego rejestru, gdzie $U $ jest jednostką, której fazę należy oszacować i gdzie $m $ jest potęgą całkowitą nadaną dla firmy Oracle


### <a name="power--int"></a>potęga: [int](xref:microsoft.quantum.lang-ref.int)

Ile razy zastosować daną jednostkową firmę Oracle.


### <a name="theta--double"></a>teta: [Double](xref:microsoft.quantum.lang-ref.double)

Kąt, przez który należy odwrócić fazę qubit formantu przed rozpoczęciem działania na stanie docelowym.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr stanu działań podejmowanych przez daną jednostkową firmę Oracle.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pomocniczy qubit służący do kontrolowania aplikacji danego programu Oracle.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


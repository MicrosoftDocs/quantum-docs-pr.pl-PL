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
# <a name="continuousphaseestimationiteration-operation"></a>ContinuousPhaseEstimationIteration, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wykonuje pojedynczą iterację algorytmu szacowania fazy iteracyjnej (kontrolowanej w trybie klasycznym) przy użyciu dowolnych rzeczywistych uprawnień dla jednostki firmy Oracle.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Operacja działająca na podwójnym $t $ i rejestrze, takim jak $U ^ t $, jest zastosowana do danego rejestru, gdzie $U $ jest jednostką, której fazę należy oszacować i gdzie $t $ jest potęgą całkowitą nadaną dla firmy Oracle


### <a name="time--double"></a>czas: [Double](xref:microsoft.quantum.lang-ref.double)

Ile razy zastosować daną jednostkową firmę Oracle.


### <a name="theta--double"></a>teta: [Double](xref:microsoft.quantum.lang-ref.double)

Kąt, przez który należy odwrócić fazę qubit formantu przed rozpoczęciem działania na stanie docelowym.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr stanu działań podejmowanych przez daną jednostkową firmę Oracle.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


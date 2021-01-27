---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839661"
---
# <a name="quantumphaseestimation-operation"></a>QuantumPhaseEstimation, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wykonuje algorytm szacowania fazy Quantum dla danego programu Oracle `U` i `targetState` odczytuje fazę do rejestru Quantum big-endian.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operacja implementująca $U ^ m $ dla podaną liczbę całkowitą potęgi m.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr Quantum reprezentujący stan $ \ket{\phi} $ działał na $U $. Jeśli $ \ket{\phi} $ jest eigenstateem $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ dla $ \phi \In [0, 2 \ PI) $ nieznana faza.


### <a name="controlregister--bigendian"></a>controlRegister: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Rejestr operacji big-endian, który może służyć do kontrolowania dostarczonej firmy Oracle i który będzie zawierać reprezentację $ \phi $ po zastosowaniu tej operacji. Założono, że controlRegister rozpoczyna się w stanie początkowym $ \ket{00\cdots 0} $, gdzie długość rejestru wskazuje żądaną precyzję.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 7e524477a4b2bcd8d6767441e278fbf501355e0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714947"
---
# <a name="quantumphaseestimation-operation"></a>QuantumPhaseEstimation, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Package [](https://nuget.org/packages/)


Wykonuje algorytm szacowania fazy Quantum dla danego programu Oracle `U` i `targetState` odczytuje fazę do rejestru Quantum big-endian.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operacja implementująca $U ^ m $ dla podaną liczbę całkowitą potęgi m.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr Quantum reprezentujący stan $ \ket{\phi} $ działał na $U $. Jeśli $ \ket{\phi} $ jest eigenstateem $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ dla $ \phi \In [0, 2 \ PI) $ nieznana faza.


### <a name="controlregister--bigendian"></a>controlRegister: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Rejestr operacji big-endian, który może służyć do kontrolowania dostarczonej firmy Oracle i który będzie zawierać reprezentację $ \phi $ po zastosowaniu tej operacji. Założono, że controlRegister rozpoczyna się w stanie początkowym $ \ket{00\cdots 0} $, gdzie długość rejestru wskazuje żądaną precyzję.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


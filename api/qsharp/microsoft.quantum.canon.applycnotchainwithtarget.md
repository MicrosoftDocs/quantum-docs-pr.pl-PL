---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718365"
---
# <a name="applycnotchainwithtarget-operation"></a>ApplyCNOTChainWithTarget, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Oblicza parzystość tablicy qubits w docelowym qubit.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a>Opis

Jeśli tablica jest początkowo w stanie $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\Text{Target}}} $, stan końcowy jest określony przez $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\Text{Target}}} $.

## <a name="input"></a>Dane wejściowe

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Tablica qubits, w której jest obliczana parzystość.


### <a name="targetqubit--qubit"></a>targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Końcowa qubit, do której parzystość elementu "qubits" to XORed.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

oraz

```qsharp
ApplyCNOTChain(qs);
```
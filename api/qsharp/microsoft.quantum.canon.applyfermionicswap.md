---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718272"
---
# <a name="applyfermionicswap-operation"></a>ApplyFermionicSWAP, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje Fermionic ZAMIANę.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a>Opis

Zasadniczo polega to na wymianie qubits przy zastosowaniu globalnej fazy-1, jeśli oba qubits są 1. Zachowuje symmetrization z orbitals.
Aby uzyskać więcej informacji, zobacz .

Ta operacja jest reprezentowana przez operatora jednostki \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ -1 \\ \\ \end{bmatrix}.
\end{align}

## <a name="input"></a>Dane wejściowe

### <a name="qubit1--qubit"></a>qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pierwszy qubit, który ma zostać zamieniony.


### <a name="qubit2--qubit"></a>qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druga qubit do zamiany.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Dokumentacja

- [*Ryan Babbush, Nathana Wiebe, Jarrod McClean, Kuba McClain, Hartmut Neven, Garnet Kin-Lic kanał* , ArXiv: 1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. wewnętrzna. SWAP](xref:Microsoft.Quantum.Intrinsic.SWAP)
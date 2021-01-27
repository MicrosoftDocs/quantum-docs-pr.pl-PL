---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: e6a88ccf4c01b2f0a7344e3823b2748790cf9650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854334"
---
# <a name="preparequbit-operation"></a>PrepareQubit, operacja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> PrepareQubit jest przestarzała. Użyj <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> zamiast tego.

Przygotowuje qubit w + 1 ( `Zero` ) eigenstate danego operatora Pauli.
Jeśli jest określony operator Identity, qubit jest przygotowana w stanie mieszanym Maximally.

Jeśli qubit był początkowo w stanie $ \ket {0} $, ta operacja przygotowuje qubit w eigenstate $ + $1 danego operatora Pauli lub, dla `PauliI` , w stanie mieszanym Maximally (zobacz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Jeśli qubit było w stanie innym niż $ \ket {0} $, ta operacja stosuje następujące bramy: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ dla `PauliZ` i <xref:microsoft.quantum.preparation.preparesinglequbitidentity> dla `PauliI` .

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="basis--pauli"></a>Podstawa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operator Pauli $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit do przygotowania.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


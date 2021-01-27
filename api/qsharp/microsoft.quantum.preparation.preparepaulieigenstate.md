---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: PreparePauliEigenstate, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: 473bb2fa4429a14f69bcae4573354aad87dc37df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854357"
---
# <a name="preparepaulieigenstate-operation"></a>PreparePauliEigenstate, operacja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Przygotowuje element qubit do pozytywnej eigenstatea danego operatora Pauli.
Jeśli jest określony operator Identity, qubit jest przygotowana w stanie mieszanym Maximally.

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a>Opis

Jeśli qubit był początkowo w stanie $ \ket {0} $, ta operacja przygotowuje qubit w eigenstate $ + $1 danego operatora Pauli lub, dla `PauliI` , w stanie mieszanym Maximally (zobacz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Jeśli qubit było w stanie innym niż $ \ket {0} $, ta operacja stosuje następujące bramy: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ dla `PauliZ` i <xref:microsoft.quantum.preparation.preparesinglequbitidentity> dla `PauliI` .

## <a name="input"></a>Dane wejściowe

### <a name="basis--pauli"></a>Podstawa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operator Pauli $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit do przygotowania.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Przykład

Aby przygotować qubit w stanie $ \ket{+} $:

```qsharp
using (q = Qubit()) {
    PreparePauliEigenstate(PauliX, qubit);
    // ...
}
```
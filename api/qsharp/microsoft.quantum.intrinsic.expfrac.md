---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 8ccea068dd61aaf8c1ba384969adef5644e8401e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198999"
---
# <a name="expfrac-operation"></a>ExpFrac, operacja

Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Stosuje wykładniczą qubit wieloskładnikowego operatora Pauli z argumentem podanym przez ułamek dyadic.

\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align}, gdzie $P _i $ to $i $ th elementu `paulis` , i gdzie $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="paulis--pauli"></a>Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tablica wartości qubit Pauli, wskazujących czynniki iloczynu dwubajtowego na każdym qubit.


### <a name="numerator--int"></a>Licznik: [int](xref:microsoft.quantum.lang-ref.int)

Licznik ($k $) w reprezentacji dyadic frakcji kąta, za pomocą którego ma zostać obrócony rejestr qubit.


### <a name="power--int"></a>potęga: [int](xref:microsoft.quantum.lang-ref.int)

Potęgi dwóch ($n $) określające mianownik kąta, w którym ma zostać obrócony rejestr qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zarejestruj się, aby zastosować dany obrót do.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Operacja miary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 56ddfbe5e63692e477ad75bde6b1b16269ed20c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711452"
---
# <a name="measure-operation"></a>Operacja miary

Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)

Package [](https://nuget.org/packages/)


Wykonuje wspólne pomiary co najmniej jednego qubits w określonych bazach Pauli.

Wynik danych wyjściowych jest podawany przez dystrybucję: \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{\psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}, \end{align}, gdzie $P _i $ to $i $ th elementu `bases` , i gdzie $N = \texttt{length} (\texttt{Bases}) $.
Oznacza to, że pomiar zwraca `Result` $d $ w taki sposób, że eigenvalue zaobserwowanego efektu pomiarowego wynosi $ (-1) ^ d $.

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>Dane wejściowe

### <a name="bases--pauli"></a>bazy: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tablica wartości qubit Pauli, wskazujących czynniki iloczynu dwubajtowego na każdym qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr qubits, który ma być mierzony.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__

`Zero` Jeśli zaobserwowano eigenvalue $ + $1 i `One` Jeśli zaobserwowano eigenvalue $-$1.

## <a name="remarks"></a>Uwagi

Jeśli tablica podstawa i tablica qubit są różne długości, operacja zakończy się niepowodzeniem.
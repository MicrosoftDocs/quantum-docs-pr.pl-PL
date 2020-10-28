---
uid: Microsoft.Quantum.Intrinsic.M
title: Operacja M
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720936"
---
# <a name="m-operation"></a>Operacja M

Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)

Package [](https://nuget.org/packages/)


Wykonuje pomiary jednego qubit w bazie Pauli $Z $.

Wynik wyjściowy jest podawany przez dystrybucję \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>Dane wejściowe

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__

`Zero` Jeśli zaobserwowano eigenvalue $ + $1 i `One` Jeśli zaobserwowano eigenvalue $-$1.

## <a name="remarks"></a>Uwagi

Równoważne:

```qsharp
Measure([PauliZ], [qubit]);
```
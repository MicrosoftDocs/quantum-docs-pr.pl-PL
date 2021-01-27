---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843725"
---
# <a name="applymajorityinplace-operation"></a>ApplyMajorityInPlace, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje qubit większość operacji w miejscu rejestracji qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

Ta operacja oblicza większość funkcji w miejscu na 3 qubits.

Jeśli qubit danych wyjściowych jako $z $ i wejściowy qubits jako $x $ i $y $, operacja wykonuje następujące przekształcenia: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Dane wejściowe

### <a name="output--qubit"></a>wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pierwszy wejściowy qubit. Należy zauważyć, że dane wyjściowe są obliczane w miejscu i przechowywane w tym qubit.


### <a name="input--qubit"></a>dane wejściowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Drugi i trzeci wejściowy qubits.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


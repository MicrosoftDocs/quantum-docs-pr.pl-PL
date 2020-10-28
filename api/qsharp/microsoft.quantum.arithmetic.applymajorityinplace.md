---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721596"
---
# <a name="applymajorityinplace-operation"></a>ApplyMajorityInPlace, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Stosuje qubit większość operacji w miejscu rejestracji qubits.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
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


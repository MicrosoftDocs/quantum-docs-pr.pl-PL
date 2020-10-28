---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721017"
---
# <a name="maj-operation"></a>MAJ, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Powoduje to zastosowanie operacji większości w miejscu do 3 qubits.

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>Opis

W przypadku określenia stanu docelowej qubit jako $ \ket{z} $ i wejścia Stanów danych wejściowych qubits jako $ \ket{x} $ i $ \ket{y} $, ta operacja wykonuje następującą transformację: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Dane wejściowe

### <a name="input0--qubit"></a>input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pierwszy qubit wejściowy.


### <a name="input1--qubit"></a>INPUT1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Drugi wejściowy qubit.


### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, na który zostanie zastosowana większość funkcji.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


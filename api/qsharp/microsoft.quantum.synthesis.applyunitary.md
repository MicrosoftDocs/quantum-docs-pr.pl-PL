---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859219"
---
# <a name="applyunitary-operation"></a>ApplyUnitary, operacja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje bramę zdefiniowaną przez 2 ^ n x 2 ^ n macierz jednostkową.

Kończy się niepowodzeniem, jeśli macierz nie jest jednostką lub ma zły rozmiar.

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="unitary--complex"></a>Jednostka jednostkowa: [złożona](xref:Microsoft.Quantum.Math.Complex)[] []

2 ^ n x 2 ^ n macierz jednostkowa opisującą operację.
Jeśli macierz nie jest jednostką lub nie ma odpowiedniego rozmiaru, zgłasza wyjątek.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubits, do którego zastosowano rejestr operacji o długości n.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


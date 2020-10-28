---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: ApplyReversedOpBECA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 1a11b85e4eca627246d7b9d3b4c10824296e9a77
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721473"
---
# <a name="applyreversedopbeca-operation"></a>ApplyReversedOpBECA, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Stosuje operację, która pobiera dane wejściowe big-endian do rejestru kodowania liczby całkowitej bez znaku przy użyciu formatu little-endian.

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="op--bigendian--unit-ctl--adj"></a>op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik

Operacja, która działa w przypadku rejestracji big-endian.


### <a name="register--littleendian"></a>Zarejestruj się: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Rejestr little-endian do przetworzenia.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
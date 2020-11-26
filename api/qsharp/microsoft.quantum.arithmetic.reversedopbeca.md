---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: ReversedOpBECA, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: da21b09110400ad4ee862f662d45e166a49e7bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222205"
---
# <a name="reversedopbeca-function"></a>ReversedOpBECA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


W przypadku operacji pobierającej dane wejściowe big-endian funkcja zwraca nową operację, która przyjmuje dane wejściowe w postaci little-endian.

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--bigendian--unit--is-adj--ctl"></a>op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Operacja, której dane wejściowe mają zostać cofnięte.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Nowa operacja, która akceptuje dane wejściowe jako rejestr little-endian.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
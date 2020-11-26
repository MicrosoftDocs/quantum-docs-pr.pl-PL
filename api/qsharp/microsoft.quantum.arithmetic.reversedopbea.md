---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 69fd4401e6862a3a6afaa51fb5b8a3592768bb42
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222307"
---
# <a name="reversedopbea-function"></a>ReversedOpBEA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


W przypadku operacji pobierającej dane wejściowe big-endian funkcja zwraca nową operację, która przyjmuje dane wejściowe w postaci little-endian.

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--bigendian--unit--is-adj"></a>op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) BigEndian jest korektą

Operacja, której dane wejściowe mają zostać cofnięte.



## <a name="output--littleendian--unit--is-adj"></a>Wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  jest korektą

Nowa operacja, która akceptuje dane wejściowe jako rejestr little-endian.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)
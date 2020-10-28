---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719697"
---
# <a name="reversedopbea-function"></a>ReversedOpBEA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


W przypadku operacji pobierającej dane wejściowe big-endian funkcja zwraca nową operację, która przyjmuje dane wejściowe w postaci little-endian.

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--bigendian--unit-adj"></a>op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) BigEndian

Operacja, której dane wejściowe mają zostać cofnięte.



## <a name="output--littleendian--unit-adj"></a>Wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) LittleEndian

Nowa operacja, która akceptuje dane wejściowe jako rejestr little-endian.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)
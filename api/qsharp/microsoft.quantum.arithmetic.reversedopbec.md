---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5bafe71b665eda082eafbe06be1308d6b042db2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222273"
---
# <a name="reversedopbec-function"></a>ReversedOpBEC, funkcja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


W przypadku operacji pobierającej dane wejściowe big-endian funkcja zwraca nową operację, która przyjmuje dane wejściowe w postaci little-endian.

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--bigendian--unit--is-ctl"></a>op: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) BigEndian jest listą CTL

Operacja, której dane wejściowe mają zostać cofnięte.



## <a name="output--littleendian--unit--is-ctl"></a>Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to CTL

Nowa operacja, która akceptuje dane wejściowe jako rejestr little-endian.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [Microsoft. Quantum. arytmetyczne. ReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)
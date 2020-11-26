---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 71b6b87a44f541e5379d8de8a3562febbfa49e1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222171"
---
# <a name="reversedoplea-function"></a>ReversedOpLEA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Po wykonaniu operacji pobierającej dane wejściowe o rozmiarze little-endian funkcja zwraca nową operację, która pobiera dane wejściowe big-endian.

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--littleendian--unit--is-adj"></a>op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) LittleEndian jest korektą

Operacja, której dane wejściowe mają zostać cofnięte.



## <a name="output--bigendian--unit--is-adj"></a>Wynik: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  jest korektą

Nowa operacja, która akceptuje dane wejściowe jako rejestr big-endian.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [Microsoft. Quantum. arytmetyczne. ReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [Microsoft. Quantum. arytmetyczne. ReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [Microsoft. Quantum. arytmetyczne. ReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)
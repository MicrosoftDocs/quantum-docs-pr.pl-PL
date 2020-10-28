---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 6ebc4e97cb6d515e99e85922d03ca246b56084ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719649"
---
# <a name="reversedople-function"></a>ReversedOpLE, funkcja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Po wykonaniu operacji pobierającej dane wejściowe o rozmiarze little-endian funkcja zwraca nową operację, która pobiera dane wejściowe big-endian.

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--littleendian--unit"></a>op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Operacja, której dane wejściowe mają zostać cofnięte.



## <a name="output--bigendian--unit"></a>Dane wyjściowe [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) : => [Jednostka](xref:microsoft.quantum.lang-ref.unit) BigEndian 

Nowa operacja, która akceptuje dane wejściowe jako rejestr big-endian.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [Microsoft. Quantum. arytmetyczne. ReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [Microsoft. Quantum. arytmetyczne. ReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [Microsoft. Quantum. arytmetyczne. ReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)
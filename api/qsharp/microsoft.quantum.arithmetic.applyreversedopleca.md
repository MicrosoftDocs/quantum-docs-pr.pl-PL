---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA
title: ApplyReversedOpLECA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLECA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 6e4edd30e33be1a8039b7fd6551470abee26ea27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721425"
---
# <a name="applyreversedopleca-operation"></a>ApplyReversedOpLECA, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Stosuje operację, która powoduje, że dane wejściowe w formacie big-endian są zakodowane w rejestrze, a liczba całkowita bez znaku jest używana.

```qsharp
operation ApplyReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="op--littleendian--unit-ctl--adj"></a>op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik

Operacja, która działa w odniesieniu do rejestru little-endian.


### <a name="register--bigendian"></a>Zarejestruj się: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Rejestr big-endian do przetworzenia.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
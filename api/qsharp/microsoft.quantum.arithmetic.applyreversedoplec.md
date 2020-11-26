---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: ApplyReversedOpLEC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 75b6c0f09c0699b50d9ac1b0274e8074520fc241
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202655"
---
# <a name="applyreversedoplec-operation"></a>ApplyReversedOpLEC, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje operację, która powoduje, że dane wejściowe w formacie big-endian są zakodowane w rejestrze, a liczba całkowita bez znaku jest używana.

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="op--littleendian--unit--is-ctl"></a>op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) LittleEndian jest listą CTL

Operacja, która działa w odniesieniu do rejestru little-endian.


### <a name="register--bigendian"></a>Zarejestruj się: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Rejestr big-endian do przetworzenia.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [Microsoft. Quantum. arytmetyczne. ApplyReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
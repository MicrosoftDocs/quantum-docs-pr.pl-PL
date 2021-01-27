---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843426"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Potwierdza, że najbardziej znaczący qubit rejestru qubit reprezentujący liczbę całkowitą bez znaku jest w określonym stanie.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="value--__invalidresult__"></a>wartość: __nieprawidłowa <Result>__

Wartość najwyższego potwierdzeń bitów.


### <a name="number--littleendian"></a>Liczba: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Liczba całkowita bez znaku, która jest sprawdzana z największą liczbą bitów.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Kontrolowana wersja tej operacji ignoruje kontrolki.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. wewnętrzna. Assert](xref:Microsoft.Quantum.Intrinsic.Assert)
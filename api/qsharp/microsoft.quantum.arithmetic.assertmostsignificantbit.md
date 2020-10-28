---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721380"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Potwierdza, że najbardziej znaczący qubit rejestru qubit reprezentujący liczbę całkowitą bez znaku jest w określonym stanie.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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
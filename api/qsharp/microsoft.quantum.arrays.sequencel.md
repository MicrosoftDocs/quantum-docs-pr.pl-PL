---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Funkcja Sequence
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220267"
---
# <a name="sequencel-function"></a>Funkcja Sequence

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pobierz tablicę liczb całkowitych w danym interwale.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Dane wejściowe

### <a name="from--bigint"></a>z: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Zamknięty indeks początkowy interwału.


### <a name="to--bigint"></a>do: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Łączny indeks końcowy interwału, który nie jest mniejszy niż `from` .



## <a name="output--bigint"></a>Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)[]

Tablica zawierająca sekwencję liczb `from` , `from + 1` ,..., `to` .

## <a name="remarks"></a>Uwagi

Różnica między `from` i `to` musi pasować do `Int` wartości.
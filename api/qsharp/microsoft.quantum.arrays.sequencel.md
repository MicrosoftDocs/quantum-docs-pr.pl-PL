---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Funkcja Sequence
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718881"
---
# <a name="sequencel-function"></a>Funkcja Sequence

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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
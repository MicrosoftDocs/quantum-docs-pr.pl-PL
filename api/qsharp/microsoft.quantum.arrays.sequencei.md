---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220301"
---
# <a name="sequencei-function"></a>SequenceI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pobierz tablicę liczb całkowitych w danym interwale.

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>Dane wejściowe

### <a name="from--int"></a>od: [int](xref:microsoft.quantum.lang-ref.int)

Zamknięty indeks początkowy interwału.


### <a name="to--int"></a>do: [int](xref:microsoft.quantum.lang-ref.int)

Łączny indeks końcowy interwału, który nie jest mniejszy niż `from` .



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]

Tablica zawierająca sekwencję liczb `from` , `from + 1` ,..., `to` .
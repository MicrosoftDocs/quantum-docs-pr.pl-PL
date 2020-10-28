---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718896"
---
# <a name="sequencei-function"></a>SequenceI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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
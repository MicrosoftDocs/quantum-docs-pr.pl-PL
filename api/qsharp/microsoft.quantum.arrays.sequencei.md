---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3cf09e48cce1aeb1aac837465ee3a5e06adf5169
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851008"
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

## <a name="example"></a>Przykład

```qsharp
let arr1 = SequenceI(0, 3); // [0, 1, 2, 3]
let arr2 = SequenceI(23, 29); // [23, 24, 25, 26, 27, 28, 29]
let arr3 = SequenceI(-5, -2); // [-5, -4, -3, -2]

let numbers = SequenceI(0, _); // function to create sequence from 0 to `to`
let naturals = SequenceI(1, _); // function to create sequence from 1 to `to`
```
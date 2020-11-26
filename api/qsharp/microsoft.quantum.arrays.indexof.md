---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221015"
---
# <a name="indexof-function"></a>IndexOf, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca pierwszy indeks pierwszego elementu w tablicy, który spełnia określony predykat. Jeśli taki element nie istnieje, zwraca wartość-1.

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="predicate--t---bool"></a>predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja predykatu działająca na elementach tablicy.


### <a name="arr--t"></a>ARR: t []

Tablica, która ma być przeszukiwana przy użyciu danego predykatu.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Najmniejszy indeks taki, `idx` który `predicate(arr[idx])` ma wartość true, lub-1, jeśli taki element nie istnieje.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C


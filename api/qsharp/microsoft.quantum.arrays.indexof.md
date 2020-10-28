---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719172"
---
# <a name="indexof-function"></a>IndexOf, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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


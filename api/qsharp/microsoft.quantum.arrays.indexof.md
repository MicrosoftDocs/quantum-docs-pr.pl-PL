---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848523"
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



## <a name="example"></a>Przykład

Załóżmy, że `IsEven : Int -> Bool` jest funkcją, która zwraca wartość, `true` Jeśli i tylko wtedy, gdy jej dane wejściowe są parzyste. Następnie można go użyć w `IndexOf` celu znalezienia pierwszego elementu parzystego w tablicy:

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```
---
uid: Microsoft.Quantum.Arrays.Most
title: Większość funkcji
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719001"
---
# <a name="most-function"></a>Większość funkcji

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Tworzy tablicę, która jest równa tablicy wejściowej, z tą różnicą, że ostatni element tablicy jest porzucany.

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="array--t"></a>Tablica: t []

Tablica, której pierwszy do drugiego elementów ma postać tablicy wyjściowej.



## <a name="output--t"></a>Wynik: t []

Tablica zawierająca elementy `array[0..Length(array) - 2]` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ elementów tablicy.
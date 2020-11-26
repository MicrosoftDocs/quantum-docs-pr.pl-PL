---
uid: Microsoft.Quantum.Arrays.Most
title: Większość funkcji
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220607"
---
# <a name="most-function"></a>Większość funkcji

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
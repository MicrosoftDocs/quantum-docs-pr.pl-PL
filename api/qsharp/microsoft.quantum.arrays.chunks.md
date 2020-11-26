---
uid: Microsoft.Quantum.Arrays.Chunks
title: Funkcja fragmentów
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221610"
---
# <a name="chunks-function"></a>Funkcja fragmentów

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dzieli tablicę na wiele części równej długości.

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Dane wejściowe

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)

Długość każdego fragmentu.


### <a name="arr--t"></a>ARR: t []

Tablica, która ma zostać podzielona.



## <a name="output--t"></a>Wynik: t [] []

Tablica zawierająca każdy fragment oryginalnej tablicy.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

Należy zauważyć, że ostatni element danych wyjściowych może być krótszy niż `nElements` Jeśli `Length(arr)` nie jest podzielny przez `nElements` .
---
uid: Microsoft.Quantum.Arrays.Chunks
title: Funkcja fragmentów
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719469"
---
# <a name="chunks-function"></a>Funkcja fragmentów

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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
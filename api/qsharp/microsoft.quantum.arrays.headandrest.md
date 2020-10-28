---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719181"
---
# <a name="headandrest-function"></a>HeadAndRest, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Zwraca krotkę pierwszych i pozostałych elementów tablicy.

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>Dane wejściowe

### <a name="array--a"></a>Tablica: "A []

Tablica z co najmniej jednym elementem.



## <a name="output--aa"></a>Wynik: ("A," A [])

Spójna kolekcja pierwszych i pozostałych elementów tablicy.

## <a name="type-parameters"></a>Parametry typu

### <a name="a"></a>"A

Typ elementów tablicy.
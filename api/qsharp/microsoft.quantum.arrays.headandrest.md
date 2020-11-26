---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221083"
---
# <a name="headandrest-function"></a>HeadAndRest, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
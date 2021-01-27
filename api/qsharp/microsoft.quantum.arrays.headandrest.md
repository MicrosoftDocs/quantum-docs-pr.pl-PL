---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848559"
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
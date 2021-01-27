---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funkcja unspakowane
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845381"
---
# <a name="unzipped-function"></a>Funkcja unspakowane

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana Tablica 2-krotek zwraca spójną kolekcję dwóch tablic, z których każda zawiera elementy krotek tablicy wejściowej.

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>Dane wejściowe

### <a name="arr--tu"></a>ARR: ('T, ' U) []

Tablica zawierająca 2-krotek



## <a name="output--tu"></a>Wynik: (t [], ' U [])

Dwie tablice, pierwszy zawierający wszystkie pierwsze elementy spójnych krotek, drugi, zawierający wszystkie pozostałe elementy spójnych krotek.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ pierwszego elementu w każdej kolekcji
### <a name="u"></a>' U

Typ drugiego elementu w każdej kolekcji

## <a name="example"></a>Przykład

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a>Zobacz też

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)
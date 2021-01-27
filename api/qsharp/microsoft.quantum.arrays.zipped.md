---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funkcja spakowane
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845348"
---
# <a name="zipped-function"></a>Funkcja spakowane

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana dwie tablice zwraca nową tablicę par, w taki sposób, że każda para zawiera element z każdej oryginalnej tablicy.

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Dane wejściowe

### <a name="left--t"></a>Left: t []

Tablica zawierająca wartości dla pierwszego elementu każdej krotki.


### <a name="right--u"></a>prawy: "U []

Tablica zawierająca wartości dla drugiego elementu każdej krotki.



## <a name="output--tu"></a>Wynik: ('T, ' U) []

Tablica zawierająca pary formularzy `(left[idx], right[idx])` dla każdej z nich `idx` . Jeśli dwie tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ elementów tablicy po lewej stronie.
### <a name="u"></a>' U

Typ odpowiednich elementów tablicy.

## <a name="example"></a>Przykład

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>Zobacz też

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. Quantum. Arrays. unspakowane](xref:Microsoft.Quantum.Arrays.Unzipped)
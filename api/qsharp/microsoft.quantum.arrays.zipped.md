---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funkcja spakowane
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718713"
---
# <a name="zipped-function"></a>Funkcja spakowane

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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

## <a name="see-also"></a>Zobacz też

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. Quantum. Arrays. unspakowane](xref:Microsoft.Quantum.Arrays.Unzipped)
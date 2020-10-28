---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718728"
---
# <a name="zip-function"></a>Zip — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


> [!WARNING]
> Plik zip został uznany za przestarzały. Użyj <xref:Microsoft.Quantum.Arrays.Zipped> zamiast tego.

Dana dwie tablice zwraca nową tablicę par, w taki sposób, że każda para zawiera element z każdej oryginalnej tablicy.

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
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

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft. Quantum. Arrays. unspakowane](xref:Microsoft.Quantum.Arrays.Unzipped)
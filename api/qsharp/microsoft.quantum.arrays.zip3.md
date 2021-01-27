---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 —, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845350"
---
# <a name="zip3-function"></a>Zip3 —, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip3 — jest przestarzała. Użyj <xref:Microsoft.Quantum.Arrays.Zipped3> zamiast tego.

Podano trzy tablice, zwraca nową tablicę 3-krotek, tak że każda 3-krotka zawiera element z każdej oryginalnej tablicy.

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>Dane wejściowe

### <a name="first--t1"></a>pierwszy: 'T 1 []

Tablica zawierająca wartości dla pierwszego elementu każdej krotki.


### <a name="second--t2"></a>sekundę: brak 2 []

Tablica zawierająca wartości dla drugiego elementu każdej krotki.


### <a name="third--t3"></a>trzecia: t 3 []

Tablica zawierająca wartości trzeciego elementu każdej krotki.



## <a name="output--t1t2t3"></a>Wynik: (t 1, t 2, t 3) []

Tablica zawierająca 3-krotek formularza `(first[idx], second[idx], third[idx])` dla każdej z nich `idx` . Jeśli trzy tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.

## <a name="type-parameters"></a>Parametry typu

### <a name="t1"></a>Brak 1

Typ pierwszego elementu tablicy.
### <a name="t2"></a>Brak 2

Typ drugiego elementu tablicy.
### <a name="t3"></a>Brak 3

Typ trzeciego elementu tablicy.

## <a name="see-also"></a>Zobacz też

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
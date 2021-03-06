---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 534721e6544a31f6f5d27db0c077e9d8c574aecd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850879"
---
# <a name="zip4-function"></a>Zip4, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip4 jest przestarzała. Użyj <xref:Microsoft.Quantum.Arrays.Zipped4> zamiast tego.

W przypadku czterech tablic funkcja zwraca nową tablicę składającą się z 4 krotek, tak że każda 4-krotka zawiera element z każdej oryginalnej tablicy.

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>Dane wejściowe

### <a name="first--t1"></a>pierwszy: 'T 1 []

Tablica zawierająca wartości dla pierwszego elementu każdej krotki.


### <a name="second--t2"></a>sekundę: brak 2 []

Tablica zawierająca wartości dla drugiego elementu każdej krotki.


### <a name="third--t3"></a>trzecia: t 3 []

Tablica zawierająca wartości trzeciego elementu każdej krotki.


### <a name="fourth--t4"></a>czwarty: t 4 []

Tablica zawierająca wartości dla czwartego elementu każdej krotki.



## <a name="output--t1t2t3t4"></a>Wynik: (t 1, brak 2, t 3, t 4) []

Tablica zawierająca 4-krotek formularza `(first[idx], second[idx], third[idx], fourth[idx])` dla każdej z nich `idx` . Jeśli cztery tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.

## <a name="type-parameters"></a>Parametry typu

### <a name="t1"></a>Brak 1

Typ pierwszego elementu tablicy.
### <a name="t2"></a>Brak 2

Typ drugiego elementu tablicy.
### <a name="t3"></a>Brak 3

Typ trzeciego elementu tablicy.
### <a name="t4"></a>T 4

Typ czwartych elementów tablicy.

## <a name="see-also"></a>Zobacz też

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
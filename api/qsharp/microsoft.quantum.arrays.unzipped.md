---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funkcja unspakowane
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718788"
---
# <a name="unzipped-function"></a>Funkcja unspakowane

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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

## <a name="see-also"></a>Zobacz też

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)
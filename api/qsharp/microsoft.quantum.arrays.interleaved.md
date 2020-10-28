---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funkcja z przeplotem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719145"
---
# <a name="interleaved-function"></a>Funkcja z przeplotem

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Przeplot dwóch tablic o (prawie) tym samym rozmiarze.

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>Opis

Ta funkcja zwraca przeplot dwóch tablic, rozpoczynając od pierwszego elementu z pierwszej tablicy, następnie pierwszy element z drugiej tablicy itd.

Pierwsza Tablica musi mieć taką samą długość jak druga, lub może mieć jeden element.

## <a name="input"></a>Dane wejściowe

### <a name="first--t"></a>pierwszy: t []

Pierwsza tablica, która ma zostać przeplatana.


### <a name="second--t"></a>Second: t []

Druga tablica, która ma zostać przeplatana.



## <a name="output--t"></a>Wynik: t []

Tablica z przeplotem

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ każdego elementu elementów `first` i `second` .
---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funkcja z przeplotem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220964"
---
# <a name="interleaved-function"></a>Funkcja z przeplotem

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funkcja z przeplotem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848112"
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

## <a name="example"></a>Przykład

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```
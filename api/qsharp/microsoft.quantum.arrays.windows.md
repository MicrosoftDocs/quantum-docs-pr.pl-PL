---
uid: Microsoft.Quantum.Arrays.Windows
title: Funkcja systemu Windows
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842191"
---
# <a name="windows-function"></a>Funkcja systemu Windows

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wszystkie kolejne podtablice długości `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Opis

Ta funkcja zwraca wszystkie `n - size + 1` podtablice długości `size` w kolejności, gdzie `n` jest długością `arr` .
Pierwsze podtablice są `arr[0..size - 1], arr[1..size], arr[2..size + 1]` do momentu ostatniej podtablicy `arr[n - size..n - 1]` .

Jeśli `size <= 0` lub `size > n` , zwracana jest pusta tablica.

## <a name="input"></a>Dane wejściowe

### <a name="size--int"></a>rozmiar: [int](xref:microsoft.quantum.lang-ref.int)

Długość podtablic.


### <a name="array--t"></a>Tablica: t []

Tablica elementów.



## <a name="output--t"></a>Wynik: t [] []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ `array` elementów.

## <a name="example"></a>Przykład

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```
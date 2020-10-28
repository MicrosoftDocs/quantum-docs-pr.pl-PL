---
uid: Microsoft.Quantum.Arrays.Windows
title: Funkcja systemu Windows
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718749"
---
# <a name="windows-function"></a>Funkcja systemu Windows

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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
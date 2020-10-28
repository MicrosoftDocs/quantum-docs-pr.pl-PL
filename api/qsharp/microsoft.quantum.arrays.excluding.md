---
uid: Microsoft.Quantum.Arrays.Excluding
title: Wyłączanie funkcji
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719277"
---
# <a name="excluding-function"></a>Wyłączanie funkcji

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Zwraca tablicę zawierającą elementy innej tablicy, z wyłączeniem elementów na danej liście indeksów.

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="remove--int"></a>Usuń: [int](xref:microsoft.quantum.lang-ref.int)[]

Tablica indeksów wskazująca, które elementy powinny być wykluczone z danych wyjściowych.


### <a name="array--t"></a>Tablica: t []

Tablica, z której są pobierane wartości w tablicy wyjściowej.



## <a name="output--t"></a>Wynik: t []

Tablica, `output` taka jak `output[0]` pierwszy element, `array` którego indeks nie pojawia się w, na `remove` przykład to `output[1]` drugi element, i tak dalej.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ elementów tablicy.
---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221355"
---
# <a name="exclude-function"></a>Exclude — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca tablicę zawierającą elementy innej tablicy, z wyłączeniem elementów na danej liście indeksów.

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
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
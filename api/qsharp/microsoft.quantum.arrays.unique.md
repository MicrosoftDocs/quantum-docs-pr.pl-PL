---
uid: Microsoft.Quantum.Arrays.Unique
title: Funkcja unikatowa
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718785"
---
# <a name="unique-function"></a>Funkcja unikatowa

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Zwraca nową tablicę, która nie ma równych elementów sąsiadujących.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Opis

Dana Tablica elementów i funkcja do testowania równości, ta funkcja zwraca nową tablicę, w której jest przechowywana względna kolejność elementów, ale wszystkie sąsiadujące elementy, które są równe są filtrowane do pojedynczego elementu.

## <a name="input"></a>Dane wejściowe

### <a name="equal--tt---bool"></a>równe: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja, która porównuje dwa elementy, które `a` są uważane za równe `b` , `equal(a, b)` Jeśli jest `true` .


### <a name="array--t"></a>Tablica: t []

Tablica, która ma zostać przefiltrowana pod kątem unikatowych elementów.



## <a name="output--t"></a>Wynik: t []

Tablica bez równych elementów sąsiadujących.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ każdego elementu `array` .

## <a name="remarks"></a>Uwagi

Jeśli istnieje wiele elementów, które są równe, ale nie obok siebie, w tablicy wyjściowej będzie wiele wystąpień.  Użyj tej funkcji razem z `Sorted` , aby uzyskać tablicę z ogólnymi unikatowymi elementami.
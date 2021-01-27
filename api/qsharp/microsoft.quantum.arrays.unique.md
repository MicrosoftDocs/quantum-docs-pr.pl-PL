---
uid: Microsoft.Quantum.Arrays.Unique
title: Funkcja unikatowa
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850923"
---
# <a name="unique-function"></a>Funkcja unikatowa

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Przykład

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a>Uwagi

Jeśli istnieje wiele elementów, które są równe, ale nie obok siebie, w tablicy wyjściowej będzie wiele wystąpień.  Użyj tej funkcji razem z `Sorted` , aby uzyskać tablicę z ogólnymi unikatowymi elementami.
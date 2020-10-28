---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operacja ForEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719205"
---
# <a name="foreach-operation"></a>Operacja ForEach

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Dana tablica i operacja, która jest zdefiniowana dla elementów tablicy, zwraca nową tablicę, która składa się z obrazów oryginalnej tablicy w ramach operacji.

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Dane wejściowe

### <a name="action--t--u"></a>Akcja: 'T => ' U 

Operacja z `'T` do do `'U` , która jest stosowana do każdego elementu.


### <a name="array--t"></a>Tablica: t []

Tablica elementów `'T` .



## <a name="output--u"></a>Wynik: "U []

Tablica `'U[]` elementów, które są mapowane przez `action` operację.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ `array` elementów.
### <a name="u"></a>' U

Typ wyniku `action` operacji.

## <a name="remarks"></a>Uwagi

Operacja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i operację, `action : 'T -> 'U` możemy zmapować elementy tablicy i utworzyć nową tablicę typu `'U[]` .
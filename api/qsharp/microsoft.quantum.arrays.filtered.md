---
uid: Microsoft.Quantum.Arrays.Filtered
title: Funkcja filtrowana
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 4c786c69b0896b517f108611e32501867838aeb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719268"
---
# <a name="filtered-function"></a>Funkcja filtrowana

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, zwraca tablicę, która składa się z tych elementów, które spełniają predykat.

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="predicate--t---bool"></a>predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja z `'T` do wartości logicznej, która jest używana do filtrowania elementów.


### <a name="array--t"></a>Tablica: t []

Tablica elementów `'T` .



## <a name="output--t"></a>Wynik: t []

Tablica `'T[]` elementów, które spełniają predykat.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ `array` elementów.

## <a name="remarks"></a>Uwagi

Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i predykat `'T -> Bool` możemy filtrować elementy.
---
uid: Microsoft.Quantum.Arrays.Any
title: Dowolna funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221661"
---
# <a name="any-function"></a>Dowolna funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, sprawdza, czy co najmniej jeden element tablicy spełnia predykat.

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="predicate--t---bool"></a>predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja z `'T` do `Bool` , która jest używana do sprawdzania elementów.


### <a name="array--t"></a>Tablica: t []

Tablica elementów `'T` .



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`Wartość lub funkcji predykatu zastosowana do wszystkich elementów.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ `array` elementów.

## <a name="remarks"></a>Uwagi

Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i funkcję `predicate: 'T -> Bool` możemy utworzyć `Bool` wartość wskazującą, czy jakiś element spełnia `predicate` .
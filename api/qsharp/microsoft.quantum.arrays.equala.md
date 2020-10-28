---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equal — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719289"
---
# <a name="equala-function"></a>Equal — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Dana dwie tablice tego samego typu i predykatu, który jest zdefiniowany dla par elementów tablic, sprawdza, czy tablice są równe.

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="equal--tt---bool"></a>równe: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja z krotki `('T, 'T)` do `Bool` , która służy do sprawdzania, czy dwa elementy tablic są równe.


### <a name="array1--t"></a>tablica1: 'T []

Pierwsza tablica do porównania.


### <a name="array2--t"></a>tablica2: t []

Druga tablica do porównania.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

Wartość `true` Jeśli i tylko wtedy `array1` , gdy i `array2` są równe.
Oznacza to, że jeśli obie tablice mają tę samą długość, a wszystkie elementy są równe zdefiniowane przez `equal` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ elementów każdej tablicy.

## <a name="remarks"></a>Uwagi

Ta funkcja jest definiowana dla typów ogólnych; oznacza to, że za każdym razem, gdy mamy dwie tablice `'T[]` i funkcję `equal: ('T, 'T) -> Bool` , ta funkcja zwraca `Bool` wartość wskazującą, czy tablice są równe.
W przypadku dwóch tablic, które mają być uznawane za równe, muszą one mieć równą długość i elementy w tych samych położeniach w tablicach muszą być równe.
---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equal — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 176e15139a27d375fb047c07fa1ee778dc8cc2ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221372"
---
# <a name="equala-function"></a>Equal — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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
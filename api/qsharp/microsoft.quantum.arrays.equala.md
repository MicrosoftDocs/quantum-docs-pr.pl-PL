---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equal — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848687"
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

## <a name="example"></a>Przykład

Poniższy kod sprawdza, czy różne pary tablic są równe:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a>Uwagi

Ta funkcja jest definiowana dla typów ogólnych; oznacza to, że za każdym razem, gdy mamy dwie tablice `'T[]` i funkcję `equal: ('T, 'T) -> Bool` , ta funkcja zwraca `Bool` wartość wskazującą, czy tablice są równe.
W przypadku dwóch tablic, które mają być uznawane za równe, muszą one mieć równą długość i elementy w tych samych położeniach w tablicach muszą być równe.
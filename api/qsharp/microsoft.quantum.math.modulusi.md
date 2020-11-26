---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227781"
---
# <a name="modulusi-function"></a>ModulusI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Oblicza pozostałą postać kanoniczną `value` modulo `modulus` .

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="value--int"></a>wartość: [int](xref:microsoft.quantum.lang-ref.int)

Wartość, dla której jest obliczana pozostała część


### <a name="modulus--int"></a>Moduł: [int](xref:microsoft.quantum.lang-ref.int)

Moduł, w którym są pożądane pozostałości, musi być dodatni



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita $r $ między 0 i `modulus - 1` taka, która `value - r` jest podzielna przez moduł

## <a name="remarks"></a>Uwagi

Ta funkcja zachowuje się inaczej, jak działa operator `%` w C# i Q # AS w wyniku jest zawsze dodatnią liczbą całkowitą z zakresu od 0 do `modulus - 1` , nawet jeśli wartość jest ujemna.
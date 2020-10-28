---
uid: Microsoft.Quantum.Math.ModulusL
title: Funkcja modułu
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725101"
---
# <a name="modulusl-function"></a>Funkcja modułu

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package [](https://nuget.org/packages/)


Oblicza pozostałą postać kanoniczną `value` modulo `modulus` .

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Dane wejściowe

### <a name="value--bigint"></a>wartość: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Wartość, dla której jest obliczana pozostała część


### <a name="modulus--bigint"></a>Moduł: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Moduł, w którym są pożądane pozostałości, musi być dodatni



## <a name="output--bigint"></a>Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Liczba całkowita $r $ między 0 i `modulus - 1` taka, która `value - r` jest podzielna przez moduł

## <a name="remarks"></a>Uwagi

Ta funkcja zachowuje się inaczej, jak działa operator `%` w C# i Q # AS w wyniku jest zawsze dodatnią liczbą całkowitą z zakresu od 0 do `modulus - 1` , nawet jeśli wartość jest ujemna.
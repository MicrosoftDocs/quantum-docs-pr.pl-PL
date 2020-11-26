---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228495"
---
# <a name="expmodi-function"></a>ExpModI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca liczbę całkowitą podniesioną do danej potęgi w odniesieniu do danego modułu.

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>Opis

Zezwól nam na expBase przez $x $, moc przez $p $ i modulo przez $N $.
Funkcja zwraca $x ^ p \operatorname{mod} N $.

Przyjęto założenie, że $N $, $x $ są pozytywne i potęga nie jest ujemna.

## <a name="input"></a>Dane wejściowe

### <a name="expbase--int"></a>expBase: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>potęga: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>Moduł: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>Uwagi

Czas jest proporcjonalny do liczby bitów w `power` , a nie do `power` samego siebie.
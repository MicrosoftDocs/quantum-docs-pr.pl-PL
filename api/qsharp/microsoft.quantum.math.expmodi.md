---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723365"
---
# <a name="expmodi-function"></a>ExpModI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package [](https://nuget.org/packages/)


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
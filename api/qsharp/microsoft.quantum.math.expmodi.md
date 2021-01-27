---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857032"
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
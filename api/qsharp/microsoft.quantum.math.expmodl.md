---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210753"
---
# <a name="expmodl-function"></a>ExpModL, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca liczbę całkowitą podniesioną do danej potęgi w odniesieniu do danego modułu.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Opis

Zezwól nam na expBase przez $x $, moc przez $p $ i modulo przez $N $.
Funkcja zwraca $x ^ p \operatorname{mod} N $.

Przyjęto założenie, że $N $, $x $ są pozytywne i potęga nie jest ujemna.

## <a name="input"></a>Dane wejściowe

### <a name="expbase--bigint"></a>expBase: [bigint](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>potęga: [bigint](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>Moduł: [bigint](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Uwagi

Czas jest proporcjonalny do liczby bitów w `power` , a nie do `power` samego siebie.
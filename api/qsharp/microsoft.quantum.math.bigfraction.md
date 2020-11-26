---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211087"
---
# <a name="bigfraction-user-defined-type"></a>BigFraction typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje liczbę racjonalną formularza `p/q` . Liczba całkowita `p` jest pierwszym elementem krotki i `q` jest drugim elementem krotki.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="numerator--bigint"></a>Licznik: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Licznik części ułamkowej.
### <a name="denominator--bigint"></a>Mianownik: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Mianownik ułamka/
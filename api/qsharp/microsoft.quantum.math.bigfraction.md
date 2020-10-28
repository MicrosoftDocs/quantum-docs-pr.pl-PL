---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723211"
---
# <a name="bigfraction-user-defined-type"></a>BigFraction typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package [](https://nuget.org/packages/)


Reprezentuje liczbę racjonalną formularza `p/q` . Liczba całkowita `p` jest pierwszym elementem krotki i `q` jest drugim elementem krotki.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="numerator--bigint"></a>Licznik: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Licznik części ułamkowej.
### <a name="denominator--bigint"></a>Mianownik: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Mianownik ułamka/
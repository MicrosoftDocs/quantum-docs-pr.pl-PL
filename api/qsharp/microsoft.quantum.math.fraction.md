---
uid: Microsoft.Quantum.Math.Fraction
title: Ułamek typu zdefiniowanego przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210679"
---
# <a name="fraction-user-defined-type"></a>Ułamek typu zdefiniowanego przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje liczbę racjonalną formularza `p/q` . Liczba całkowita `p` jest pierwszym elementem krotki i `q` jest drugim elementem krotki.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="numerator--int"></a>Licznik: [int](xref:microsoft.quantum.lang-ref.int)

Licznik części ułamkowej.
### <a name="denominator--int"></a>Mianownik: [int](xref:microsoft.quantum.lang-ref.int)

Mianownik ułamka/
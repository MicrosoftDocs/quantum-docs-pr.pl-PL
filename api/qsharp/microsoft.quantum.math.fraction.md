---
uid: Microsoft.Quantum.Math.Fraction
title: Ułamek typu zdefiniowanego przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723659"
---
# <a name="fraction-user-defined-type"></a>Ułamek typu zdefiniowanego przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package [](https://nuget.org/packages/)


Reprezentuje liczbę racjonalną formularza `p/q` . Liczba całkowita `p` jest pierwszym elementem krotki i `q` jest drugim elementem krotki.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="numerator--int"></a>Licznik: [int](xref:microsoft.quantum.lang-ref.int)

Licznik części ułamkowej.
### <a name="denominator--int"></a>Mianownik: [int](xref:microsoft.quantum.lang-ref.int)

Mianownik ułamka/
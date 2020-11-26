---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210985"
---
# <a name="complexpolar-user-defined-type"></a>ComplexPolar typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje liczbę zespoloną w postaci biegunowej.

Reprezentacja biegunowa liczby zespolonej jest $c = r e ^ {i t} $.

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="magnitude--double"></a>Wielkość: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Wartość bezwzględna $r \ge $0 of $c $.
### <a name="argument--double"></a>Argument: [Double](xref:microsoft.quantum.lang-ref.double)

Faza $t \In \mathbb R $ of $c $.
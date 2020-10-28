---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709646"
---
# <a name="complexpolar-user-defined-type"></a>ComplexPolar typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package [](https://nuget.org/packages/)


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
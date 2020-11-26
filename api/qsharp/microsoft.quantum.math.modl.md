---
uid: Microsoft.Quantum.Math.ModL
title: ModL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 0b1ac69cc1474e9cfa6a3489b2b2fdf497e812e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227798"
---
# <a name="modl-function"></a>ModL, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca moduł liczby w odniesieniu do innej liczby.

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a>Dane wejściowe

### <a name="a--bigint"></a>Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Dane wejściowe $a $, których moduł ma zostać zwrócony.


### <a name="b--bigint"></a>b: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Liczba, względem której ma zostać zwrócony moduł $a $.



## <a name="output--bigint"></a>Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Moduł $a \bmod b $.
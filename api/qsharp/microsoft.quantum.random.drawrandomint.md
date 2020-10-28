---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724658"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt, operacja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package [](https://nuget.org/packages/)


Rysuje losową liczbę całkowitą w danym zakresie włącznie.

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="min--int"></a>min: [int](xref:microsoft.quantum.lang-ref.int)

Najmniejsza liczba całkowita do narysowania.


### <a name="max--int"></a>maks.: [int](xref:microsoft.quantum.lang-ref.int)

Największa liczba całkowita do narysowania.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita w zakresie włącznie z `min` do z `max` jednolitym prawdopodobieństwem.

## <a name="remarks"></a>Uwagi

Kończy się niepowodzeniem, jeśli `max <= min` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)
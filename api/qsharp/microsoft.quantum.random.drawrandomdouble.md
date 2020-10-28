---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723986"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble, operacja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package [](https://nuget.org/packages/)


Rysuje losową liczbę rzeczywistą w danym interwale włącznie.

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="min--double"></a>min: [Double](xref:microsoft.quantum.lang-ref.double)

Najmniejsza liczba rzeczywista do narysowania.


### <a name="max--double"></a>Max: [Double](xref:microsoft.quantum.lang-ref.double)

Największa liczba rzeczywista do narysowania.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)

Losowa liczba rzeczywista w interwale łącznym od `min` do wartości `max` z jednolitym prawdopodobieństwem.

## <a name="remarks"></a>Uwagi

Kończy się niepowodzeniem, jeśli `max <= min` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)
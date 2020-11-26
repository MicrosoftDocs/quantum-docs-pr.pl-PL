---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192948"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble, operacja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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
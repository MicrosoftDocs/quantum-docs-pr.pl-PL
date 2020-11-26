---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192914"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt, operacja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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
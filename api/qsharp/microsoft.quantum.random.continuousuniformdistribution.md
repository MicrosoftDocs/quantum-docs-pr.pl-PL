---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193084"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Zwraca jednolitą dystrybucję dla danego interwału włącznie.

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Dane wejściowe

### <a name="min--double"></a>min: [Double](xref:microsoft.quantum.lang-ref.double)

Najmniejsza liczba rzeczywista do narysowania.


### <a name="max--double"></a>Max: [Double](xref:microsoft.quantum.lang-ref.double)

Największa liczba rzeczywista do narysowania.



## <a name="output--continuousdistribution"></a>Wynik: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Rozkład, którego losowo variates są liczbami rzeczywistymi w interwale włącznie z `min` do, `max` z jednolitym prawdopodobieństwem.

## <a name="remarks"></a>Uwagi

Kończy się niepowodzeniem, jeśli `max <= min` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)
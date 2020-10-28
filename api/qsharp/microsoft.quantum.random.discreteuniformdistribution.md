---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720297"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package [](https://nuget.org/packages/)


Zwraca jednolitą dystrybucję dla danego zakresu włącznie.

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Dane wejściowe

### <a name="min--int"></a>min: [int](xref:microsoft.quantum.lang-ref.int)

Najmniejsza liczba całkowita do narysowania.


### <a name="max--int"></a>maks.: [int](xref:microsoft.quantum.lang-ref.int)

Największa liczba całkowita do narysowania.



## <a name="output--discretedistribution"></a>Wynik: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Rozkład, którego losowo variates są liczbami całkowitymi w łącznym zakresie od `min` do `max` z jednolitym prawdopodobieństwem.

## <a name="remarks"></a>Uwagi

Kończy się niepowodzeniem, jeśli `max <= min` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)
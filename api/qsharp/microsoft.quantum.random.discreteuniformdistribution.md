---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853722"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Przykład

Poniższy fragment kodu Q # losowy rzutuje na sześć stron:

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a>Uwagi

Kończy się niepowodzeniem, jeśli `max <= min` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)
---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842313"
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

## <a name="example"></a>Przykład

Poniższy fragment kodu Q # losowo rysuje kąt między $0 $ i $2 \pi $:

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a>Uwagi

Kończy się niepowodzeniem, jeśli `max <= min` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)
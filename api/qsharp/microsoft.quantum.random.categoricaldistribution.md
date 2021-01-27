---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842345"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Zwraca dyskretną dystrybucję kategorii, w której prawdopodobieństwo dla każdej ze skończonej listy podanych wyników jest jawnie określone.

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Dane wejściowe

### <a name="probs--double"></a>PRAWDPD: [Podwójna](xref:microsoft.quantum.lang-ref.double)[]

Prawdopodobieństwa dla każdego wyniku z rozkładu kategorii.
Te prawdopodobieństwa nie mogą być znormalizowane, ale muszą być nieujemne.



## <a name="output--discretedistribution"></a>Wynik: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Indeks `i` z prawdopodobieństwem `probs[i] / sum` , gdzie `sum` jest sumą `probs` podaną przez `Fold(PlusD, 0.0, probs)` .

## <a name="example"></a>Przykład

Poniższy kod Q # będzie wyświetlał 0 z prawdopodobieństwem 30% i 1 z prawdopodobieństwem 70%:

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```
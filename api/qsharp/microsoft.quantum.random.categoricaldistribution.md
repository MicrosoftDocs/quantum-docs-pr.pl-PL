---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210254"
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
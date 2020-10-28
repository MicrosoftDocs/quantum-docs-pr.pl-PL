---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722819"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package [](https://nuget.org/packages/)


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
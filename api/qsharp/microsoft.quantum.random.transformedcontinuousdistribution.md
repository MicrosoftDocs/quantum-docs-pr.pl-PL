---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710943"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package [](https://nuget.org/packages/)


Pod kątem ciągłej dystrybucji program zwraca nową dystrybucję, która przekształca oryginał przez daną funkcję.

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Dane wejściowe

### <a name="transform--double---double"></a>transformacja: [podwójne](xref:microsoft.quantum.lang-ref.double) -> [podwójne](xref:microsoft.quantum.lang-ref.double)

Funkcja, która przekształca variates oryginalnej dystrybucji do przekształconej dystrybucji.


### <a name="distribution--continuousdistribution"></a>dystrybucja: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Oryginalna dystrybucja, która ma zostać przekształcona.



## <a name="output--continuousdistribution"></a>Wynik: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Nowa dystrybucja odnosząca się do `distribution` transformacji podawanej przez `transform` .
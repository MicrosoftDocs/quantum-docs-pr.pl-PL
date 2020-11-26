---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226268"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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
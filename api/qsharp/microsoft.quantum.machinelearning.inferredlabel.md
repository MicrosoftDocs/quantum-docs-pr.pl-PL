---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211784"
---
# <a name="inferredlabel-function"></a>InferredLabel, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Podajesz prawdopodobieństwo klasyfikacji i bias zwraca etykietę wywnioskowaną z tego prawdopodobieństwa.

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="bias--double"></a>różnica: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Różnica między dwiema klasami, zazwyczaj wynikiem szkolenia klasyfikatora.


### <a name="probability--double"></a>prawdopodobieństwo: [Double](xref:microsoft.quantum.lang-ref.double)

Klasyfikacja prawdopodobieństwa dla konkretnej próbki zwykle wynika z oszacowania jej częstotliwości klasyfikacji.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Etykieta wywnioskowana z danego prawdopodobieństwa klasyfikacji.
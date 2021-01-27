---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848405"
---
# <a name="inferredlabels-function"></a>InferredLabels, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dana tablica prawdopodobieństwa klasyfikacji i bias zwraca etykietę wywnioskowaną z każdego prawdopodobieństwa.

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>Dane wejściowe

### <a name="bias--double"></a>różnica: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Różnica między dwiema klasami, zazwyczaj wynikiem szkolenia klasyfikatora.


### <a name="probabilities--double"></a>prawdopodobieństwa: [Podwójna](xref:microsoft.quantum.lang-ref.double)[]

Tablica prawdopodobieństwa klasyfikacji dla zestawu próbek zazwyczaj wynika z oszacowania częstotliwości klasyfikacji.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]

Etykieta wywnioskowana z każdego prawdopodobieństwa klasyfikacji.
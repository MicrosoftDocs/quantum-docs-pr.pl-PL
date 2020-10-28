---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722483"
---
# <a name="inferredlabels-function"></a>InferredLabels, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


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
---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722516"
---
# <a name="inferredlabel-function"></a>InferredLabel, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


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
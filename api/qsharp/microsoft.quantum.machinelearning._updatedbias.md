---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: Funkcja _UpdatedBias
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 2704d08e4c1ce868e1fd9065c3cab0285d431094
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720564"
---
# <a name="_updatedbias-function"></a>Funkcja _UpdatedBias

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Zwraca wartość bias, która prowadzi do niewystarczającego wyniku niewystarczającej klasyfikacji.

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="labeledprobabilities--doubleint"></a>labeledProbabilities: ([Double](xref:microsoft.quantum.lang-ref.double),[int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="bias--double"></a>różnica: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)




### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)


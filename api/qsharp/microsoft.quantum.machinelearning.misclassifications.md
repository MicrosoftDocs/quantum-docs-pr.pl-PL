---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Niesklasyfikowane funkcje
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211682"
---
# <a name="misclassifications-function"></a>Niesklasyfikowane funkcje

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Po otrzymaniu zestawu etykiet wywnioskowanych i zestawu prawidłowych etykiet zwraca indeksy, dla których każdy zestaw etykiet różni się.

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>Dane wejściowe

### <a name="inferredlabels--int"></a>inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]

Etykiety wywnioskowane dla danego szkolenia lub zestawu walidacji.


### <a name="actuallabels--int"></a>actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]

Prawdziwe etykiety dla danego szkolenia lub zestawu walidacji.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]

Tablica indeksów `idx` , takich jak `inferredLabels[idx] != actualLabels[idx]` .
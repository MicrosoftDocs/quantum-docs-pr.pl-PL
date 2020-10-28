---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Niesklasyfikowane funkcje
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723580"
---
# <a name="misclassifications-function"></a>Niesklasyfikowane funkcje

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


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
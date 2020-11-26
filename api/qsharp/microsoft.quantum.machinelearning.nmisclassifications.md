---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196314"
---
# <a name="nmisclassifications-function"></a>NMisclassifications, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


W przypadku zestawu etykiet wywnioskowanych i zestawu prawidłowych etykiet zwraca liczbę indeksów, w których każdy zestaw etykiet różni się.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="proposed--int"></a>proponowane: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>rzeczywista: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Liczba indeksów `idx` , takich jak `inferredLabels[idx] != actualLabels[idx]` .
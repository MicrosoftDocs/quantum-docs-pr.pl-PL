---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709739"
---
# <a name="nmisclassifications-function"></a>NMisclassifications, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


W przypadku zestawu etykiet wywnioskowanych i zestawu prawidłowych etykiet zwraca liczbę indeksów, w których każdy zestaw etykiet różni się.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="proposed--int"></a>proponowane: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>rzeczywista: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Liczba indeksów `idx` , takich jak `inferredLabels[idx] != actualLabels[idx]` .
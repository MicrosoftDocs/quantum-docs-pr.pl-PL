---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: adc7042d6108c7ec72d13340633824d3eaf5e18e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853915"
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

## <a name="example"></a>Przykład

```qsharp
let nMisclassifications = NMisclassifications([1, 1, 0, 0], [0, 1, 1, 0]);
Message($"{nMisclassifications}"); // Will print 2.
```
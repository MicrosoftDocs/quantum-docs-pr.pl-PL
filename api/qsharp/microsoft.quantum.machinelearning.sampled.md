---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Próbkowanie funkcji
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211631"
---
# <a name="sampled-function"></a>Próbkowanie funkcji

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Próbkuje daną tablicę przy użyciu danego harmonogramu.

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="schedule--samplingschedule"></a>Harmonogram: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Harmonogram do użycia w wartościach próbkowania.


### <a name="values--t"></a>wartości: t []

Tablica wartości do próbkowania.



## <a name="output--t"></a>Wynik: t []

Tablica elementów z wartości, zgodnie z podanym harmonogramem.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C


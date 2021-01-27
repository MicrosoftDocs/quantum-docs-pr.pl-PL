---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Próbkowanie funkcji
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854948"
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


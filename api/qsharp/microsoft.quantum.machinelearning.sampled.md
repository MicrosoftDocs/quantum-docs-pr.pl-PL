---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Próbkowanie funkcji
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722427"
---
# <a name="sampled-function"></a>Próbkowanie funkcji

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


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


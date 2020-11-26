---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191452"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases, funkcja

Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Oblicza częściowe fazy odbicia dla wzmocnienia amplitudy stałej.

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Dane wejściowe

### <a name="nqueries--int"></a>nQueries: [int](xref:microsoft.quantum.lang-ref.int)

Liczba zapytań do przygotowania stanu. Musi być nieparzystą liczbą całkowitą.


### <a name="successmin--double"></a>successMin: [Double](xref:microsoft.quantum.lang-ref.double)

Minimalne prawdopodobieństwo sukcesu.



## <a name="output--reflectionphases"></a>Wynik: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Tablica faz, które mogą być używane w implementacji algorytmu Quantum w ramach amplitudy stałych punktów.

## <a name="references"></a>Odwołania

Używamy faz w "wzmocnienia amplitudy stałej" z optymalną liczbą zapytań "

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Zobacz również "Metodologia złożonych bram Quantum"
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) dla faz w `RotationPhases` formacie.
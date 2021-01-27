---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845858"
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
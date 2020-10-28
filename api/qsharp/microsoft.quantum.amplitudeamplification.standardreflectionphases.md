---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721732"
---
# <a name="standardreflectionphases-function"></a>StandardReflectionPhases, funkcja

Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package [](https://nuget.org/packages/)


Oblicza częściowe fazy odbicia w przypadku wzmocnienia amplitudy standardowej.

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Dane wejściowe

### <a name="niterations--int"></a>nIterations: [int](xref:microsoft.quantum.lang-ref.int)

Liczba iteracji wzmocnienia amplitudy, dla których mają zostać wygenerowane częściowe fazy odbicia.



## <a name="output--reflectionphases"></a>Wynik: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Operacja implementująca fazy określone jako częściowe odbicie

## <a name="remarks"></a>Uwagi

Wszystkie fazy to $ \pi $, z wyjątkiem pierwszego odbicia stanu początkowego i ostatniego odbicia w stanie docelowym, które są $0 $.
---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721755"
---
# <a name="rotationphasesasreflectionphases-function"></a>RotationPhasesAsReflectionPhases, funkcja

Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package [](https://nuget.org/packages/)


Konwertuje fazy określone jako rotacje pojedynczej qubit na fazy określone jako częściowe odbicia.

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Dane wejściowe

### <a name="rotphases--rotationphases"></a>rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)

Tablica rotacji z pojedynczą qubitą do przekonwertowania na częściowe odbicia.



## <a name="output--reflectionphases"></a>Wynik: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Operacja implementująca fazy określone jako częściowe odbicia.

## <a name="references"></a>Dokumentacja

Używamy Konwencji w

- [ *G.H. niskie, I. L. Czuang*](https://arxiv.org/abs/1707.05391) do odnoszące się do faz operatora odbicia z jedną qubitą.
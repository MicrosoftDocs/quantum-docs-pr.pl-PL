---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721769"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package [](https://nuget.org/packages/)


Fazy dla sekwencji rotacji z pojedynczą qubitą w wzmocnienie amplitudy.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Uwagi

Pierwszy parametr jest tablicą faz dla odbić, wyrażoną jako iloczyn pojedynczej rotacji qubit.
[ G.H. Niski, I. L. Czuang, https://arxiv.org/abs/1707.05391 ].
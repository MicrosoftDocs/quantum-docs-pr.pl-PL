---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191367"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fazy dla sekwencji rotacji z pojedynczą qubitą w wzmocnienie amplitudy.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Uwagi

Pierwszy parametr jest tablicą faz dla odbić, wyrażoną jako iloczyn pojedynczej rotacji qubit.
[ G.H. Niski, I. L. Czuang, https://arxiv.org/abs/1707.05391 ].
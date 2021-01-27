---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843966"
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
---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191350"
---
# <a name="reflectionphases-user-defined-type"></a>ReflectionPhases typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fazy dla sekwencji częściowego odbicia w wzmocnienia amplitudy.

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="aboutstart--double"></a>AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]

Tablica faz odbicia informacji o stanie początkowym.
### <a name="abouttarget--double"></a>AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]

Tablica faz dla odbicia stanu docelowego.

## <a name="remarks"></a>Uwagi

Obie tablice muszą mieć równej długości. Należy zauważyć, że w wielu przypadkach Pierwsza faza dotycząca stanu początkowego i ostatniej fazy dotyczącej stanu docelowego wprowadza globalną fazę zmiany i może być ustawiona na $0 $.
---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721816"
---
# <a name="reflectionphases-user-defined-type"></a>ReflectionPhases typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package [](https://nuget.org/packages/)


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
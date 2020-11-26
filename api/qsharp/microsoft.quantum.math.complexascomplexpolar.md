---
uid: Microsoft.Quantum.Math.ComplexAsComplexPolar
title: ComplexAsComplexPolar, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexAsComplexPolar
qsharp.summary: Converts a complex number of type `Complex` to a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5155583291e69a78df66f3b77d758fc1708d9146
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195634"
---
# <a name="complexascomplexpolar-function"></a>ComplexAsComplexPolar, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konwertuje liczbę zespoloną typu `Complex` na liczbę zespoloną typu `ComplexPolar` .

```qsharp
function ComplexAsComplexPolar (input : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a>Dane wejściowe

### <a name="input--complex"></a>dane wejściowe: [złożone](xref:Microsoft.Quantum.Math.Complex)

Liczba złożona $c = x + i y $.



## <a name="output--complexpolar"></a>Wynik: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Liczba złożona $c = r e ^ {i t} $.
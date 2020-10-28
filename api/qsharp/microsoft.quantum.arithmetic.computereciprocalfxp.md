---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721248"
---
# <a name="computereciprocalfxp-operation"></a>ComputeReciprocalFxP, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Oblicza wartość $1/x $ dla ustalonej liczby $x $.

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="x--fixedpoint"></a>x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Liczba stałych punktów do odwrócenia.


### <a name="result--fixedpoint"></a>wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Liczba stałych punktów, która będzie przechowywać wynik. Musi być zainicjowany do $ \ket{0.0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


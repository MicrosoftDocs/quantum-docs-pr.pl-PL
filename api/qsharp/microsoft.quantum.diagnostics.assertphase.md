---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712950"
---
# <a name="assertphase-operation"></a>AssertPhase, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package [](https://nuget.org/packages/)


Potwierdza, że faza równego stanu nadpozycji ma oczekiwaną wartość.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Opis

Ta operacja potwierdza, że faza $ \phi $ stanu Quantum, która może być wyrażona jako $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ KET {0} + e ^ {-i\phi} \ KET {1} ) $ dla niektórych dowolnych rzeczywistych $t $ ma oczekiwaną wartość.

## <a name="input"></a>Dane wejściowe

### <a name="expected--double"></a>Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)

Oczekiwana wartość $ \phi \In (-\pi, \pi] $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit przechowujący oczekiwany stan.


### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Absolutna tolerancja różnicy między wartością rzeczywistą i oczekiwaną.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830077"
---
# <a name="assertphase-operation"></a>AssertPhase, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Przykład

Następujące potwierdzenie powiodło się: `qubit` znajduje się w stanie $ \ket{\psi} = e ^ {i 0,5} \ sqrt {1/2} \ KET {0} + e ^ {i 0,5} \ sqrt {1/2} \ KET {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` jest w stanie $ \ket{\psi} = e ^ {i 0,5} \ sqrt {1/2} \ KET {0} + e ^ {-i 0,5} \ sqrt {1/2} \ KET {1} $;

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` jest w stanie $ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ KET {0} + e ^ {i 0,2} \ sqrt {1/2} \ KET {1} $;

- `AssertPhase(-1.2,qubit,10e-10);`
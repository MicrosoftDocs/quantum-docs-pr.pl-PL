---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 4ff0abe67a6d18204e417a45f8d8f1d092d02b88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200802"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation, operacja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Obraca pojedynczy qubit o π/4 o oś Y.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a>Opis

Wykonuje rotację π/4 `Y` .

Obrót jest wykonywany przez zużywanie stanu Magic; oznacza to, że kopia stanu $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket {8} {1} .
\end{align} $ $

## <a name="input"></a>Dane wejściowe

### <a name="data--qubit"></a>dane: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, który ma zostać obrócony o $Y $ przez $ \pi/$4.


### <a name="magic--qubit"></a>Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit początkowo w stanie Magic. Następująca aplikacja `magic` jest zwracana do stanu $ \ket {0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```qsharp
Ry(PI() / 4.0, data);
```

oraz

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

Ta operacja obsługuje `Adjoint` Funktor, w którym wykorzystano ten sam stan Magic, ale efektem na qubit danych jest wartość $-\ Pi/4 $ $Y $-Rotation.
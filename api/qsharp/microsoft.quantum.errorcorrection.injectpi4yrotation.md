---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712320"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation, operacja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package [](https://nuget.org/packages/)


Obraca pojedynczy qubit o π/4 o oś Y.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
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
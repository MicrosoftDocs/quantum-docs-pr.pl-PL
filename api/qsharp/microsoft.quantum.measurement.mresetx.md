---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725003"
---
# <a name="mresetx-operation"></a>MResetX, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Package [](https://nuget.org/packages/)


Mierzy pojedynczy qubit w bazie X, a następnie resetuje go do ustalonego stanu początkowego po pomiar.

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>Opis

Wykonuje pomiar pojedynczej qubit na podstawie $X $ i zapewnia, że qubit jest zwracany do $ \ket {0} $ po pomiarze.

## <a name="input"></a>Dane wejściowe

### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pojedyncze qubit, które mają być mierzone.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__

Wynik pomiaru `target` w Pauli $X $.
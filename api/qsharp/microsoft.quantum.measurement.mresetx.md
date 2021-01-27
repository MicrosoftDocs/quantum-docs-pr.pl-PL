---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853757"
---
# <a name="mresetx-operation"></a>MResetX, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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
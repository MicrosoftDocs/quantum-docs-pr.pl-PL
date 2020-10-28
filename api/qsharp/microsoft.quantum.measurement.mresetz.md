---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711055"
---
# <a name="mresetz-operation"></a>MResetZ, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Package [](https://nuget.org/packages/)


Mierzy pojedynczy qubit w bazie Z i resetuje go do ustalonego stanu początkowego po pomiar.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Opis

Wykonuje pomiar pojedynczej qubit na podstawie $Z $ i zapewnia, że qubit jest zwracany do $ \ket {0} $ po pomiarze.

## <a name="input"></a>Dane wejściowe

### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pojedyncze qubit, które mają być mierzone.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__

Wynik pomiaru `target` w Pauli $Z $.
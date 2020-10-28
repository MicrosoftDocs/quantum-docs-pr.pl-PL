---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725008"
---
# <a name="mresety-operation"></a>MResetY, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Package [](https://nuget.org/packages/)


Mierzy pojedynczy qubit w bazie Y i resetuje go do ustalonego stanu początkowego po pomiar.

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>Opis

Wykonuje pomiar pojedynczej qubit na podstawie $Y $ i zapewnia, że qubit jest zwracany do $ \ket {0} $ po pomiarze.

## <a name="input"></a>Dane wejściowe

### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pojedyncze qubit, które mają być mierzone.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__

Wynik pomiaru `target` w Pauli $Y $.
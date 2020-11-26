---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227033"
---
# <a name="mresety-operation"></a>MResetY, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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
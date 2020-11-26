---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227084"
---
# <a name="measureallz-operation"></a>MeasureAllZ, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wspólnie mierzy rejestr qubits na bazie Pauli Z.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Opis

Mierzy rejestr qubits w $Z \otimes Z \otimes \cdots \otimes Z $, reprezentujący parzystość całego rejestru.

## <a name="input"></a>Dane wejściowe

### <a name="register--qubit"></a>Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr, który ma być mierzony.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__

Wynik pomiaru $Z \otimes Z \otimes \cdots \otimes Z $.
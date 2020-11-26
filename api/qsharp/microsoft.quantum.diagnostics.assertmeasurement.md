---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 3fbe000202abbd8a206b0c83dfa35f4546ea91cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202451"
---
# <a name="assertmeasurement-operation"></a>AssertMeasurement, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Potwierdzenia, które mierzą podaną qubits w danej Pauli, będą mieć zawsze określony wynik.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="bases--pauli"></a>bazy: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Efekt pomiaru, który pozwala uzyskać prawdopodobieństwo wystąpienia wartości, wyrażony jako operator qubit Pauli.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr, na którym należy wykonać potwierdzenie.


### <a name="result--__invalidresult__"></a>wynik: __nieprawidłowe <Result>__

Oczekiwany wynik `Measure(bases, qubits)` .


### <a name="msg--string"></a>msg: [ciąg](xref:microsoft.quantum.lang-ref.string)

Komunikat, który ma być raportowany, jeśli potwierdzenie nie powiedzie się.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Należy zauważyć, że sąsiadujące i kontrolowane wersje tej operacji nie będą sprawdzać warunku.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Diagnostics. AssertMeasurementProbability](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)
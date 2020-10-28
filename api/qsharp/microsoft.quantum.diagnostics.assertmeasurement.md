---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713034"
---
# <a name="assertmeasurement-operation"></a>AssertMeasurement, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package [](https://nuget.org/packages/)


Potwierdzenia, które mierzą podaną qubits w danej Pauli, będą mieć zawsze określony wynik.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
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
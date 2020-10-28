---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712978"
---
# <a name="assertmeasurementprobability-operation"></a>AssertMeasurementProbability, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package [](https://nuget.org/packages/)


Potwierdzenia, które mierzą podaną qubits w danej Pauli, będą miały wynik z określonym prawdopodobieństwem, w granicach tolerancji.

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="bases--pauli"></a>bazy: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Efekt pomiaru, który pozwala uzyskać prawdopodobieństwo wystąpienia wartości, wyrażony jako operator qubit Pauli.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr, na którym należy wykonać potwierdzenie.


### <a name="result--__invalidresult__"></a>wynik: __nieprawidłowe <Result>__

Oczekiwany wynik `Measure(bases, qubits)` .


### <a name="prob--double"></a>funkcja PRAWDPD: [Podwójna](xref:microsoft.quantum.lang-ref.double)

Prawdopodobieństwo, z którym jest oczekiwany dany wynik.


### <a name="msg--string"></a>msg: [ciąg](xref:microsoft.quantum.lang-ref.string)

Komunikat, który ma być raportowany, jeśli potwierdzenie nie powiedzie się.


### <a name="tol--double"></a>stosowanie: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Należy zauważyć, że sąsiadujące i kontrolowane wersje tej operacji nie będą sprawdzać warunku.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Diagnostics. AssertMeasurement](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)
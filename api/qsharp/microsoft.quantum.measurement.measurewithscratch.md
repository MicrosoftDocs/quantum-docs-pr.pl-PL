---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227067"
---
# <a name="measurewithscratch-operation"></a>MeasureWithScratch, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mierzy dany operator Pauli za pomocą jawnego qubitu do przeprowadzenia pomiaru.

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>Dane wejściowe

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Operator qubit Pauli określony jako tablica operatorów z pojedynczą qubit Pauli.


### <a name="target--qubit"></a>target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit rejestr do zmierzenia.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__

Wynik pomiaru danego operatora Pauli w `target` rejestrze.
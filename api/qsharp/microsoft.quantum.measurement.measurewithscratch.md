---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720324"
---
# <a name="measurewithscratch-operation"></a>MeasureWithScratch, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Package [](https://nuget.org/packages/)


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
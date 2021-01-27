---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853766"
---
# <a name="measurepaulis-operation"></a>MeasurePaulis, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana tablica operatorów wieloqubitowych Pauli, miara każdego przy użyciu określonego gadżetu pomiaru, a następnie zwraca tablicę wyników.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Dane wejściowe

### <a name="paulis--pauli"></a>Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tablica operatorów qubit Pauli, które mają być mierzone.


### <a name="target--qubit"></a>target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zarejestruj się, w którym mają zostać dopasowane określone operatory.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __nieprawidłowy <Result>__ 

Operacja, która wykonuje pomiary danego operatora qubit.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__[]

Tablica wyników uzyskanych od mierzenia każdego elementu `paulis` w `target` .
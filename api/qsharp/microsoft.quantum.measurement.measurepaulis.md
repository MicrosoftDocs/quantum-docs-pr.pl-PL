---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 4faaf78f24fa28ae5e4f701b80d9297c910b975e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194223"
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
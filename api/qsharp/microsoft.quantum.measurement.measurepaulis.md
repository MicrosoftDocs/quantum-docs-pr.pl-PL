---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720345"
---
# <a name="measurepaulis-operation"></a>MeasurePaulis, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Package [](https://nuget.org/packages/)


Dana tablica operatorów wieloqubitowych Pauli, miara każdego przy użyciu określonego gadżetu pomiaru, a następnie zwraca tablicę wyników.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Dane wejściowe

### <a name="paulis--pauli"></a>Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tablica operatorów qubit Pauli, które mają być mierzone.


### <a name="target--qubit"></a>target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zarejestruj się, w którym mają zostać dopasowane określone operatory.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __nieprawidłowy <Result>__ 

Operacja, która wykonuje pomiary danego operatora qubit.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__ []

Tablica wyników uzyskanych od mierzenia każdego elementu `paulis` w `target` .
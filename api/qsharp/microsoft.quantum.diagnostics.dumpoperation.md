---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202060"
---
# <a name="dumpoperation-operation"></a>DumpOperation, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Po wykonaniu operacji program wyświetla diagnostykę operacji, które są dostępne dla bieżącego celu wykonania.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits, w których dana operacja działa.


### <a name="op--qubit--unit--is-adj"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Operacja, która ma zostać zdiagnozowana.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Wywołanie tej operacji nie ma zauważalnego efektu z poziomu Q #. Dokładna Diagnostyka, która jest wyświetlana, jeśli istnieje, zależy od bieżącego celu wykonywania i środowiska edytora.
Na przykład, gdy jest używany w symulatorze Quantum o pełnym stanie, zostanie wyświetlona macierz jednostkowa użyta do reprezentowania `op` .

Należy pamiętać, że w przypadku korzystania z symulatorów, które dopuszczają niejednoznaczność globalną fazy (np. symulatora pełnego stanu), zwrócone reprezentacje mogą się różnić w zależności od globalnej fazy.

Podobnie porządkowanie macierzy wierszy i kolumn może różnić się w zależności od konwencji używanych przez każdy symulator obsługujący tę operację.
---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: ApplyToPartition, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: a0dc3453e7501816132569869e858418d5f3f4e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850536"
---
# <a name="applytopartition-operation"></a>ApplyToPartition, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje parę operacji do danej partycji rejestracji w dwóch częściach.

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="op--qubitqubit--unit"></a>op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Para operacji do zastosowania do danej partycji.


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits z elementu docelowego, które mają zostać umieszczone w pierwszej części partycji.
Pozostałe qubits stanowią drugą część partycji.


### <a name="target--qubit"></a>target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr qubits, które są partycjonowane i obsługiwane przez daną dwie operacje.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyToPartitionA](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [Microsoft. Quantum. Canon. ApplyToPartitionC](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [Microsoft. Quantum. Canon. ApplyToPartitionCA](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)
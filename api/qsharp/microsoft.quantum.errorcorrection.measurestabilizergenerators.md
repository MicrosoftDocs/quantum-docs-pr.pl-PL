---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: 6c048c17df21d1026dc671f30d72a13ed8d8b7f5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200632"
---
# <a name="measurestabilizergenerators-operation"></a>MeasureStabilizerGenerators, operacja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mierzy dany zestaw generatorów grupy stabilizatorów.

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>Dane wejściowe

### <a name="stabilizergroup--pauli"></a>stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tablica operatorów multiqubit Pauli.
Na przykład, `stabilizerGroup[0]` jest listą macierzy Pauli z jednym qubitm, który jest produktem, który jest generatorem stabilizatorów.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Tablica qubits, w której jest zdefiniowany kod stabilizatorów.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __nieprawidłowy <Result>__ 

Operacja określająca sposób mierzenia operatora multiqubit Pauli.



## <a name="output--syndrome"></a>Wynik: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Wynik pomiarów.

## <a name="remarks"></a>Uwagi

Nie sprawdza to, czy dany zestaw generatorów jest podróży.
Jeśli nie są one podróży, wynik pomiarów może być dowolny.
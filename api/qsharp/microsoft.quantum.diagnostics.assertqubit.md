---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 0e005230427bbd570133712679c51661e7ae6496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202247"
---
# <a name="assertqubit-operation"></a>AssertQubit, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Potwierdza, że qubit `q` znajduje się w oczekiwanej eigenstate operatora Pauli z.

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="expected--__invalidresult__"></a>Oczekiwano __: <Result> nieprawidłowe__

Który stan qubit powinien znajdować się w: `Zero` lub `One` .


### <a name="q--qubit"></a>p: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, którego stan jest potwierdzony.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Umożliwia potwierdzenie dowolnego stanu qubit, a nie tylko $Z $ eigenstates.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)
---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853455"
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
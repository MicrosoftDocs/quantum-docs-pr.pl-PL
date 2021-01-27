---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851826"
---
# <a name="measureidentity-operation"></a>MeasureIdentity, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mierzy operator tożsamości w rejestrze qubits.

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>Dane wejściowe

### <a name="register--qubit"></a>Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr, który ma być mierzony.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__

Wartość wyniku `Zero` .

## <a name="remarks"></a>Uwagi

Ponieważ $ \boldone $ ma tylko eigenvalue $1 $ i nie ma negatywnej eigenvalue, ta operacja zawsze zwraca wartość `Zero` odpowiadającą eigenvalue $ + 1 = (-1) ^ 0 $ i nie powoduje zwinięcia stanu `register` .

Ta operacja nie jest przydatna, ale jest przydatna w kontekście Tomography procesu, ponieważ zawiera informacje na temat zachowywania śledzenia procesów Quantum.
W szczególności maszyna docelowa ze skalą stratną powinna zastąpić tę operację rzeczywistą wartością miary $ \boldone $.
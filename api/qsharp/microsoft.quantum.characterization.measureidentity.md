---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714966"
---
# <a name="measureidentity-operation"></a>MeasureIdentity, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Package [](https://nuget.org/packages/)


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
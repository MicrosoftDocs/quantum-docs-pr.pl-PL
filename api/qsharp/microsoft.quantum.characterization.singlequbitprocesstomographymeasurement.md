---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714924"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>SingleQubitProcessTomographyMeasurement, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Package [](https://nuget.org/packages/)


Wykonuje pojedynczy qubit proces pomiaru Tomography w bazie Pauli, z uwzględnieniem konkretnego kanału zainteresowania.

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>Dane wejściowe

### <a name="preparation--pauli"></a>Przygotowanie: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Element Pauli $P $, w którym ma zostać przygotowany qubit.


### <a name="measurement--pauli"></a>Pomiar: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Element bazowy Pauli $Q $, w którym ma być mierzona wartość qubit.


### <a name="channel--qubit--unit"></a>Channel: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Pojedynczy qubit kanału $ \Lambda $, którego zachowanie jest szacowane przy użyciu Tomography procesu.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__

Wynik `Zero` z prawdopodobieństwem $ $ \Begin{align} \Pr (\texttt{zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).
\end{align} $ $

## <a name="remarks"></a>Uwagi

Dystrybucja względem wyników zwróconych przez tę operację jest szczególnym przypadkiem dwóch qubit stanu Tomography. Let $ \rho = J (\Lambda)/$2 to stan Choi – Jamiłkowski dla $ \Lambda $. Następnie powyższa dystrybucja jest taka sama jak $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $ WHERE $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 to efektywne pomiary odpowiadające $P $ i $Q $.
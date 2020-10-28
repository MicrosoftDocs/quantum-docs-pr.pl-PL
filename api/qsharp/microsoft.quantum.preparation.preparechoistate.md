---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724000"
---
# <a name="preparechoistate-operation"></a>PrepareChoiState, operacja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Package [](https://nuget.org/packages/)


Przygotowuje stan Choi – Jamiłkowski dla danej operacji do rejestrów referencyjnych i docelowych.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="op--qubit--unit"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja $ \Lambda $, której stan Choi – Jamiłkowski $J (\Lambda)/2 ^ N $, ma zostać przygotowana, gdzie $N $ jest liczbą qubits, na których `op` działa.


### <a name="reference--qubit"></a>odwołanie: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr qubits rozpoczynający się w stanie $ \ket{00\cdots 0} $, który ma być używany jako odwołanie do akcji `op` .


### <a name="target--qubit"></a>target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr qubits początkowo w stanie $ \ket{00\cdots 0} $, na którym `op` ma zostać zastosowany.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Choi – Jamiłkowski State $J (\Lambda) $ procesu Quantum jest zdefiniowany jako $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ WHERE $ | X\rangle \! \rangle $ to *wektoryzacji* macierzy $X $ w Konwencji stosu kolumn. Aby poznać klasyczny opis tego stanu, można uzyskać pełne informacje na temat efektu $ \Lambda $ działającego na dowolnych Stanach danych wejściowych i podstawą fundamentów *procesów Quantum Tomography* .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. przygotowaniu. PrepareChoiStateA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft. Quantum. przygotowaniu. PrepareChoiStateC](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [Microsoft. Quantum. przygotowaniu. PrepareChoiStateCA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)
---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: cb34078c09f8c28b5b9bbda1bae6936d13ffcc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854398"
---
# <a name="preparechoistate-operation"></a>PrepareChoiState, operacja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Przygotowuje stan Choi – Jamiołkowski dla danej operacji do rejestrów referencyjnych i docelowych.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="op--qubit--unit"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja $ \Lambda $, której stan Choi – Jamiołkowski $J (\Lambda)/2 ^ N $, ma zostać przygotowana, gdzie $N $ jest liczbą qubits, na których `op` działa.


### <a name="reference--qubit"></a>odwołanie: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr qubits rozpoczynający się w stanie $ \ket{00\cdots 0} $, który ma być używany jako odwołanie do akcji `op` .


### <a name="target--qubit"></a>target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr qubits początkowo w stanie $ \ket{00\cdots 0} $, na którym `op` ma zostać zastosowany.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Choi – Jamiłkowski State $J (\Lambda) $ procesu Quantum jest zdefiniowany jako $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ WHERE $ | X\rangle \! \rangle $ to *wektoryzacji* macierzy $X $ w Konwencji stosu kolumn. Aby poznać klasyczny opis tego stanu, można uzyskać pełne informacje na temat efektu $ \Lambda $ działającego na dowolnych Stanach danych wejściowych i podstawą fundamentów *procesów Quantum Tomography*.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. przygotowaniu. PrepareChoiStateA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft. Quantum. przygotowaniu. PrepareChoiStateC](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [Microsoft. Quantum. przygotowaniu. PrepareChoiStateCA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)
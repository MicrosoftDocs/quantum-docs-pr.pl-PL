---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 7c330ebdc156e60713a734d39a3600ee1326563c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853480"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dwie operacje, potwierdzają, że działają identycznie dla wszystkich stanów wejściowych.

To potwierdzenie jest implementowane przez sprawdzenie działania operacji we wszystkich stanach formularza $V _0 \otimes... \otimes V_ {n-1} $, gdzie $V _k $ jest jednym z Stanów $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ i $ \ket{i} $ (+ 1 Eigenstate-Pauli-operator).

To potwierdzenie używa $n $ qubits i wymaga wielu wywołań operacji, które są porównywane.

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits $n $, w których operacje `givenU` i `expectedU` działania.


### <a name="givenu--qubit--unit"></a>givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja na $n $ qubits do sprawdzenia.


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Operacja odwołania na $n $ qubits, która `givenU` ma zostać porównana z.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Odwołania

Podstawa States $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ i $ \ket{i} $ to Chuang-Nielsen, opisana w [ *i. L. Czuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)
---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843403"
---
# <a name="assertprobint-operation"></a>AssertProbInt, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Potwierdza, że prawdopodobieństwo określonego stanu rejestru Quantum ma oczekiwaną wartość.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Opis

Mając $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, potwierdza, że prawdopodobieństwo $ | \ alpha_j | ^ 2 $ stanu $ \ket{j} $ indeksowane przez $j $ ma oczekiwaną wartość.

## <a name="input"></a>Dane wejściowe

### <a name="stateindex--int"></a>stateIndex: [int](xref:microsoft.quantum.lang-ref.int)

Indeks $j $ stanu $ \ket{j} $ reprezentowanego przez `LittleEndian` rejestr.


### <a name="expected--double"></a>Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)

Oczekiwana wartość $ | \ alpha_j | ^ 2 $.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Rejestr qubit, który przechowuje $ \ket{\psi} $ w formacie little-endian.


### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Absolutna tolerancja różnicy między wartością rzeczywistą i oczekiwaną.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Przykład

Załóżmy, że `qubits` Rejestr koduje qubit Quantum $ \ket{\psi} = \ sqrt {1/8} \ KET {0} + \ sqrt {7/8} \ KET {6} $ w formacie little-endian.
Oznacza to, że liczba Stany $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ i $ \ket {6} \equiv\ket {0} \ket {1} \ket {1} $. Następnie następujące potwierdzenia zostały wykonane pomyślnie:

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```
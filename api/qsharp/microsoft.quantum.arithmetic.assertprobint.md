---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721365"
---
# <a name="assertprobint-operation"></a>AssertProbInt, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


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


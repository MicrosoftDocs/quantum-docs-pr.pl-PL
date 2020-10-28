---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: MultiplexZ, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: f7b1973e18ad396ebe892ad63ae47374a7cafbd5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715778"
---
# <a name="multiplexz-operation"></a>MultiplexZ, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje obrót Pauli Z na tablicy qubits.

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a>Opis

W ten sposób stosowana jest przemnożona sterowana operacja jednostkowa, która dokonuje rotacji przez kąt $ \ theta_j $ o pojedynczej Pauli operator $Z $, gdy jest on kontrolowany przez $n $-qubit Number $ \ket{j} $.
W szczególności ta operacja może być reprezentowana przez jednostkę

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.
\end{align} $ $

## <a name="input"></a>Dane wejściowe

### <a name="coefficients--double"></a>współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]

Tablica do $2 ^ n $ współczynniki $ \ theta_j $. Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.


### <a name="control--littleendian"></a>Kontrolka: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.


### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pojedynczy rejestr qubit, który jest obrócony $e ^ {i P \ theta_j} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

`coefficients` zostanie uzupełniona o elementy $ \ theta_j = $0,0, jeśli określono mniej niż $2 ^ n $.

## <a name="references"></a>Dokumentacja

- Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApproximatelyMultiplexZ](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)
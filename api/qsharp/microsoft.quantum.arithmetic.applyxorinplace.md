---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210117"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje operacje bitowe-XOR między klasyczną liczbą całkowitą i liczbą całkowitą reprezentowaną przez rejestr qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

Stosuje `X` operacje do qubits w rejestrze little-endian w oparciu o 1 bity w postaci liczby całkowitej.

Poinformuj nas o tym, `value` że i pozwól y być liczbą całkowitą bez znaku `target` , a następnie `InPlaceXorLE` wykonuje operację określoną przez następującą mapę: $ \ket{y}\rightarrow \ket{y\oplus a} $, gdzie $ \oplus $ jest operatorem wyłącznym or.

## <a name="input"></a>Dane wejściowe

### <a name="value--int"></a>wartość: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita, która przyjmuje wartość nieujemną.


### <a name="target--littleendian"></a>obiekt docelowy: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Rejestr Quantum używany do przechowywania `value` w kodowaniu little-endian.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)


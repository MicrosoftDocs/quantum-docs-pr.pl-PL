---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721392"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Stosuje operacje bitowe-XOR między klasyczną liczbą całkowitą i liczbą całkowitą reprezentowaną przez rejestr qubits.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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


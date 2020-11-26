---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 969be01204bad497496ff24cb64213f5fe1f089b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209761"
---
# <a name="xbits-function"></a>XBits, funkcja

Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Zwraca liczbę całkowitą reprezentującą X bity tablicy operatorów Pauli.

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="paulis--pauli"></a>Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tablica operatorów Pauli, która ma być reprezentowana jako liczba całkowita.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita $x $ z reprezentacją binarną $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, gdzie $p _i = $0, jeśli `paulis[i]` jest `PauliI` lub `PauliZ` i gdzie $p _i = $1, jeśli `paulis[i]` jest `PauliX` lub `PauliY` .

## <a name="remarks"></a>Uwagi

Funkcja zgłosi, jeśli długość `paulis` tablicy jest większa niż 63.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. bitowy. ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)
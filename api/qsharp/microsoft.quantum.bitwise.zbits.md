---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718533"
---
# <a name="zbits-function"></a>ZBits, funkcja

Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)

Package [](https://nuget.org/packages/)


Zwraca liczbę całkowitą reprezentującą bity Z tablicy operatorów Pauli.

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="paulis--pauli"></a>Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tablica operatorów Pauli, która ma być reprezentowana jako liczba całkowita.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita $x $ z reprezentacją binarną $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, gdzie $p _i = $0, jeśli `paulis[i]` jest `PauliI` lub `PauliX` i gdzie $p _i = $1, jeśli `paulis[i]` jest `PauliY` lub `PauliZ` .

## <a name="remarks"></a>Uwagi

Funkcja zgłosi, jeśli długość `paulis` tablicy jest większa niż 63.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. bitowy. XBits](xref:Microsoft.Quantum.Bitwise.XBits)
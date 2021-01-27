---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842058"
---
# <a name="zbits-function"></a>ZBits, funkcja

Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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